# insertform
<?php
require 'Conex.php';
//Recibir los datos y almacenarlos en variables   

    //___________________________________FORMULARIO 1________________________________________________________
//debug
//print_r($_POST);exit; 

if(
isset($_POST["FechayHora"])&&
isset($_POST["LugardelosHechos"])&&
isset($_POST["CausadelosHechos"])&&
isset($_POST["NombreAgenteTansito"])&&
isset($_POST["InformedeTansito"])&&
isset($_POST["VelocidaddelVehiculo"])&&
isset($_POST["EstadodelVehiculo"])&&
isset($_POST["DescripciondelHecho"])&&
isset($_POST["FormatodeAccidenteeIncidente"])&&
isset($_POST["AdjuntarImagen1"])&&
isset($_POST["AdjuntarImagen2"])&&
isset($_POST["AdjuntarImagen3"])&&
isset($_POST["TipodeNovedad"])&&
isset($_POST["Vehiculo"])&&
isset($_POST["TipodeVehiculo"])&&
isset($_POST["NumeroDocumentoIdentidad"])&&
isset($_POST["Genero"])&&
isset($_POST["RoloCargo"])&&
isset($_POST["TipoDocumentoIdentidad"])&&
isset($_POST["NiveldeAcceso"])&&
isset($_POST["NumerodePoliza"])&&
isset($_POST["TipodePoliza"])&&
isset($_POST["VehiculoqueaplicalaPoliza"])
){
$insertar = "INSERT INTO tblaccidentesincidentes(AccFechaHora,
                                                 AccLugar, 
                                                 AccCausa, 
                                                 AccAgenteTransito, 
                                                 AccInformeTransito, 
                                                 AccVelocidad, 
                                                 AccEstadoVehiculo, 
                                                 AccDescripcion, 
                                                 AccAdjuntoFormato, 
                                                 AccImagen1, 
                                                 AccImagen2, 
                                                 AccImagen3, 
                                                 tblNovedad_idNovedad, 
                                                 TblVehiculo_idVehiculo, 
                                                 TblVehiculo_TblTipoVehiculo_idTipoVehiculo, 
                                                 TblUsuario_UsuDocumentoIdentidad, 
                                                 TblUsuario_TblGenero_idGenero, 
                                                 TblUsuario_tblRol_RolCodigo,                         TblUsuario_TblTipoDocumentoIdentidad_IdTipoDocumentoIdentidad, 
                                                 TblUsuario_TblNivelAcceso_idNivelAcceso, 
                                                 TblPolizaSeguros_PolNroPoliza, TblPolizaSeguros_TblTipoPolizaSeguros_idTipoPolizaSeguros, 
                                                 TblPolizaSeguros_TblVehiculo_idVehiculo) 
                                         VALUES ('".$_POST["FechayHora"]."',
                                                 '".$_POST["LugardelosHechos"]."',
                                                 '".$_POST["CausadelosHechos"]."',
                                                 '".$_POST["NombreAgenteTansito"]."',
                                                 '".$_POST["InformedeTansito"]."',
                                                 '".$_POST["VelocidaddelVehiculo"]."',
                                                 '".$_POST["EstadodelVehiculo"]."',
                                                 '".$_POST["DescripciondelHecho"]."',
                                                 '".$_POST["FormatodeAccidenteeIncidente"]."',
                                                 '".$_POST["AdjuntarImagen1"]."',
                                                 '".$_POST["AdjuntarImagen2"]."',
                                                 '".$_POST["AdjuntarImagen3"]."',
                                                 '".$_POST["TipodeNovedad"]."',
                                                 '".$_POST["Vehiculo"]."',
                                                 '".$_POST["TipodeVehiculo"]."',
                                                 '".$_POST["NumeroDocumentoIdentidad"]."',
                                                 '".$_POST["Genero"]."',
                                                 '".$_POST["RoloCargo"]."',
                                                 '".$_POST["TipoDocumentoIdentidad"]."',
                                                 '".$_POST["NiveldeAcceso"]."',
                                                 '".$_POST["NumerodePoliza"]."',
                                                 '".$_POST["TipodePoliza"]."',
                                                 '".$_POST["VehiculoqueaplicalaPoliza"]."')";
}

//Ejecutar consulta
$resultado = mysqli_query($conexion,$insertar);
if (!$resultado) {
    echo 'Error al guardar insertar '.mysqli_error($conexion).'<br/>';
   }else{
       echo 'Los datos de insertar se han guardado satisfactoriamente!<br/>";';
}    
       
//Cerrar conexión
    mysqli_close($conexion);


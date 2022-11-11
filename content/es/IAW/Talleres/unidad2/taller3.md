---
categories: ["Prácticas"]
tags: ["IAW", "php", "docs"]
title: "Taller 3: Instalación de la aplicación BookMedik"
linkTitle: "Taller 3"
date: 2022-11-03
type: "docs"
---

##### 1. Entrega la configuración del virtualhost



##### 2. Entrega el contenido del fichero `Database.php`

{{< highlight bash "linenos=table,hl_lines=7" >}}
<?php
class Database {
        public static $db;
        public static $con;
        function Database(){
                $this->user="roberto";$this->pass="roberto";$this->host="localhost";$this->ddbb="bookmedik";
        }

        function connect(){
                $con = new mysqli($this->host,$this->user,$this->pass,$this->ddbb);
                $con->query("set sql_mode=''");
                return $con;
        }

        public static function getCon(){
                if(self::$con==null && self::$db==null){
                        self::$db = new Database();
                        self::$con = self::$db->connect();
                }
                return self::$con;
        }

}
?>
{{< / highlight >}}

##### 3. Entrega una captura con el acceso a bookmedik, después del login



##### 4. Indica el fichero que has modificado (con el path completo) para modificar el límite de memoria. Muestra un pantallazo de la salida del fichero `info.php` donde se vea el cambio

He modificado el fichero `/etc/php/7.4/apache2/php.ini`. 
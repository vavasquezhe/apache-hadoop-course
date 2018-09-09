# Instalación y configuración de Hadoop en modo local (*standalone*)


Esta guía describe la instalación y configuración  de Apache Hadoop en modo standalone. 
Esta es la instalación más simple.

### Paso 1

Descargue e instale Java Development Kit (JDE), versión 8. 

http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html


### Paso 2

Descargue la versión más reciente de Apache Hadoop.

http://hadoop.apache.org/releases.html


### Paso 3

Habrá `Terminal`, navegue hasta el directorio de descargas y descomprima Hadoop. 
Luego renombre el directory y copielo a su directorio de usuario. En el resto de 
esta guía se asumirá que esta es la ubicación de la instalación. Siempre 
reemplace `USERNAME` por su nombre de usuario.

```
tar -xzf hadoop-x.y.z.tar
mv hadoop-x.y.z /Users/USERNAME/hadoop
```

### Paso 4

Edite su archivo `.bash_profile` usando un editor de textos. Puede hacer esto desde
la línea de comandos con:

    nano ~/.bash_profile
    
Agregue los siguientes comandos:


    export JAVA_HOME=$(/usr/libexec/java_home)
    export HADOOP_HOME="/Users/USERNAME/hadoop"
    export HADOOP_COMMON_LIB_NATIVE_DIR="$HADOOP_HOME/lib/native"
    export HADOOP_OPTS="-Djava.library.path=$HADOOP_HOME/lib/native"
    export HADOOP_OPTS="$HADOOP_OPTS -Djava.library.path=$HADOOP_HOME/lib"
    export HADOOP_CLASSPATH=${JAVA_HOME}/lib/tools.jar
    export PATH="$JAVA_HOME/bin:$HADOOP_HOME:$PATH"


### Paso 5

Verifique la instalación. En Terminal digite 

    source ~/.bash_profile


Luego digite `hadoop` en la línea de comandos. Como resultado, debe imprimirse la ayuda de hadoop en la pantalla.

**Nota.--** En este paso, Apache Hadoop se puede ejecutar en modo *standalone*.

**Nota,--** Hadoop usará el sistema local de archivos como sistema HDFS.

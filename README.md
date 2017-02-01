# seriesdetiempo
temporal <- tempfile()
download.file("http://www.beta.inegi.org.mx/contenidos/proyectos/enchogares/regulares/enoe/microdatos/enoe_15ymas/2016/2016trim1_dbf.zip",temporal)
files=unzip(temporal,list = TRUE)$Name
unzip(temporal,files = files[grepl("dbf",files)])
install.packages("foreing")
require(foreign)
SDEMT11 <- data.frame(read.dbf("sdemt116.dbf"))

View(SDEMT11)

nombres <- c("sergio","carlos","paula") # c= concatenar ,contruir vectores; ""= caracteres en letras
# #=comentario
# <- es para dar el mombre es como el igual pero no podemos igualar aqui
# edad es el mombre de mi vector

  edad <- c(23,43,51)
base1 <- data.frame(nombres,edad) #data.frame=funcion y sus parentesis para la cantidad de variables
 3+4

 table (SDEMT11$SEX) #tabla para contar sexo
 table(SDEMT11$ENT)
 table(base1$nombres)

 install.packages("questionr")### bajamos de internet la libreria
 require(questionr) # mandamos llamr la libreria a mi seccion de R
 wtd.table(SDEMT11$SEX, weights = SDEMT11$FAC)
 

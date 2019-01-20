# codigo-Udemy
#Código curso Contar historias con datos Udemy
#CLASE 7
#Para visualizar el dataset
Descripcionpersonas

#Para ver la estructura del dataset
str(Descripcionpersonas)

#Cambiar numeros por M y F para la variable genero en el dataset
Descripcionpersonas$Género <- factor(Descripcionpersonas$Género, labels = c("M", "F"))

#CLASE 8
#Para ver un plot de estatura para hombres y mujeres
plot(Descripcionpersonas$Estatura~Descripcionpersonas$Genero, xlab="Genero", ylab="Estatura", main="Estatura personas")

#Para ver un plot de peso y estatura
plot(Descripcionpersonas$Peso.Kg.~Descripcionpersonas$Estatura, xlab="Estatura", ylab="Peso", main="Relación estatura y peso")

#histograma
ggplot()+geom_histogram(data=Descripcionpersonas, aes(x=Peso.Kg.), fill="blue", color="red", binwidth=3)+
labs(y="Cantidad personas", x="Peso en kg",
title="Peso de las personas")+
theme(panel.background=element_blank(), panel.grid.major=element_blank(),panel.grid.minor=element_blank())

#Para visualizar correlaciones
pairs(Descripcion.personas[,3:5])

#Para filtrar o hacer subsetting
mujeres <- subset(Descripcion.personas, Genero == 'F',)

#Ahora ver esa selección de solo mujeres
mujeres

#Y hacer pairs de solo mujeres
pairs(mujeres[,3:5])

#CLASE 9
#Para promedios
mean(Descripcion.personas$Peso.Kg.)

#Es lo mismo que escribir:
mean(Descripcion.personas[,3])

#Pedir a R las estadisticas descriptivas del dataset (mediana, cuartiles, promedio)
summary(Descripcion.personas)

#Ver la diferencia de cada dato frente al promedio en una variable. En este caso, la diferencia de cada persona frente al
#promedio del peso del grupo
Descripcion.personas$Diff <- Descripcion.personas$Peso.Kg. - mean(Descripcion.personas$Peso.Kg)
print(Descripcion.personas)

#Desviacion estandar del peso de las personas. Es decir, la variacion del peso de cada persona frente al promedio de peso del grupo.
sd(Descripcion.personas$Peso.Kg.)

#Coeficiente de variación: si supera 25% los datos estan desviados del promedio. Si no, los datos son homogéneos.
coeficiente <- sd(Descripcion.personas$Peso.Kg.)/mean(Descripcion.personas$Peso.Kg.)*100
print(coeficiente)

#Ver correlación del dataset en unas variables
cor(Descripcion.personas[,3:5])

#Clase 15 con dataset dias festivos
Festivos <- read.csv("~/Desktop/Festivos.csv")
View(Festivos)

#Plot de dataset Dias festivos relacionando pib percapita en cada región
plot(Festivos$Pib.per.cápita ~ Festivos$Región, xlab="Región", ylab="Pib per cápita", main="Pib per cápita en paises con más dias festivos en cuatro regiones")

#Ahora el plot con ggplot
grafica <- ggplot(Festivos, aes(x=Región, y=puntaje.competitividad, fill=Región))+geom_boxplot()+
labs(x="Regiones", y="Puntaje Competitividad", title="Competitividad en paises con más festivos por Región")+
theme(legend.position = "none");grafica +
theme(panel.background = element_blank(),panel.grid.major=element_blank(),
panel.grid.minor=element.blank())

#plot de pib per cápita relacionado con cantidad de dias festivos al año
plot(Festivos$Pib.per.cápita ~ Festivos$Dias.Festivos.año, xlab="Dias Festivos", ylab="Pib Per cápita",
main="Relación Dias Festivos - Pib Per cápita en países con más días festivos en cuatro regiones")

#El mismo plot (scatter plot) pero ahora con ggplot y con colores en los puntos según la región
ggplot(Festivos, aes(Dias.Festivos.año,Pib.per.cápita))+geom_point(aes(color=factor(Región)))+
xlab("Dias festivos") + ylab("Pib per cápita")+
ggtitle ("Relación dias festivos - Pib per cápita en paises con más dias festivos en cuatro regiones")

#Histograma
ggplot()+geom_histogram(data=Festivos, aes(X=Dias.Festivos.año),
fill="blue", color="red", binwidth=1)+
labs(y="Conteo paises", x="Dias festivos al año",
title="Paises con mas dias festivos al año en cuatro regiones del mundo")+
theme(panel.background=element_blank(),panel.grid.major=element_blank(),
panel.grid.minor=element_blank())

#visualizacion de posibles correlaciones con pairs
pairs(Festivos[,3:7])

#correlación de variables en estos paises
cor(Festivos[,3:7])

#Una matriz de scatter plot con paquete car
install.packages("car")
scatterplotMatrix(~ Dias.Festivos.año+Pib.per.cápita + X..Desempleo, data=Festivos)

#Diferencia del pib per cápita de cada país frente al promedio
Festivos$Diff <- Festivos$Pib.per.cápita - mean(Festivos$Pib.per.cápita)
print(Festivos)

#Resúmen de estadisticas claves del dataset Festivos
summary(Festivos)



























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




















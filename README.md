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









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


















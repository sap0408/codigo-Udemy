# codigo-Udemy
Código curso Contar historias con datos Udemy
CLASE 7
#Para visualizar el dataset
Descripcionpersonas

#Para ver la estructura del dataset
str(Descripcionpersonas)

#Cambiar numeros por M y F para la variable genero en el dataset
Descripcionpersonas$Género <- factor(Descripcionpersonas$Género, labels = c("M", "F"))






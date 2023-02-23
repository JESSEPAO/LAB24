####################
#                  #
# Copiar todo esto #
#                  #
####################
# Hecho con gusto por JESSICA PAOLA AGUILAR SERVIN


# LABORATORIO - Analisis de Redes en R - Indicadores básicos Globales 
library(EconGeo)


# cargar DATA
EL= read.csv("https://raw.githubusercontent.com/PABalland/ON/master/lesmis-el.csv")

# ver encabezado
head (EL)

#transformar a  matriz 
MM <- get.matrix(EL)

#Ver matriz simetrica (red no dirigida- red bidireccional)
#Diferencias entre red dirigida y no dirigida
#Esta es una red no dirigida porque la matriz de adyaciencias es simetrica

#Grafica
library(igraph)
g <- graph_from_data_frame(d=EL, directed = FALSE)
g

plot(g)

#elimina los pesos
EL$Weight = NULL
head(EL)


#grafico tridimensional
install.packages("networkD3")
library(networkD3)
simpleNetwork(EL)

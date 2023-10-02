## Daniel Alejandro Romero Castañeda (202215842, Sergio Andres Delgado Quevedo (202212287) y Carlos Andres Castillo (202116837)
## R version 4.3.1 (2023-06-16 ucrt)
## llamar librerias
library(pacman)
library(rio)
library(data.table)
library(tidyverse)
## Importar/exportar bases de datos
## Importar
setwd("~/Problemset2/output")
      

location<-import(file= "location.rds.csv" ,skip=1)
identificacion <- import(file="identification.rds.csv" , skip=1)

## Exportar
saveRDS(data.frame(identificacion), "identification.rds")
saveRDS(data.frame(location), "location.rds")
## Generar variables
...
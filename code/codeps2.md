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
      

location<-import(file= "Modulo de sitio o ubicacion.sav" ,skip=1)
identificacion <- import(file="Modulo de identificacion.sav" , skip=1)

## Exportar
saveRDS(data.frame(identificacion), "identification.rds")
saveRDS(data.frame(location), "location.rds")

## Generar variables
## Generar variable con condicional 1
identificacion <- mutate(identificacion, business_type = case_when(GRUPOS4 == 1 ~ "agricultura", GRUPOS4 == 2 ~ "industria manufacturera", GRUPOS4 == 3 ~ "comercio", GRUPOS4 == 4 ~ "servicios"))
## Generar variable con condicional 2
location <- mutate(location, local = ifelse(test = (P3053 == 6 | P3053 == 7 ), yes=1 , no=0))

## Eliminar filas/columnas de un conjunto de datos

## crear subconjunto
identification_sub <- subset(x = identificacion, business_type == "industria manufacturera")
## crear objeto conservando variables de otro objeto
.....
## sobreescribir variables de un objeto en otro
......
## combinar base de datos
....
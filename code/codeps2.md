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
identificacion <- mutate(identificacion, business_type = case_when(GRUPOS4 == 1 ~ "agricultura", GRUPOS4 == 2 ~ "industria manufacturera", GRUPOS4 == 3 ~ "comercio", GRUPOS4 == 4 ~ "servicios"))

location <-  mutate(location, local = ifelse(test = ()))
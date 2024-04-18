##COBERTURA MOVIL EN COLOMBIA POR PROVEEDORES DE TELEFONIA, DEPARTAMENTO, MUNICIPIO##

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px

##DATASET COBERTURA MOVIL 
datos= pd.read_csv('CoberturaMovil.csv')

##Columnas
datos.columns

#DTypes
datos.dtypes

#Dataframe
dataframe=pd.DataFrame(datos)
proveedor=dataframe["PROVEEDOR"].value_counts()
mun= dataframe["MUNICIPIO"].value_counts()
dep=dataframe["DEPARTAMENTO"].value_counts().head()

dataframe
proveedor
mun
dep

##GRAFICO 1 Matplotlib
plt.subplot(1,1,1)
proveedor.plot(kind="bar", rot=20)

plt.title("PROVEEDOR")
plt.show()


#Grafico 2 Seaborn
sns.displot(datos[ "DEPARTAMENTO"])
plt.show()


#Grafico 3 Plotly
fig = px.line(datos, x = 'PROVEEDOR', y = 'DEPARTAMENTO', title='Cobertura por proveedor en los Departamento de Colombia')
fig.show()


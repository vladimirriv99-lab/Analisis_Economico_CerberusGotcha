  # Analisis_Economico_CerberusGotcha
  Análisis de la asignación de capital para el negocio Cerberus Gotcha, concentración de los activos asi como su riesgo potencial en los equipos, con una identificación de la optima distribución de recursos para el mantenimiento del equipo y  recomendación operativa para el dueño
  ## PROBLEMATICA
  El cliente deseaba saber en cuanto tiempo podria recuperar su inversión  inicial o si debia modificar precios al publico para poder obtener mejores ganancias.
  ## Tablas
  realicé una digitalización de sus insumos asi como de los costos actuales del servicio en comparación a su costo de adquisición a través de postgreSql 
  <img width="2131" height="796" alt="image" src="https://github.com/user-attachments/assets/b74318b5-3da2-4a02-93e2-c0196763b8e1" />
  primera tabla básica para los unicos servicios que tiene actualmente 
  <img width="2034" height="731" alt="image" src="https://github.com/user-attachments/assets/b16b6233-9aaf-4ae8-a180-665984b59155" />
  Segunda tabla de sus activos 
  <img width="2217" height="1381" alt="image" src="https://github.com/user-attachments/assets/360d4577-4b22-4d1e-8d11-ef1183e55c18" />
  En este punto aun no me proporcionaba el costo unitario por activo asi que al recibir dicha información agregué la columna despues.
  <img width="1271" height="132" alt="image" src="https://github.com/user-attachments/assets/66bac92d-07b4-4028-9e8b-f7fd7bad9030" />
  Por respeto al cliente no subo sus costos de adquisicion pero estos fueron actualizados mediante la linea de codigo:
  UPDATE
  Inventario_CG set Costo_unitario = *monto* where CATEGORIA = 'ARMA';
  la cual fue modificada para cada uno de los activos
  <img width="1662" height="1388" alt="image" src="https://github.com/user-attachments/assets/48a3c02a-bf28-40b5-873c-32454de6ac58" />
  al realizar los querys necesarios, obtuvimos el monto total de inversión  tanto de manera global como unitaria. 
  Debido al proceso llevado me funcionaba crear una vista temporal para poder obtener los datos requeridos ya que elaborar una tabla correspondiente era innecesaria lo cual nos arrojo que casi el 77% de la inversión  de capital se concentraba en un solo activo "Marcadoras" y minimamente en el resto de los activos
  <img width="1337" height="541" alt="image" src="https://github.com/user-attachments/assets/7835e768-1286-4a9b-8b6e-dd1b8fe52729" />
  <img width="1255" height="231" alt="image" src="https://github.com/user-attachments/assets/530c943e-a3db-4de0-8ba7-d1759a6ae914" />
  debido a la naturaleza del proyecto era imposible conjuntar los productos por kit de renta proporcionados ya que un solo activo podia combinarse de manera variada con el resto de los activos por lo tanto para poder hacer "cruce" recurri a utilizar subquerys dentro de la consulta 
  <img width="2118" height="811" alt="image" src="https://github.com/user-attachments/assets/a36960ef-0eb7-424c-9050-2a3678440fd5" />
  Dando como resultado que el retorno de inversión de capital se daba al rentar 1234 kit's completos pero dado que teniamos varios activos, analizamos por categoría, dando a conocer un dato ya antes identificado, que las marcadoras abarcaban más del 77% de la inversión.
  <img width="2448" height="743" alt="image" src="https://github.com/user-attachments/assets/ed6eabfd-ff35-494a-b33b-a5ce1741ca88" />
  seguido por la protección 
  
  <img width="2480" height="725" alt="image" src="https://github.com/user-attachments/assets/05e11e77-c15b-4a71-b578-cfb2d93fe351" />
  y finalmente las utilidades.
  
#RECOMENDACIONES
Incluir en el servicio más elementos de protección, con costo aparte, siendo que estos mismos son más rápidos en generar ganancias, mientras que las marcadoras requieren una cantidad de 960.00 rentas para empezar a generar ganancias, los equipos de protección solo necesitan 180.00 rentas para generar ganancias.
Asi como tener especial cuidado con las Marcadoras y  priorizar en reparaciones para las mismas, ya que si alguna de ellas se queda fuera de servicio, representaría una pérdida de dinero considerable. 

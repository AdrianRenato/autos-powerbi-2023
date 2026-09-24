# 🚗 Dashboard de Ventas Automotrices 2023 (Power BI)

Proyecto de análisis de datos en **Power BI** sobre las ventas de una empresa automotriz durante el año **2023**. Incluye análisis descriptivo de ventas, segmentación de clientes con **RFM** y análisis de retención por **cohortes**.

## 🎯 Objetivo y hallazgos

**¿Qué unidad de negocio genera más ventas?**
**UN Vehículos**, con unos 1,436 millones, cerca del 88% del total. Le siguen UN Servicio (78 M) y UN Repuestos (73 M).

**¿Qué asesor comercial vende más?**
El **Asesor 22** (49.6 M), seguido del Asesor 33 (49.0 M) y el Asesor 3 (47.9 M). Las ventas están bastante parejas entre los asesores.

**¿Cómo se distribuyen las ventas por condición de pago?**
Están muy equilibradas: Al contado 25.5%, Crédito 25.0%, Cheque 24.9% y Por letras 24.6%.

**¿Qué clientes son los más valiosos y cuáles están en riesgo?**
La segmentación RFM clasifica a los 2,000 clientes en 9 segmentos. Los segmentos con más clientes son Prometedor (19.4%) y Cliente Estable (16.7%). En el lado de riesgo, **En Riesgo** agrupa al 12.7% de los clientes y **Perdido** al 5.8%. Solo el 0.5% son Campeones y el 1.8% Big Spenders.

**¿Cuántos clientes de cada cohorte siguen comprando mes a mes?**
La retención cae rápido: de 2,000 clientes en el mes 0, unos 1,966 compran en el mes 1, 754 en el mes 3 y 213 en el mes 5.

**Estacionalidad:** las ventas se concentran en **enero–marzo y diciembre**, con una caída fuerte entre abril y octubre.

> ⚠️ Los importes de `Ventas` están en USD y SOL y el dashboard los suma sin convertir, por lo que los montos son referenciales.

## 📊 Contenido del dashboard

| Página | Qué muestra |
|---|---|
| **Descriptivo** | KPIs (Ventas Totales, Ticket Promedio, % Margen, Costo Total, Margen Bruto, Cantidades Vendidas), ventas por unidad de negocio, asesor, cliente y condición de pago. Filtros por mes, tipo de documento, marca y división. |
| **RFM** | Segmentación de clientes por Recencia, Frecuencia y Monto: dispersión de clientes, cantidad por segmento y tabla detallada. |
| **Cohorte** | Matriz de clientes activos y tasa de retención por cohorte y mes, además de clientes activos por canal y departamento. |

## 🗂️ Base de datos

Archivo: `autospb_base_de_datos.xlsx`

| Hoja | Filas | Descripción |
|---|---|---|
| `Ventas` | 50,000 | Tabla de hechos: documento, fecha, cliente, canal, artículo, cantidad, precio, importe, costos, condición de pago, cohorte y mes de retención |
| `Dim Producto` | 2,800 | Unidad de negocio, división, familia, marca, código y descripción |
| `Dim Cliente` | 2,000 | Nombre y ubicación fiscal (departamento, provincia, distrito) |
| `Dim Asesor` | 38 | Asesores comerciales y su zona |
| `Calendario` | 365 | Tabla de fechas de 2023 |

**Periodo:** 01/01/2023 – 31/12/2023
**Monedas:** las ventas están en USD y SOL.

## 🧠 Modelo y técnicas

- Modelo estrella (Ventas + dimensiones + Calendario)
- Medidas DAX: ventas, margen, ticket promedio, clientes activos, tasa de retención
- Segmentación **RFM** (Campeón, Leal Activo, Big Spender, En Riesgo, Hibernando, Perdido, etc.)
- Análisis de **cohortes** y retención
- Transformación de datos con Power Query

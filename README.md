# TechStore — Práctica SQL: Consultas Básicas SELECT

Este repositorio contiene las tres consultas solicitadas por el equipo de finanzas de TechStore. El objetivo es practicar selección de columnas, alias y buenas prácticas de escritura SQL.

---

## ❗ ¿Por qué es mala práctica usar `SELECT *` en producción?

Usar `SELECT *` puede parecer cómodo, pero trae varios problemas:

### 1. Rendimiento
Trae **todas las columnas**, incluso las que no se necesitan.  
Esto aumenta el peso de la consulta, el tráfico entre el servidor y el cliente y el tiempo de ejecución.

Ejemplo: si la tabla crece y se agregan columnas grandes (JSON, textos largos), `SELECT *` se vuelve mucho más lento sin que el analista lo note.

### 2. Mantenibilidad
Si mañana alguien agrega o elimina columnas, un reporte que usa `SELECT *` puede **romperse** o devolver datos inesperados.

Las consultas explícitas (`SELECT columna1, columna2`) son más estables y fáciles de revisar.

### 3. Seguridad
Traer todas las columnas puede exponer información sensible que el usuario **no debería ver**, como datos internos o campos que no están destinados al área de negocio.

---

## 🎯 ¿Por qué son importantes los alias para un stakeholder no técnico?

Los alias permiten transformar nombres técnicos en etiquetas claras para el negocio.

Ejemplo:

- Nombre técnico: `total_amount`
- Alias para finanzas: `monto_total`

Un analista sabe qué es `total_amount`, pero alguien del área financiera lo interpreta más rápido si ve **monto_total**, sin necesidad de conocer la estructura de la base de datos.

Los alias mejoran la comunicación, reducen errores y hacen que los reportes sean accesibles para cualquier persona del equipo.

---

## 📁 Estructura del repositorio


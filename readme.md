# 🎬 Taller MongoDB: Expresiones Regulares en un Contexto Real

## Proyecto: Plataforma de Streaming con NFTs

Este proyecto simula una **plataforma de streaming** donde los usuarios acceden a contenido audiovisual (películas y series) mediante **NFTs** como mecanismo de suscripción y pago. La base de datos refleja escenarios reales con entidades como usuarios, medios, historial de visualización, facturas y NFTs.

---

## 📦 Estructura del Repositorio

```
taller-mongodb-streamingNFT/
│
├── collection_bills.json
├── collection_employees.json
├── collection_genres.json
├── collection_historial.json
├── collection_languages.json
├── collection_media.json
├── collection_subtitle.json
├── collection_users.json
├── README.md
```

---

## 🔍 Consultas con Expresiones Regulares

A continuación se listan **30 consultas** reales y útiles utilizando expresiones regulares en MongoDB:

### Consulta 1: Alias que comienzan con `"car"`
```js
db.users.find({ alias: { $regex: "^car", $options: "i" } })
```
🔹 Útil para autocompletar nombres de usuario.

### Consulta 2: Correos que contienen `"example"`
```js
db.users.find({ correo: { $regex: "example", $options: "i" } })
```
🔹 Para detectar correos de dominio corporativo/común.

### Consulta 3: Nombres que empiezan con `"Ma"`
```js
db.users.find({ "nombre_completo.nombre": { $regex: "^Ma" } })
```
🔹 Filtrado por nombres comunes.

### Consulta 4: Descripciones con la palabra `"mundo"`
```js
db.media.find({ descripcion: { $regex: "mundo", $options: "i" } })
```
🔹 Buscar contenidos con ambientaciones globales o fantásticas.

### Consulta 5: Títulos que terminan en `"os"`
```js
db.media.find({ titulo: { $regex: "os$" } })
```
🔹 Análisis fonético y sugerencias.

### Consulta 6: Alias con mínimo 6 caracteres
```js
db.users.find({ alias: { $regex: "^.{6,}$" } })
```
🔹 Revisión de estándares de seguridad.

### Consulta 7: Subtítulos en formato `.srt`
```js
db.subtitle.find({ formato: { $regex: "^srt$" } })
```
🔹 Gestión de tipos de subtítulo.

### Consulta 8: Transacciones que comienzan con `"a"`
```js
db.bills.find({ transaccion_id: { $regex: "^a" } })
```
🔹 Filtro por bloques de transacciones.

### Consulta 9: NFTs cuyo `fingerprint` termina en `"j"`
```js
db.nfts.find({ fingerprint: { $regex: "j$" } })
```
🔹 Validación criptográfica.

### Consulta 10: Episodios con `"sueño"` en la descripción
```js
db.media.find({ "temporadas.episodios.descripcion": { $regex: "sueño", $options: "i" } })
```
🔹 Curación temática.

### Consulta 11: Correos que terminan en `.com`
```js
db.users.find({ correo: { $regex: "\.com$" } })
```
🔹 Verificación de dominios tradicionales.

### Consulta 12: Alias que contienen el número `"42"`
```js
db.users.find({ alias: { $regex: "42" } })
```
🔹 Búsqueda específica.

### Consulta 13: NFTs que mencionan `"30 días"`
```js
db.nfts.find({ descripcion: { $regex: "30 d[ií]as", $options: "i" } })
```
🔹 Duración de acceso promocional.

### Consulta 14: Nombres que comienzan con vocal
```js
db.users.find({ "nombre_completo.nombre": { $regex: "^[AEIOUaeiou]" } })
```
🔹 Estadísticas de nombres.

### Consulta 15: Descripciones con varias veces `"magia"`
```js
db.media.find({ descripcion: { $regex: "magia.*magia", $options: "i" } })
```
🔹 Alta densidad temática.

### Consulta 16: Transacciones solo con letras y números
```js
db.bills.find({ transaccion_id: { $regex: "^[a-zA-Z0-9]+$" } })
```
🔹 Validaciones sin símbolos.

### Consulta 17: Títulos que empiezan con `"La"`
```js
db.media.find({ titulo: { $regex: "^La " } })
```
🔹 Sugerencias de contenido común.

### Consulta 18: Idiomas de subtítulo que comienzan con `"lang_"`
```js
db.subtitle.find({ idioma: { $regex: "^lang_" } })
```
🔹 Verificación de prefijos estándar.

### Consulta 19: Alias que terminan en vocal
```js
db.users.find({ alias: { $regex: "[aeiou]$" } })
```
🔹 Validaciones UX.

### Consulta 20: Descripciones con números
```js
db.media.find({ descripcion: { $regex: "\d" } })
```
🔹 Identificar menciones numéricas.

### Consulta 21: Formatos con exactamente 3 letras
```js
db.subtitle.find({ formato: { $regex: "^.{3}$" } })
```
🔹 Control de longitud estándar.

### Consulta 22: Títulos de episodios que empiezan con `"El "`
```js
db.media.find({ "temporadas.episodios.titulo": { $regex: "^El " } })
```
🔹 Navegación narrativa.

### Consulta 23: Correos con números
```js
db.users.find({ correo: { $regex: "\d" } })
```
🔹 Correos sospechosos o corporativos.

### Consulta 24: Alias solo con letras
```js
db.users.find({ alias: { $regex: "^[a-zA-Z]+$" } })
```
🔹 Registros alfabéticos puros.

### Consulta 25: Títulos que contienen `"rr"`
```js
db.media.find({ titulo: { $regex: "rr" } })
```
🔹 Identificación fonética.

### Consulta 26: NFTs cuyo nombre empieza con `"Acceso"`
```js
db.nfts.find({ nombre: { $regex: "^Acceso" } })
```
🔹 Clasificación de productos por tipo.

### Consulta 27: Billeteras que empiezan por `"addr1q9"`
```js
db.users.find({ "wallet.direccion_billetera": { $regex: "^addr1q9" } })
```
🔹 Segmentación por prefijos de red.

### Consulta 28: Descripciones con signos de puntuación
```js
db.media.find({ descripcion: { $regex: "[!.,]" } })
```
🔹 Análisis de estilo narrativo.

### Consulta 29: Nombres con letra `"z"`
```js
db.users.find({ "nombre_completo.nombre": { $regex: "z", $options: "i" } })
```
🔹 Exploración lingüística.

### Consulta 30: Portadas que contienen `"cdn"`
```js
db.media.find({ portada: { $regex: "cdn" } })
```
🔹 Verificación de uso de red de distribución de contenido.

---

## ✅ Estado del Proyecto

- [x] 5 colecciones distintas
- [x] Más de 10 documentos por colección
- [x] 30 consultas útiles con expresiones regulares
- [x] Instrucciones de carga en MongoDB
- [x] Explicaciones prácticas por cada consulta

---
# 📚 GUÍA DE REFERENCIA - MULTITRACK INVENTORY

---

## 🧱 ESTRUCTURA BÁSICA XML

<?xml version="1.0" encoding="utf-8"?>
<Contenedor xmlns:android="http://schemas.android.com/apk/res/android"
android:layout_width="match_parent"
android:layout_height="match_parent">

    <!-- elementos aquí -->

</Contenedor>

---

## 📦 LAYOUTS (Contenedores)

### LinearLayout vertical (elementos uno debajo del otro)
<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:orientation="vertical">
</LinearLayout>

### LinearLayout horizontal (elementos uno al lado del otro)
<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:orientation="horizontal">
</LinearLayout>

### ScrollView (para pantallas largas)
<ScrollView
android:layout_width="match_parent"
android:layout_height="match_parent">
<!-- Solo puede tener UN hijo directo -->
</ScrollView>

---

## 🔤 ELEMENTOS VISUALES

### TextView (mostrar texto)
<TextView
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="Mi texto"
android:textSize="18sp"
android:textColor="@color/texto_oscuro"
android:textStyle="bold"/>

### EditText (campo de entrada)
<EditText
android:id="@+id/etNombre"
android:layout_width="match_parent"
android:layout_height="48dp"
android:hint="Escribe aquí"
android:background="@color/gris_secundario"
android:padding="12dp"
android:inputType="text"/>

### Button (botón)
<Button
android:id="@+id/btnAccion"
android:layout_width="match_parent"
android:layout_height="52dp"
android:text="Aceptar"
android:textColor="@color/texto_blanco"
android:background="@color/verde_boton"/>

### ImageView (imagen)
<ImageView
android:layout_width="100dp"
android:layout_height="100dp"
android:src="@drawable/mi_imagen"/>

---

## 🎨 ATRIBUTOS DE ESTILO

| Atributo                  | Para qué sirve              |
|---------------------------|-----------------------------|
| android:background        | Color o imagen de fondo     |
| android:textColor         | Color del texto             |
| android:textSize          | Tamaño del texto (usar sp)  |
| android:textStyle         | bold, italic, normal        |
| android:gravity           | Alinear: center, start, end |
| android:padding           | Espacio adentro             |
| android:layout_margin     | Espacio afuera              |
| android:visibility        | visible, invisible, gone    |

---

## 📐 TAMAÑOS

| Valor          | Significado                        |
|----------------|------------------------------------|
| match_parent   | Ocupa todo el espacio disponible   |
| wrap_content   | Ocupa solo lo que necesita         |
| 200dp          | Tamaño fijo                        |
| dp             | Para tamaños y márgenes            |
| sp             | SOLO para tamaños de texto         |

---

## 🎨 COLORES MULTITRACK INVENTORY

| Nombre                | HEX       | Uso                    |
|-----------------------|-----------|------------------------|
| @color/azul_principal | #1F3C88   | Header y fondos        |
| @color/gris_secundario| #F2F2F2   | Campos de entrada      |
| @color/verde_boton    | #2ECC71   | Botones de acción      |
| @color/texto_blanco   | #FFFFFF   | Texto sobre azul/verde |
| @color/texto_oscuro   | #000000   | Texto principal        |
| @color/texto_gris     | #888888   | Labels y subtextos     |

---

## 🪪 IDs - Cómo nombrar elementos

| Elemento   | Prefijo | Ejemplo              |
|------------|---------|----------------------|
| Button     | btn     | @+id/btnIngresar     |
| TextView   | tv      | @+id/tvTitulo        |
| EditText   | et      | @+id/etUsuario       |
| ImageView  | iv      | @+id/ivLogo          |
| LinearLayout| ll     | @+id/llHeader        |

---

## 🔗 TIPOS DE inputType (EditText)

| inputType        | Para qué              |
|------------------|-----------------------|
| text             | Texto normal          |
| textPassword     | Contraseña oculta     |
| number           | Solo números          |
| textEmailAddress | Correo electrónico    |
| phone            | Número de teléfono    |

---

## 🔵 KOTLIN - CONCEPTOS BÁSICOS

### Variables
val nombre = "Juan"       // No cambia
var edad = 25             // Puede cambiar

### Tipos de datos
var texto: String = "Hola"
var numero: Int = 10
var decimal: Double = 9.99
var activo: Boolean = true

### Conectar XML con Kotlin
val etUsuario = findViewById<EditText>(R.id.etUsuario)
val btnSignUp = findViewById<Button>(R.id.btnSignUp)

### Acción de un botón
btnSignUp.setOnClickListener {
val usuario = etUsuario.text.toString()
}

### Condición
if (usuario == "admin") {
// correcto
} else {
// incorrecto
}

---

## 🗂️ CARPETAS IMPORTANTES

| Carpeta              | Para qué                        |
|----------------------|---------------------------------|
| res/layout/          | Pantallas XML                   |
| res/values/colors.xml| Colores de la app               |
| res/drawable/        | Imágenes e íconos               |
| kotlin+java/         | Código Kotlin                   |
| manifests/           | Configuración general de la app |

## ORDEN DE ATRIBUTOS DENTRO DE LOS ELEMENTOS PARA CONFIGURAR EL TEXTO

<TextView
android:id             → 1. Identificación
android:layout_width   → 2. Dimensiones
android:layout_height  → 3. Dimensiones
android:layout_margin  → 4. Posición exterior
android:padding        → 5. Posición interior
android:background     → 6. Apariencia visual
android:text           → 7. Contenido
android:textSize       → 8. Estilo de texto
android:textColor      → 9. Estilo de texto
android:textStyle      → 10. Estilo de texto
android:fontFamily     → 11. Estilo de texto
android:gravity/>      → 12. Alineación
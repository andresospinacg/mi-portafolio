# Configuración de Google Analytics

## Pasos para configurar el seguimiento de visitas

### 1. Crear una cuenta de Google Analytics

1. Ve a [Google Analytics](https://analytics.google.com/)
2. Inicia sesión con tu cuenta de Google
3. Haz clic en "Comenzar a medir" o "Crear cuenta"
4. Completa el proceso de configuración:
   - Nombre de la cuenta
   - Nombre de la propiedad (tu sitio web)
   - Zona horaria y moneda
   - Detalles de tu negocio

### 2. Obtener tu ID de medición

1. En Google Analytics, ve a **Administración** (ícono de engranaje)
2. En la columna "Propiedad", selecciona **Flujos de datos**
3. Haz clic en tu flujo de datos web (o crea uno nuevo)
4. Copia el **ID de medición** (formato: `G-XXXXXXXXXX`)

### 3. Configurar el ID en tu proyecto

1. Crea un archivo `.env` en la raíz del proyecto:
   ```bash
   cp .env.example .env
   ```

2. Abre el archivo `.env` y reemplaza `G-XXXXXXXXXX` con tu ID real:
   ```
   PUBLIC_GOOGLE_ANALYTICS_ID=G-TU-ID-AQUI
   ```

### 4. Verificar la instalación

1. Compila y despliega tu sitio
2. Visita tu sitio web
3. En Google Analytics, ve a **Informes** > **Tiempo real**
4. Deberías ver tu visita registrada en tiempo real

## Notas importantes

- **El script solo se ejecuta en producción**: Durante el desarrollo (`npm run dev`), Google Analytics no se cargará para evitar contaminar tus estadísticas.
- **Privacidad**: Google Analytics cumple con GDPR, pero considera agregar un aviso de cookies si tu sitio es para usuarios europeos.
- **Variables de entorno**: El archivo `.env` no debe subirse a Git. Ya está incluido en `.gitignore`.

## Métricas que puedes ver

Con Google Analytics 4 podrás ver:
- Número de visitantes en tiempo real
- Páginas más visitadas
- Ubicación geográfica de tus visitantes
- Dispositivos utilizados (móvil, escritorio, tablet)
- Fuentes de tráfico (búsquedas, redes sociales, directo)
- Tiempo promedio en el sitio
- Y mucho más...

## Recursos adicionales

- [Documentación oficial de GA4](https://support.google.com/analytics/answer/10089681)
- [Configurar GA4 en Astro](https://docs.astro.build/en/guides/integrations-guide/)

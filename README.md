# Calculadora BTC

Aplicación web estática que permite convertir entre Bitcoin, satoshis y monedas populares (USD, USDT, ARS, ETH, SOL) usando precios en tiempo real provistos por la API pública de CoinGecko. El proyecto está escrito únicamente con HTML, CSS y JavaScript vanilla, por lo que puede alojarse fácilmente en GitHub Pages u otros servicios de hosting estático.

## Características principales
- Conversión bidireccional entre BTC y satoshis, y cálculo cruzado con otras monedas fiat o crypto.
- Precios actualizados en vivo mediante peticiones `fetch` a CoinGecko.
- Interfaz responsiva con modo oscuro, tipografía Inter y uso de Font Awesome para íconos.
- Actualización automática de equivalencias, diferencial en porcentajes y tabla diaria de referencias.
- Sin dependencias externas ni pasos de compilación: basta con un navegador moderno.

## Estructura del proyecto
```
CalculadoraBTC/
├── index.html        # App completa: marcado, estilos y lógica en un único archivo
└── README.md         # Documentación del repositorio
```

## Requisitos previos
- Navegador moderno (Chrome, Firefox, Edge, Safari) con soporte para `fetch`.
- Conexión a Internet para obtener los precios en vivo desde CoinGecko.

## Cómo probarlo en local
1. Clona el repositorio o descarga los archivos:
   ```bash
   git clone https://github.com/<tu-usuario>/CalculadoraBTC.git
   cd CalculadoraBTC
   ```
2. Abre `index.html` directamente en tu navegador o sirve el directorio con cualquier servidor estático, por ejemplo:
   ```bash
   python3 -m http.server 8000
   ```
   Luego visita `http://localhost:8000`.

> Consejo: usar un servidor local evita problemas con el uso de `fetch` en algunos navegadores, que bloquean las peticiones desde archivos `file://`.

## Despliegue en GitHub Pages
1. Sube los archivos a un repositorio nuevo en GitHub.
2. En la pestaña **Settings › Pages**, selecciona la rama `main` y la carpeta raíz (`/`).
3. Guarda los cambios; GitHub publicará el sitio en `https://<tu-usuario>.github.io/CalculadoraBTC/`.
4. Actualiza las URLs canónicas y sociales del `<head>` en `index.html` si publicas con un dominio distinto.

## Uso de la API de CoinGecko
- La app consulta los endpoints públicos `simple/price` de CoinGecko para BTC, ETH, SOL, USDT y ARS.
- CoinGecko impone límites de 50 peticiones/minuto; evitar recargar la página compulsivamente para no recibir respuestas 429.
- No se requiere API key, pero se recomienda revisar los [Términos de Uso de CoinGecko](https://www.coingecko.com/en/terms) antes de desplegar en producción.

## Buenas prácticas y mantenimiento
- Mantén una copia del archivo `index.html` minificada si necesitas optimizar tiempos de carga para producción.
- Revisa periódicamente que los endpoints de CoinGecko sigan vigentes.
- Considera agregar tests básicos o un linter si amplías la lógica de conversión.

## Cómo contribuir
1. Haz un fork del repositorio.
2. Crea una rama descriptiva: `git checkout -b feat/nueva-moneda`.
3. Realiza tus cambios y documenta cualquier configuración adicional.
4. Abre un Pull Request resumiendo los cambios y adjuntando capturas si afectan al UI.

## Licencia
Actualmente el proyecto no cuenta con una licencia explícita. Define la licencia que prefieras (por ejemplo, MIT) antes de aceptar contribuciones externas o distribuir el código.

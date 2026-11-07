# ATEMPO — Versiones oficiales

Este repositorio distribuye **únicamente** las versiones oficiales de ATEMPO para Android (alarmas, calendario, medicamentos y tareas). No contiene código fuente.

## Descargar

La última versión estable está siempre en **[Releases → Latest](https://github.com/AndresMesino/atempo-releases/releases/latest)**. Descargue el archivo `atempo-X.Y.Z.apk`.

- Android 8.0 (API 26) o superior.
- Si ya tiene ATEMPO instalado, no hace falta descargar nada: la propia app comprueba, descarga, verifica e instala las actualizaciones desde **Configuración → Actualizaciones**, y Android pide siempre su confirmación. Sus datos se conservan.

## Certificado oficial de firma

Todas las versiones oficiales están firmadas con este certificado:

| Dato | Valor |
|---|---|
| Titular | `CN=ATEMPO, O=ATEMPO, C=CO` |
| Algoritmo | RSA 4096 |
| **SHA-256** | `7A:33:19:FE:D7:77:27:88:57:43:64:FE:C0:06:DA:8A:11:A9:D8:91:38:70:C8:CD:B9:A1:26:0A:93:6F:7F:6A` |

Un APK firmado con cualquier otro certificado **no es oficial**: la app lo rechaza y Android tampoco permite instalarlo encima de la versión oficial.

## Cómo verificar un APK

**1. Firma digital (lo que garantiza la autenticidad).** Con las herramientas del SDK de Android:

```
apksigner verify --print-certs atempo-X.Y.Z.apk
```

Debe indicar un único firmante y `Signer #1 certificate SHA-256 digest: 7a3319fed7772788574364fec006da8a11a9d8913870c8cdb9a1260a936f7f6a`.

**2. Integridad del archivo.** Compare el SHA-256 con el de `update.json` y `SHA256SUMS.txt` del mismo Release:

```
sha256sum atempo-X.Y.Z.apk          # Linux / macOS
certutil -hashfile atempo-X.Y.Z.apk SHA256   # Windows
```

El hash por sí solo no demuestra quién publicó el archivo; la firma del punto 1 sí.

**3. Metadatos firmados (opcional).** `update.json` (lo que consulta la app) está firmado con una clave ECDSA P-256 que no se guarda en GitHub. Su clave pública está en [`keys/update-metadata-public.pem`](keys/update-metadata-public.pem):

```
base64 -d update.json.sig > update.json.sig.der
openssl dgst -sha256 -verify keys/update-metadata-public.pem -signature update.json.sig.der update.json
```

Debe responder `Verified OK`. La app hace esta misma comprobación y descarta cualquier información de versión que no la supere.

## Contenido de cada Release

| Archivo | Para qué sirve |
|---|---|
| `atempo-X.Y.Z.apk` | La aplicación firmada |
| `update.json` | Metadatos de la versión (versión, fecha, novedades, tamaño, SHA-256, certificado) |
| `update.json.sig` | Firma de `update.json` |
| `SHA256SUMS.txt` | Hashes de los archivos anteriores |

El historial completo está en [CHANGELOG.md](CHANGELOG.md).

## Seguridad

Si encuentra un APK que dice ser ATEMPO con otra firma, o cree haber hallado un problema de seguridad, abra un *issue* en este repositorio sin incluir datos personales.

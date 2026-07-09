# Demo Vulnerable App — TMAS Code Security

⚠️ **Repositorio de DEMOSTRACIÓN.** Contiene dependencias intencionalmente
desactualizadas y secrets **falsos (dummy)** con el único fin de mostrar las
capacidades de detección de **Trend Vision One Code Security (TMAS)**.

**Nada de este contenido es malicioso ni funcional.** No desplegar en producción.

## Qué demuestra

- **Vulnerabilities:** `package.json` y `requirements.txt` traen versiones viejas
  de librerías populares con CVEs conocidos → TMAS los detecta en el scan de
  vulnerabilidades open source.
- **Secrets:** `config.env` contiene credenciales de mentira con formato realista
  (AWS, API keys, tokens) → TMAS los detecta en el scan de secrets.

## Cómo se usa

1. Guardar el secret `TMAS_API_KEY` en Settings → Secrets and variables → Actions.
2. Hacer push a `master`/`main` o abrir un PR.
3. El workflow corre TMAS y reporta:
   - Comentario en el PR
   - Logs del GitHub Action
   - Consola de Vision One (CI/CD Artifacts y Code Repositories)

## Nota sobre Malware

El scan de malware **no** aplica a este repo porque solo funciona sobre imágenes
de contenedor (`docker:`/`registry:`), no sobre código fuente (`dir:.`). Por eso
`malwareScan` está en `false`. Para ver malware en la consola, usar un repo con
imagen de contenedor.

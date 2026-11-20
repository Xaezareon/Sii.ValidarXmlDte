
# Valida XML DTE

This solution allows you to validate DTE (Electronic Tax Documents) from Chile's [Servicio de Impuestos Internos (SII)](https://www.sii.cl/) against XSD schemas. It is designed as a lightweight API that processes one or more DTEs and returns validation results, highlighting schema errors or warnings.

It includes:

- Minimal API for local or cloud-based validation
- XML input (ISO-8859-1) with one or more DTEs
- Fast response format with IDs, errors, and warnings

> This repository has no relationship with the government entity [SII](https://www.sii.cl/), only for educational purposes.

---

### 📆 Supported DTE Types

- `DTE`
- `EnvioDTE`
- `EnvioBOLETA`
- `RespuestaDTE`
- `EnvioRecibos`
- `RESULTADO_ENVIO`

---

### 🚀 Usage

Once the app is running, you can sign DTEs via::

```bash
curl -X POST http://localhost:5167/api/dte/validar \
  -H "Content-Type: application/xml" \
  -d @/dte.xml
```

The response will be:

```json
[
  {
    "id": "D33F2178",
    "errors": [],
    "warnings": []
  },
  {
    "id": "D33F2179",
    "errors": ["Missing mandatory element: Receptor"],
    "warnings": []
  }
]
```


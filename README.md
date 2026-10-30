# Radar de Eventos · Feito pela Raio

Agenda pública dos eventos de TI, IA e dados, automação, indústria, saneamento e energia dos próximos 3 meses, com foco no Rio Grande do Sul.

## Como funciona

- **Branch `main`**: o site (`index.html`). É publicado uma vez no Cloudflare Pages e só muda quando o layout muda.
- **Branch `dados`**: só o arquivo `eventos.json`. Toda segunda, uma tarefa agendada atualiza esse arquivo. O site lê os eventos direto dele ao abrir, então os eventos novos aparecem sem nenhum deploy novo.
- `eventos.json` na `main` é só uma cópia de segurança, usada se a branch `dados` não responder.

## Formato do `eventos.json`

```json
{
  "meta": { "updatedAt": "AAAA-MM-DD", "weekNote": "texto curto", "window": "AAAA-MM-DD a AAAA-MM-DD" },
  "events": [
    {
      "id": "slug-estavel", "title": "", "short": "", "start": "AAAA-MM-DD", "end": "AAAA-MM-DD",
      "time": "19h–21h", "venue": "", "city": "", "uf": "RS", "km": 20,
      "format": "presencial | online | hibrido", "price": "gratuito | pago | a confirmar", "priceNote": "",
      "themes": ["ia","ti","automacao","industria","saneamento","energia","processos","inovacao"],
      "audience": ["ti","processos","energia"],
      "why": "", "url": "", "source": "", "addedAt": "AAAA-MM-DD", "pick": false
    }
  ]
}
```

## Cloudflare Pages

- Framework: **None** · Build command: vazio · Output directory: `/`
- Production branch: `main`
- Branch deployments: **None** (para a branch `dados` não gerar deploy)

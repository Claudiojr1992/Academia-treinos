# Treino em Dia

App de treinos para aluno e personal: fichas com séries e timer de descanso, agenda, controle de líquidos e carboidratos, evolução corporal com mapa do corpo, alertas de conquista e banco com 900 exercícios com demonstração em foto.

## Estrutura

| Pasta | O que tem |
|---|---|
| `web/` | O app completo em um único `index.html`, mais o banco de exercícios (`exercicios-free.json`) e as fotos de demonstração (`fotos/`). |
| `android/` | Projeto Android que empacota a pasta `web/` num WebView. |
| `.github/workflows/android.yml` | Gera o APK automaticamente a cada push na `main`. |

## Como baixar o APK

1. Abra a aba **Actions** do repositório e espere o fluxo **Gerar APK** terminar (cerca de 5 minutos).
2. Vá em **Releases** e baixe o arquivo `TreinoEmDia-v1.0.X.apk`.
3. No celular Android, abra o arquivo e permita a instalação de fontes desconhecidas.

Para gerar de novo sem alterar código: **Actions → Gerar APK → Run workflow**.

## Versão Claude × versão APK

O app foi criado como artefato no Claude, onde usa recursos da plataforma. No APK ele roda sozinho no celular:

| Recurso | No Claude | No APK |
|---|---|---|
| Treinos, séries, timer, agenda, evolução, conquistas | ✅ | ✅ |
| Líquidos e carboidratos (lista de alimentos e digitação) | ✅ | ✅ |
| Banco de 900 exercícios com fotos animadas | ✅ | ✅ |
| Sincronização entre personal e alunos, cadastro com código | ✅ | ❌ (dados ficam só no aparelho) |
| Carboidratos pela foto do prato, tradução automática | ✅ | ❌ |
| Gravação de vídeo dos exercícios | ✅ | ❌ |

Para ter sincronização no APK, o próximo passo é ligar o app a um backend próprio (por exemplo, Supabase ou Firebase).

## Testar no computador

```bash
cd web
python3 -m http.server 8000
# abra http://localhost:8000
```

## Créditos

Exercícios e fotos: [free-exercise-db](https://github.com/yuhonas/free-exercise-db) (domínio público, Unlicense). Nomes traduzidos para o português.

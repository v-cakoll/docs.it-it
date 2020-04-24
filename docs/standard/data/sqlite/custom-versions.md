---
title: Versioni di SQLite personalizzate
ms.date: 12/13/2019
description: Informazioni su come usare una versione personalizzata della libreria SQLite nativa.
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746987"
---
# <a name="custom-sqlite-versions"></a>Versioni di SQLite personalizzate

Microsoft. Data. sqlite si basa su SQLitePCLRaw. È possibile usare versioni personalizzate della libreria SQLite nativa usando un bundle o configurando un provider SQLitePCLRaw.

## <a name="bundles"></a>Bundle

SQLitePCLRaw offre pacchetti bundle che semplificano l'accesso alle dipendenze appropriate tra piattaforme diverse.

Il pacchetto Microsoft. Data. sqlite principale porta in SQLitePCLRaw. bundle_e_sqlite3 per impostazione predefinita.

Per usare un bundle diverso, installare il `Microsoft.Data.Sqlite.Core` pacchetto insieme al pacchetto del bundle che si vuole usare. I bundle vengono inizializzati automaticamente da Microsoft. Data. sqlite.

| Bundle | Description |
| --- | --- |
| SQLitePCLRaw. bundle_e_sqlite3 | Fornisce una versione coerente di SQLite su tutte le piattaforme. Include le estensioni FTS4, FTS5, JSON1 e R * tree. Questa è la modalità predefinita. |
| SQLitePCLRaw. bundle_green | Come bundle_e_sqlite3, tranne che per iOS in cui viene usata la libreria SQLite di sistema. |
| SQLitePCLRaw. bundle_zetetic | Usa le compilazioni sqlcipher ufficiali da zetetica (non incluso). |
| SQLitePCLRaw. bundle_winsqlite3 | USA winsqlite3. dll, la libreria SQLite di sistema in Windows 10. |
| SQLitePCLRaw. bundle_e_sqlcipher | Fornisce una compilazione Open Source non ufficiale di sqlcipher. |

Ad esempio, per usare la build Open Source non ufficiale di sqlcipher usare i comandi seguenti.

### <a name="net-core-cli"></a>[Interfaccia della riga di comando di .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a>Provider SQLitePCLRaw

È possibile usare la propria build di SQLite sfruttando il `SQLitePCLRaw.provider.dynamic_cdecl` pacchetto. In questo caso, si è responsabili della distribuzione della libreria nativa con l'app. Si noti che i dettagli della distribuzione delle librerie native con l'app variano notevolmente a seconda della piattaforma .NET e del runtime in uso.

Prima di tutto, è necessario implementare IGetFunctionPointer. L'implementazione è piuttosto semplice in .NET Core.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

Configurare quindi il provider SQLitePCLRaw. Assicurarsi che questa operazione venga eseguita prima che Microsoft. Data. sqlite venga usato nell'app. Evitare inoltre di usare un pacchetto di bundle SQLitePCLRaw che potrebbe sostituire il provider.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]

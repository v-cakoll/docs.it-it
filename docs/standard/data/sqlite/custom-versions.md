---
title: Versioni di SQLite personalizzate
ms.date: 05/14/2020
description: Informazioni su come usare una versione personalizzata della libreria SQLite nativa.
ms.openlocfilehash: 15db10db26bc7c5017313ca020a0e1e528ba207a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83440837"
---
# <a name="custom-sqlite-versions"></a>Versioni di SQLite personalizzate

`Microsoft.Data.Sqlite`si basa su `SQLitePCLRaw` . È possibile usare versioni personalizzate della libreria SQLite nativa usando un bundle o configurando un `SQLitePCLRaw` provider.

## <a name="bundles"></a>Bundle

`SQLitePCLRaw`fornisce pacchetti di bundle basati su praticità, che semplificano l'accesso alle dipendenze appropriate tra piattaforme diverse. Il pacchetto principale viene `Microsoft.Data.Sqlite` incluso `SQLitePCLRaw.bundle_e_sqlite3` per impostazione predefinita. Per usare un bundle diverso, installare il `Microsoft.Data.Sqlite.Core` pacchetto insieme al pacchetto del bundle che si vuole usare. I bundle vengono inizializzati automaticamente da `Microsoft.Data.Sqlite` .

| Bundle | Description |
|--|--|
| [SQLitePCLRaw. bundle_e_sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlite3) | Fornisce una versione coerente di SQLite su tutte le piattaforme. Include le estensioni FTS4, FTS5, JSON1 e R * tree. Questo è il valore predefinito. |
| [SQLitePCLRaw. bundle_e_sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlcipher) | Fornisce una build Open Source non ufficiale di `SQLCipher` . |
| [SQLitePCLRaw. bundle_green](https://www.nuget.org/packages/SQLitePCLRaw.bundle_green) | Uguale a `bundle_e_sqlite3` , tranne che per iOS in cui viene usata la libreria SQLite di sistema. |
| [SQLitePCLRaw. bundle_winsqlite3](https://www.nuget.org/packages/SQLitePCLRaw.bundle_winsqlite3) | USA `winsqlite3.dll` , la libreria SQLite di sistema in Windows 10. |
| [SQLitePCLRaw. bundle_zetetic](https://www.nuget.org/packages/SQLitePCLRaw.bundle_zetetic) | Usa le `SQLCipher` compilazioni ufficiali da zetetica (non incluse). |

Ad esempio, per usare la build Open Source non ufficiale di `SQLCipher` usare i comandi seguenti.

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

## <a name="sqlitepclraw-available-providers"></a>Provider disponibili SQLitePCLRaw

Quando non si basa su un bundle, è possibile usare i provider disponibili di SQLite con l'assembly principale.

| Provider | Description |
|--|--|
| [SQLitePCLRaw. provider. Dynamic](https://www.nuget.org/packages/SQLitePCLRaw.provider.dynamic) | Il `dynamic` provider carica la libreria nativa anziché usare <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType> gli attributi. Per altre informazioni sull'uso di questo provider, vedere [use the Dynamic provider](#use-the-dynamic-provider). |
| [SQLitePCLRaw. provider. e_sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlite3) | `e_sqlite3`È il provider predefinito. |
| [SQLitePCLRaw. provider. e_sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlcipher) | Il `e_sqlcipher` provider non è ufficiale e non è supportato `SQLCipher` . |
| [SQLitePCLRaw. provider. sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlite3) | Il `sqlite3` provider è un sistema fornito `SQLite` per iOS, MacOS e Linux. |
| [SQLitePCLRaw. provider. sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlcipher) | Il `sqlcipher` provider è per le `SQLCipher` compilazioni ufficiali da `Zetetic` . |
| [SQLitePCLRaw. provider. winsqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.winsqlite3) | Il `winsqlite3` provider è per gli ambienti Windows 10. |

Per usare il `sqlite3` provider, usare i comandi seguenti:

### <a name="net-core-cli"></a>[Interfaccia della riga di comando di .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.core
dotnet add package SQLitePCLRaw.provider.sqlite3
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.core
Install-Package SQLitePCLRaw.provider.sqlite3
```

---

Con i pacchetti installati, è necessario impostare il provider sull' `sqlite3` istanza.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SqliteProviderSample/Program.cs)]

## <a name="use-the-dynamic-provider"></a>Usare il provider dinamico

È possibile usare la propria build di SQLite sfruttando il `SQLitePCLRaw.provider.dynamic_cdecl` pacchetto. In questo caso, si è responsabili della distribuzione della libreria nativa con l'app. Si noti che i dettagli della distribuzione delle librerie native con l'app variano notevolmente a seconda della piattaforma .NET e del runtime in uso.

Prima di tutto, è necessario implementare `IGetFunctionPointer` . L'implementazione in .NET Core è la seguente:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

Configurare quindi il `SQLitePCLRaw` provider. Assicurarsi che questa operazione venga eseguita prima che `Microsoft.Data.Sqlite` venga usato nell'app. Evitare inoltre di usare un `SQLitePCLRaw` pacchetto bundle che potrebbe sostituire il provider.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]

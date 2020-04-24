---
title: Crittografia
ms.date: 12/13/2019
description: Informazioni su come crittografare il file di database.
ms.openlocfilehash: ccdd4b6b8642b3cde1c2667c9ca432a9b0ef21f2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447265"
---
# <a name="encryption"></a>Crittografia

SQLite non supporta la crittografia dei file di database per impostazione predefinita. È invece necessario usare una versione modificata di SQLite come [See](https://www.hwaci.com/sw/sqlite/see.html), [sqlcipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/)o [wxSQLite3](https://utelle.github.io/wxsqlite3). Questo articolo illustra l'uso di una build Open Source non supportata di sqlcipher, ma le informazioni si applicano anche ad altre soluzioni poiché in genere seguono lo stesso modello.

## <a name="installation"></a>Installazione

### <a name="net-core-cli"></a>[Interfaccia della riga di comando di .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

Per altre informazioni sull'uso di una libreria nativa diversa per la crittografia, vedere [versioni personalizzate di SQLite](custom-versions.md).

## <a name="specify-the-key"></a>Specificare la chiave

Per abilitare la crittografia, specificare la chiave usando `Password` la parola chiave della stringa di connessione. Usare <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> per aggiungere o aggiornare il valore dall'input dell'utente ed evitare attacchi intrusivi nelle stringhe di connessione.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a>Reimpostazione del database

Se si desidera modificare la chiave di crittografia di un database, eseguire un' `PRAGMA rekey` istruzione. Per decrittografare il database `NULL`, specificare.

Sfortunatamente, SQLite non supporta i parametri `PRAGMA` nelle istruzioni. Usare invece la funzione `quote()` per evitare attacchi intrusivi nel codice SQL.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]

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
# <a name="encryption"></a><span data-ttu-id="6644a-103">Crittografia</span><span class="sxs-lookup"><span data-stu-id="6644a-103">Encryption</span></span>

<span data-ttu-id="6644a-104">SQLite non supporta la crittografia dei file di database per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6644a-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="6644a-105">È invece necessario usare una versione modificata di SQLite come [See](https://www.hwaci.com/sw/sqlite/see.html), [sqlcipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/)o [wxSQLite3](https://utelle.github.io/wxsqlite3).</span><span class="sxs-lookup"><span data-stu-id="6644a-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="6644a-106">Questo articolo illustra l'uso di una build Open Source non supportata di sqlcipher, ma le informazioni si applicano anche ad altre soluzioni poiché in genere seguono lo stesso modello.</span><span class="sxs-lookup"><span data-stu-id="6644a-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="6644a-107">Installazione</span><span class="sxs-lookup"><span data-stu-id="6644a-107">Installation</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="6644a-108">Interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="6644a-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="6644a-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6644a-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="6644a-110">Per altre informazioni sull'uso di una libreria nativa diversa per la crittografia, vedere [versioni personalizzate di SQLite](custom-versions.md).</span><span class="sxs-lookup"><span data-stu-id="6644a-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="6644a-111">Specificare la chiave</span><span class="sxs-lookup"><span data-stu-id="6644a-111">Specify the key</span></span>

<span data-ttu-id="6644a-112">Per abilitare la crittografia, specificare la chiave usando `Password` la parola chiave della stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="6644a-112">To enable encryption, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="6644a-113">Usare <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> per aggiungere o aggiornare il valore dall'input dell'utente ed evitare attacchi intrusivi nelle stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="6644a-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a><span data-ttu-id="6644a-114">Reimpostazione del database</span><span class="sxs-lookup"><span data-stu-id="6644a-114">Rekeying the database</span></span>

<span data-ttu-id="6644a-115">Se si desidera modificare la chiave di crittografia di un database, eseguire un' `PRAGMA rekey` istruzione.</span><span class="sxs-lookup"><span data-stu-id="6644a-115">If you want to change the encryption key of a database, issue a `PRAGMA rekey` statement.</span></span> <span data-ttu-id="6644a-116">Per decrittografare il database `NULL`, specificare.</span><span class="sxs-lookup"><span data-stu-id="6644a-116">To decrypt the database, specify `NULL`.</span></span>

<span data-ttu-id="6644a-117">Sfortunatamente, SQLite non supporta i parametri `PRAGMA` nelle istruzioni.</span><span class="sxs-lookup"><span data-stu-id="6644a-117">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="6644a-118">Usare invece la funzione `quote()` per evitare attacchi intrusivi nel codice SQL.</span><span class="sxs-lookup"><span data-stu-id="6644a-118">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]

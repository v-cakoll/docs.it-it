---
title: Versioni personalizzate di SQLite
ms.date: 12/13/2019
description: Informazioni su come usare una versione personalizzata della libreria SQLite nativa.
ms.openlocfilehash: 8a2646138ea9dbecf412a2e8e0e347e2d71a5b0b
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447146"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="b3941-103">Versioni personalizzate di SQLite</span><span class="sxs-lookup"><span data-stu-id="b3941-103">Custom SQLite versions</span></span>

<span data-ttu-id="b3941-104">Microsoft. Data. sqlite si basa su SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="b3941-104">Microsoft.Data.Sqlite is built on top of SQLitePCLRaw.</span></span> <span data-ttu-id="b3941-105">È possibile usare versioni personalizzate della libreria SQLite nativa usando un bundle o configurando un provider SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="b3941-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a SQLitePCLRaw provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="b3941-106">Bundle</span><span class="sxs-lookup"><span data-stu-id="b3941-106">Bundles</span></span>

<span data-ttu-id="b3941-107">SQLitePCLRaw offre pacchetti bundle che semplificano l'accesso alle dipendenze appropriate tra piattaforme diverse.</span><span class="sxs-lookup"><span data-stu-id="b3941-107">SQLitePCLRaw provides bundle packages that make it easy to bring in the right dependencies across different platforms.</span></span>

<span data-ttu-id="b3941-108">Il pacchetto Microsoft. Data. sqlite principale porta in SQLitePCLRaw. bundle_e_sqlite3 per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b3941-108">The main Microsoft.Data.Sqlite package brings in SQLitePCLRaw.bundle_e_sqlite3 by default.</span></span>

<span data-ttu-id="b3941-109">Per usare un bundle diverso, installare il pacchetto di `Microsoft.Data.Sqlite.Core` invece insieme al pacchetto del bundle che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="b3941-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="b3941-110">I bundle vengono inizializzati automaticamente da Microsoft. Data. sqlite.</span><span class="sxs-lookup"><span data-stu-id="b3941-110">Bundles are automatically initialized by Microsoft.Data.Sqlite.</span></span>

| <span data-ttu-id="b3941-111">Bundle</span><span class="sxs-lookup"><span data-stu-id="b3941-111">Bundle</span></span> | <span data-ttu-id="b3941-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3941-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="b3941-113">SQLitePCLRaw. bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="b3941-113">SQLitePCLRaw.bundle_e_sqlite3</span></span> | <span data-ttu-id="b3941-114">Fornisce una versione coerente di SQLite su tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="b3941-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="b3941-115">Include FTS4, FTS5, JSON1 e</span><span class="sxs-lookup"><span data-stu-id="b3941-115">Includes the FTS4, FTS5, JSON1, and</span></span> | <span data-ttu-id="b3941-116">Estensioni di R \* tree.</span><span class="sxs-lookup"><span data-stu-id="b3941-116">R\*Tree extensions.</span></span> <span data-ttu-id="b3941-117">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="b3941-117">This is the default.</span></span> |
| <span data-ttu-id="b3941-118">SQLitePCLRaw. bundle_green</span><span class="sxs-lookup"><span data-stu-id="b3941-118">SQLitePCLRaw.bundle_green</span></span> | <span data-ttu-id="b3941-119">Come bundle_e_sqlite3, tranne che per iOS in cui viene usata la libreria SQLite di sistema.</span><span class="sxs-lookup"><span data-stu-id="b3941-119">Same as bundle_e_sqlite3, except on iOS where it uses the system SQLite library.</span></span> |
| <span data-ttu-id="b3941-120">SQLitePCLRaw. bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="b3941-120">SQLitePCLRaw.bundle_zetetic</span></span> | <span data-ttu-id="b3941-121">Usa le compilazioni sqlcipher ufficiali da zetetica (non incluso).</span><span class="sxs-lookup"><span data-stu-id="b3941-121">Uses the official SQLCipher builds from Zetetic (not included).</span></span> |
| <span data-ttu-id="b3941-122">SQLitePCLRaw. bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="b3941-122">SQLitePCLRaw.bundle_winsqlite3</span></span> | <span data-ttu-id="b3941-123">USA winsqlite3. dll, la libreria SQLite di sistema in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b3941-123">Uses winsqlite3.dll, the system SQLite library on Windows 10.</span></span> |
| <span data-ttu-id="b3941-124">SQLitePCLRaw. bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="b3941-124">SQLitePCLRaw.bundle_e_sqlcipher</span></span> | <span data-ttu-id="b3941-125">Fornisce una compilazione Open Source non ufficiale di sqlcipher.</span><span class="sxs-lookup"><span data-stu-id="b3941-125">Provides an unofficial, open-source build of SQLCipher.</span></span> |

<span data-ttu-id="b3941-126">Ad esempio, per usare la build Open Source non ufficiale di sqlcipher usare i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="b3941-126">For example, to use the unofficial, open-source build of SQLCipher use the following commands.</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="b3941-127">Interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="b3941-127">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="b3941-128">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b3941-128">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a><span data-ttu-id="b3941-129">Provider SQLitePCLRaw</span><span class="sxs-lookup"><span data-stu-id="b3941-129">SQLitePCLRaw providers</span></span>

<span data-ttu-id="b3941-130">È possibile usare la propria build di SQLite sfruttando il pacchetto di `SQLitePCLRaw.provider.dynamic_cdecl`.</span><span class="sxs-lookup"><span data-stu-id="b3941-130">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="b3941-131">In questo caso, si è responsabili della distribuzione della libreria nativa con l'app.</span><span class="sxs-lookup"><span data-stu-id="b3941-131">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="b3941-132">Si noti che i dettagli della distribuzione delle librerie native con l'app variano notevolmente a seconda della piattaforma .NET e del runtime in uso.</span><span class="sxs-lookup"><span data-stu-id="b3941-132">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="b3941-133">Prima di tutto, è necessario implementare IGetFunctionPointer.</span><span class="sxs-lookup"><span data-stu-id="b3941-133">First, you'll need to implement IGetFunctionPointer.</span></span> <span data-ttu-id="b3941-134">L'implementazione è piuttosto semplice in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b3941-134">The implementation is fairly trivial on .NET Core.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="b3941-135">Configurare quindi il provider SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="b3941-135">Next, configure the SQLitePCLRaw provider.</span></span> <span data-ttu-id="b3941-136">Assicurarsi che questa operazione venga eseguita prima che Microsoft. Data. sqlite venga usato nell'app.</span><span class="sxs-lookup"><span data-stu-id="b3941-136">Ensure this is done before Microsoft.Data.Sqlite is used in your app.</span></span> <span data-ttu-id="b3941-137">Evitare inoltre di usare un pacchetto di bundle SQLitePCLRaw che potrebbe sostituire il provider.</span><span class="sxs-lookup"><span data-stu-id="b3941-137">Also, avoid using a SQLitePCLRaw bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]

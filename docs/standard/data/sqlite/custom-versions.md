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
# <a name="custom-sqlite-versions"></a><span data-ttu-id="1eae9-103">Versioni di SQLite personalizzate</span><span class="sxs-lookup"><span data-stu-id="1eae9-103">Custom SQLite versions</span></span>

<span data-ttu-id="1eae9-104">`Microsoft.Data.Sqlite`si basa su `SQLitePCLRaw` .</span><span class="sxs-lookup"><span data-stu-id="1eae9-104">`Microsoft.Data.Sqlite` is built on top of `SQLitePCLRaw`.</span></span> <span data-ttu-id="1eae9-105">È possibile usare versioni personalizzate della libreria SQLite nativa usando un bundle o configurando un `SQLitePCLRaw` provider.</span><span class="sxs-lookup"><span data-stu-id="1eae9-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a `SQLitePCLRaw` provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="1eae9-106">Bundle</span><span class="sxs-lookup"><span data-stu-id="1eae9-106">Bundles</span></span>

<span data-ttu-id="1eae9-107">`SQLitePCLRaw`fornisce pacchetti di bundle basati su praticità, che semplificano l'accesso alle dipendenze appropriate tra piattaforme diverse.</span><span class="sxs-lookup"><span data-stu-id="1eae9-107">`SQLitePCLRaw` provides convenience-based bundle packages, that make it easy to bring in the right dependencies across different platforms.</span></span> <span data-ttu-id="1eae9-108">Il pacchetto principale viene `Microsoft.Data.Sqlite` incluso `SQLitePCLRaw.bundle_e_sqlite3` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1eae9-108">The main `Microsoft.Data.Sqlite` package brings in `SQLitePCLRaw.bundle_e_sqlite3` by default.</span></span> <span data-ttu-id="1eae9-109">Per usare un bundle diverso, installare il `Microsoft.Data.Sqlite.Core` pacchetto insieme al pacchetto del bundle che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="1eae9-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="1eae9-110">I bundle vengono inizializzati automaticamente da `Microsoft.Data.Sqlite` .</span><span class="sxs-lookup"><span data-stu-id="1eae9-110">Bundles are automatically initialized by `Microsoft.Data.Sqlite`.</span></span>

| <span data-ttu-id="1eae9-111">Bundle</span><span class="sxs-lookup"><span data-stu-id="1eae9-111">Bundle</span></span> | <span data-ttu-id="1eae9-112">Description</span><span class="sxs-lookup"><span data-stu-id="1eae9-112">Description</span></span> |
|--|--|
| [<span data-ttu-id="1eae9-113">SQLitePCLRaw. bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="1eae9-113">SQLitePCLRaw.bundle_e_sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlite3) | <span data-ttu-id="1eae9-114">Fornisce una versione coerente di SQLite su tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="1eae9-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="1eae9-115">Include le estensioni FTS4, FTS5, JSON1 e R \* tree.</span><span class="sxs-lookup"><span data-stu-id="1eae9-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="1eae9-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="1eae9-116">This is the default.</span></span> |
| [<span data-ttu-id="1eae9-117">SQLitePCLRaw. bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="1eae9-117">SQLitePCLRaw.bundle_e_sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlcipher) | <span data-ttu-id="1eae9-118">Fornisce una build Open Source non ufficiale di `SQLCipher` .</span><span class="sxs-lookup"><span data-stu-id="1eae9-118">Provides an unofficial, open-source build of `SQLCipher`.</span></span> |
| [<span data-ttu-id="1eae9-119">SQLitePCLRaw. bundle_green</span><span class="sxs-lookup"><span data-stu-id="1eae9-119">SQLitePCLRaw.bundle_green</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_green) | <span data-ttu-id="1eae9-120">Uguale a `bundle_e_sqlite3` , tranne che per iOS in cui viene usata la libreria SQLite di sistema.</span><span class="sxs-lookup"><span data-stu-id="1eae9-120">Same as `bundle_e_sqlite3`, except on iOS where it uses the system SQLite library.</span></span> |
| [<span data-ttu-id="1eae9-121">SQLitePCLRaw. bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="1eae9-121">SQLitePCLRaw.bundle_winsqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_winsqlite3) | <span data-ttu-id="1eae9-122">USA `winsqlite3.dll` , la libreria SQLite di sistema in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1eae9-122">Uses `winsqlite3.dll`, the system SQLite library on Windows 10.</span></span> |
| [<span data-ttu-id="1eae9-123">SQLitePCLRaw. bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="1eae9-123">SQLitePCLRaw.bundle_zetetic</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_zetetic) | <span data-ttu-id="1eae9-124">Usa le `SQLCipher` compilazioni ufficiali da zetetica (non incluse).</span><span class="sxs-lookup"><span data-stu-id="1eae9-124">Uses the official `SQLCipher` builds from Zetetic (not included).</span></span> |

<span data-ttu-id="1eae9-125">Ad esempio, per usare la build Open Source non ufficiale di `SQLCipher` usare i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="1eae9-125">For example, to use the unofficial, open-source build of `SQLCipher` use the following commands.</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="1eae9-126">Interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="1eae9-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="1eae9-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1eae9-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-available-providers"></a><span data-ttu-id="1eae9-128">Provider disponibili SQLitePCLRaw</span><span class="sxs-lookup"><span data-stu-id="1eae9-128">SQLitePCLRaw available providers</span></span>

<span data-ttu-id="1eae9-129">Quando non si basa su un bundle, è possibile usare i provider disponibili di SQLite con l'assembly principale.</span><span class="sxs-lookup"><span data-stu-id="1eae9-129">When not relying on a bundle, you can use the available providers of SQLite with the core assembly.</span></span>

| <span data-ttu-id="1eae9-130">Provider</span><span class="sxs-lookup"><span data-stu-id="1eae9-130">Provider</span></span> | <span data-ttu-id="1eae9-131">Description</span><span class="sxs-lookup"><span data-stu-id="1eae9-131">Description</span></span> |
|--|--|
| [<span data-ttu-id="1eae9-132">SQLitePCLRaw. provider. Dynamic</span><span class="sxs-lookup"><span data-stu-id="1eae9-132">SQLitePCLRaw.provider.dynamic</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.dynamic) | <span data-ttu-id="1eae9-133">Il `dynamic` provider carica la libreria nativa anziché usare <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType> gli attributi.</span><span class="sxs-lookup"><span data-stu-id="1eae9-133">The `dynamic` provider loads the native library instead of using <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType> attributes.</span></span> <span data-ttu-id="1eae9-134">Per altre informazioni sull'uso di questo provider, vedere [use the Dynamic provider](#use-the-dynamic-provider).</span><span class="sxs-lookup"><span data-stu-id="1eae9-134">For more information on using this provider, see [use the dynamic provider](#use-the-dynamic-provider).</span></span> |
| [<span data-ttu-id="1eae9-135">SQLitePCLRaw. provider. e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="1eae9-135">SQLitePCLRaw.provider.e_sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlite3) | <span data-ttu-id="1eae9-136">`e_sqlite3`È il provider predefinito.</span><span class="sxs-lookup"><span data-stu-id="1eae9-136">The `e_sqlite3` is the default provider.</span></span> |
| [<span data-ttu-id="1eae9-137">SQLitePCLRaw. provider. e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="1eae9-137">SQLitePCLRaw.provider.e_sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlcipher) | <span data-ttu-id="1eae9-138">Il `e_sqlcipher` provider non è ufficiale e non è supportato `SQLCipher` .</span><span class="sxs-lookup"><span data-stu-id="1eae9-138">The `e_sqlcipher` provider is the unofficial and unsupported `SQLCipher`.</span></span> |
| [<span data-ttu-id="1eae9-139">SQLitePCLRaw. provider. sqlite3</span><span class="sxs-lookup"><span data-stu-id="1eae9-139">SQLitePCLRaw.provider.sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlite3) | <span data-ttu-id="1eae9-140">Il `sqlite3` provider è un sistema fornito `SQLite` per iOS, MacOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="1eae9-140">The `sqlite3` provider is a system-provided `SQLite` for iOS, macOS, and Linux.</span></span> |
| [<span data-ttu-id="1eae9-141">SQLitePCLRaw. provider. sqlcipher</span><span class="sxs-lookup"><span data-stu-id="1eae9-141">SQLitePCLRaw.provider.sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlcipher) | <span data-ttu-id="1eae9-142">Il `sqlcipher` provider è per le `SQLCipher` compilazioni ufficiali da `Zetetic` .</span><span class="sxs-lookup"><span data-stu-id="1eae9-142">The `sqlcipher` provider is for official `SQLCipher` builds from `Zetetic`.</span></span> |
| [<span data-ttu-id="1eae9-143">SQLitePCLRaw. provider. winsqlite3</span><span class="sxs-lookup"><span data-stu-id="1eae9-143">SQLitePCLRaw.provider.winsqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.winsqlite3) | <span data-ttu-id="1eae9-144">Il `winsqlite3` provider è per gli ambienti Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1eae9-144">The `winsqlite3` provider is for Windows 10 environments.</span></span> |

<span data-ttu-id="1eae9-145">Per usare il `sqlite3` provider, usare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1eae9-145">To use the `sqlite3` provider use the following commands:</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="1eae9-146">Interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="1eae9-146">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.core
dotnet add package SQLitePCLRaw.provider.sqlite3
```

### <a name="visual-studio"></a>[<span data-ttu-id="1eae9-147">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1eae9-147">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.core
Install-Package SQLitePCLRaw.provider.sqlite3
```

---

<span data-ttu-id="1eae9-148">Con i pacchetti installati, è necessario impostare il provider sull' `sqlite3` istanza.</span><span class="sxs-lookup"><span data-stu-id="1eae9-148">With the packages installed, you then set the provider to the `sqlite3` instance.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SqliteProviderSample/Program.cs)]

## <a name="use-the-dynamic-provider"></a><span data-ttu-id="1eae9-149">Usare il provider dinamico</span><span class="sxs-lookup"><span data-stu-id="1eae9-149">Use the dynamic provider</span></span>

<span data-ttu-id="1eae9-150">È possibile usare la propria build di SQLite sfruttando il `SQLitePCLRaw.provider.dynamic_cdecl` pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1eae9-150">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="1eae9-151">In questo caso, si è responsabili della distribuzione della libreria nativa con l'app.</span><span class="sxs-lookup"><span data-stu-id="1eae9-151">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="1eae9-152">Si noti che i dettagli della distribuzione delle librerie native con l'app variano notevolmente a seconda della piattaforma .NET e del runtime in uso.</span><span class="sxs-lookup"><span data-stu-id="1eae9-152">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="1eae9-153">Prima di tutto, è necessario implementare `IGetFunctionPointer` .</span><span class="sxs-lookup"><span data-stu-id="1eae9-153">First, you'll need to implement `IGetFunctionPointer`.</span></span> <span data-ttu-id="1eae9-154">L'implementazione in .NET Core è la seguente:</span><span class="sxs-lookup"><span data-stu-id="1eae9-154">The implementation on .NET Core is as follows:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="1eae9-155">Configurare quindi il `SQLitePCLRaw` provider.</span><span class="sxs-lookup"><span data-stu-id="1eae9-155">Next, configure the `SQLitePCLRaw` provider.</span></span> <span data-ttu-id="1eae9-156">Assicurarsi che questa operazione venga eseguita prima che `Microsoft.Data.Sqlite` venga usato nell'app.</span><span class="sxs-lookup"><span data-stu-id="1eae9-156">Ensure this is done before `Microsoft.Data.Sqlite` is used in your app.</span></span> <span data-ttu-id="1eae9-157">Evitare inoltre di usare un `SQLitePCLRaw` pacchetto bundle che potrebbe sostituire il provider.</span><span class="sxs-lookup"><span data-stu-id="1eae9-157">Also, avoid using a `SQLitePCLRaw` bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]

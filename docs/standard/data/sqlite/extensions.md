---
title: Estensioni di
ms.date: 12/13/2019
description: Informazioni su come caricare le estensioni SQLite.
ms.openlocfilehash: 74b207205492bac48c89cb756470326f8e4a13c4
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777378"
---
# <a name="extensions"></a><span data-ttu-id="eb61e-103">Estensioni di</span><span class="sxs-lookup"><span data-stu-id="eb61e-103">Extensions</span></span>

<span data-ttu-id="eb61e-104">SQLite supporta il caricamento delle estensioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="eb61e-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="eb61e-105">Le estensioni includono elementi come funzioni SQL aggiuntive, regole di confronto, tabelle virtuali e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="eb61e-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="eb61e-106">.NET Core include una logica aggiuntiva per l'individuazione delle librerie native in altre posizioni, come i pacchetti NuGet a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="eb61e-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="eb61e-107">Sfortunatamente, SQLite non può sfruttare questa logica. chiama direttamente l'API della piattaforma per caricare le librerie.</span><span class="sxs-lookup"><span data-stu-id="eb61e-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="eb61e-108">Per questo motivo, è possibile che l'app debba modificare le variabili di ambiente PATH, LD_LIBRARY_PATH o DYLD_LIBRARY_PATH prima di caricare le estensioni SQLite.</span><span class="sxs-lookup"><span data-stu-id="eb61e-108">Because of this, your app may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="eb61e-109">In GitHub è disponibile [un esempio](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) che illustra come trovare i file binari per il runtime corrente all'interno di un pacchetto NuGet a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="eb61e-109">There's [a sample](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="eb61e-110">Per caricare un'estensione, chiamare il metodo <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>.</span><span class="sxs-lookup"><span data-stu-id="eb61e-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="eb61e-111">Microsoft. Data. sqlite garantirà che l'estensione rimanga caricata anche se la connessione viene chiusa e riaperta.</span><span class="sxs-lookup"><span data-stu-id="eb61e-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="eb61e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb61e-112">See also</span></span>

* [<span data-ttu-id="eb61e-113">Estensioni caricabili in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="eb61e-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)

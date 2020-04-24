---
title: Estensioni
ms.date: 12/13/2019
description: Informazioni su come caricare le estensioni SQLite.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242959"
---
# <a name="extensions"></a><span data-ttu-id="57b57-103">Estensioni</span><span class="sxs-lookup"><span data-stu-id="57b57-103">Extensions</span></span>

<span data-ttu-id="57b57-104">SQLite supporta il caricamento delle estensioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="57b57-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="57b57-105">Le estensioni includono elementi come funzioni SQL aggiuntive, regole di confronto, tabelle virtuali e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="57b57-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="57b57-106">.NET Core include una logica aggiuntiva per l'individuazione delle librerie native in altre posizioni, come i pacchetti NuGet a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="57b57-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="57b57-107">Sfortunatamente, SQLite non può sfruttare questa logica. chiama direttamente l'API della piattaforma per caricare le librerie.</span><span class="sxs-lookup"><span data-stu-id="57b57-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="57b57-108">Per questo motivo, potrebbe essere necessario modificare le variabili di ambiente PATH, LD_LIBRARY_PATH o DYLD_LIBRARY_PATH prima di caricare le estensioni SQLite.</span><span class="sxs-lookup"><span data-stu-id="57b57-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="57b57-109">In GitHub è disponibile [un esempio](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) che illustra come trovare i file binari per il runtime corrente all'interno di un pacchetto NuGet a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="57b57-109">There's [a sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="57b57-110">Per caricare un'estensione, chiamare il <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="57b57-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="57b57-111">Microsoft. Data. sqlite garantirà che l'estensione rimanga caricata anche se la connessione viene chiusa e riaperta.</span><span class="sxs-lookup"><span data-stu-id="57b57-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="57b57-112">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="57b57-112">See also</span></span>

* [<span data-ttu-id="57b57-113">Estensioni caricabili in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="57b57-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)

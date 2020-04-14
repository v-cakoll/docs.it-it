---
title: Estensioni
ms.date: 12/13/2019
description: Scopri come caricare le estensioni SQLite.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242959"
---
# <a name="extensions"></a><span data-ttu-id="904ff-103">Estensioni</span><span class="sxs-lookup"><span data-stu-id="904ff-103">Extensions</span></span>

<span data-ttu-id="904ff-104">SQLite supporta il caricamento delle estensioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="904ff-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="904ff-105">Le estensioni includono elementi come funzioni SQL aggiuntive, regole di confronto, tabelle virtuali e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="904ff-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="904ff-106">.NET Core include logica aggiuntiva per l'individuazione di librerie native in posizioni aggiuntive, ad esempio pacchetti NuGet di riferimento.</span><span class="sxs-lookup"><span data-stu-id="904ff-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="904ff-107">Sfortunatamente, SQLite non può sfruttare questa logica; chiama direttamente l'API della piattaforma per caricare le librerie.</span><span class="sxs-lookup"><span data-stu-id="904ff-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="904ff-108">Per questo motivo, potrebbe essere necessario modificare le variabili di ambiente PATH, LD_LIBRARY_PATH o DYLD_LIBRARY_PATH prima di caricare le estensioni SQLite.</span><span class="sxs-lookup"><span data-stu-id="904ff-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="904ff-109">C'è [un esempio](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) su GitHub che illustra la ricerca di binari per il runtime corrente all'interno di un pacchetto NuGet di riferimento.</span><span class="sxs-lookup"><span data-stu-id="904ff-109">There's [a sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="904ff-110">Per caricare un'estensione, chiamare il <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> metodo .</span><span class="sxs-lookup"><span data-stu-id="904ff-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="904ff-111">Microsoft.Data.Sqlite garantirà che l'estensione rimanga caricata anche se la connessione viene chiusa e riaperta.</span><span class="sxs-lookup"><span data-stu-id="904ff-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="904ff-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="904ff-112">See also</span></span>

* [<span data-ttu-id="904ff-113">Estensioni caricabili in fase di esecuzioneRun-Time Loadable Extensions</span><span class="sxs-lookup"><span data-stu-id="904ff-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)

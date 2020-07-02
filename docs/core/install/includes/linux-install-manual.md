---
ms.openlocfilehash: ea2883912907843e4b6d65db5ba186af43f27aaa
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85806071"
---

<!-- Note, this content is copied in ../macos.md. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="974ac-101">In alternativa ai gestori di pacchetti, è possibile scaricare e installare manualmente l'SDK e il Runtime.</span><span class="sxs-lookup"><span data-stu-id="974ac-101">As an alternative to the package managers, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="974ac-102">L'installazione manuale viene in genere eseguita come parte del test di integrazione continua o in una distribuzione Linux non supportata.</span><span class="sxs-lookup"><span data-stu-id="974ac-102">Manual install is usually performed as part of continuous integration testing or on an unsupported Linux distribution.</span></span> <span data-ttu-id="974ac-103">Per uno sviluppatore o un utente, è in genere preferibile usare un gestore di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="974ac-103">For a developer or user, it's generally better to use a package manager.</span></span>

<span data-ttu-id="974ac-104">Se si installa .NET Core SDK, non è necessario installare il runtime corrispondente.</span><span class="sxs-lookup"><span data-stu-id="974ac-104">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="974ac-105">Scaricare prima di tutto una versione **binaria** per l'SDK o il runtime da uno dei siti seguenti:</span><span class="sxs-lookup"><span data-stu-id="974ac-105">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="974ac-106">Download di ✔️ [.net 5,0 Preview](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="974ac-106">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="974ac-107">Download di ✔️ [.NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="974ac-107">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="974ac-108">Download di ✔️ [.NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="974ac-108">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="974ac-109">Tutti i download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="974ac-109">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="974ac-110">Estrarre quindi il file scaricato e usare il `export` comando per impostare le variabili usate da .NET Core e quindi assicurarsi che .NET Core si trovi nel percorso.</span><span class="sxs-lookup"><span data-stu-id="974ac-110">Next, extract the downloaded file and use the `export` command to set variables used by .NET Core and then ensure .NET Core is in PATH.</span></span>

<span data-ttu-id="974ac-111">Per estrarre il runtime e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, scaricare prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="974ac-111">To extract the runtime and make the .NET Core CLI commands available at the terminal, first download a .NET Core binary release.</span></span> <span data-ttu-id="974ac-112">Quindi, aprire un terminale ed eseguire i comandi seguenti dalla directory in cui è stato salvato il file.</span><span class="sxs-lookup"><span data-stu-id="974ac-112">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="974ac-113">Il nome del file di archivio può variare a seconda di ciò che è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="974ac-113">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="974ac-114">**Usare il comando seguente per estrarre il runtime**:</span><span class="sxs-lookup"><span data-stu-id="974ac-114">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="974ac-115">**Usare il comando seguente per estrarre l'SDK**:</span><span class="sxs-lookup"><span data-stu-id="974ac-115">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="974ac-116">I `export` comandi precedenti rendono disponibili solo i comandi di interfaccia della riga di comando di .NET Core per la sessione terminal in cui è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="974ac-116">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="974ac-117">È possibile modificare il profilo della Shell per aggiungere i comandi in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="974ac-117">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="974ac-118">Sono disponibili numerose Shell diverse per Linux e ognuna presenta un profilo diverso.</span><span class="sxs-lookup"><span data-stu-id="974ac-118">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="974ac-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="974ac-119">For example:</span></span>
>
> - <span data-ttu-id="974ac-120">**Shell bash**: *~/. bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="974ac-120">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="974ac-121">**Korn Shell**: *~/.KSHRC* o *. profile*</span><span class="sxs-lookup"><span data-stu-id="974ac-121">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="974ac-122">**Shell Z**: *~/.zshrc* o *. zprofile*</span><span class="sxs-lookup"><span data-stu-id="974ac-122">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="974ac-123">Modificare il file di origine appropriato per la shell e aggiungere `:$HOME/dotnet` alla fine dell'istruzione esistente `PATH` .</span><span class="sxs-lookup"><span data-stu-id="974ac-123">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="974ac-124">Se non `PATH` è inclusa alcuna istruzione, aggiungere una nuova riga con `export PATH=$PATH:$HOME/dotnet` .</span><span class="sxs-lookup"><span data-stu-id="974ac-124">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="974ac-125">Aggiungere anche `export DOTNET_ROOT=$HOME/dotnet` alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="974ac-125">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="974ac-126">Questo approccio consente di installare diverse versioni in posizioni separate e scegliere in modo esplicito quello da usare per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="974ac-126">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

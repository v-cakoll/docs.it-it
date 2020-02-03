---
title: Collegamento all'origine e librerie .NET
description: Procedure consigliate per l'uso del collegamento all'origine per migliorare il debug per le librerie .NET.
ms.date: 01/15/2019
ms.openlocfilehash: 3d768ae6e79efa23a8402ea37bc34cd58cd52c8c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744543"
---
# <a name="source-link"></a><span data-ttu-id="b789d-103">Collegamento all'origine</span><span class="sxs-lookup"><span data-stu-id="b789d-103">Source Link</span></span>

<span data-ttu-id="b789d-104">Il collegamento all'origine è una tecnologia che consente il debug del codice sorgente degli assembly .NET da NuGet da parte degli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="b789d-104">Source Link is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="b789d-105">Il collegamento all'origine viene eseguito durante la creazione del pacchetto NuGet e incorpora i metadati di controllo del codice sorgente all'interno degli assembly e del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b789d-105">Source Link executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="b789d-106">Gli sviluppatori che scaricano il pacchetto e che hanno abilitato il collegamento all'origine in Visual Studio possono eseguire istruzione per istruzione il relativo codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="b789d-106">Developers who download the package and have Source Link enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="b789d-107">Il collegamento all'origine fornisce i metadati di controllo del codice sorgente per creare una straordinaria esperienza di debug.</span><span class="sxs-lookup"><span data-stu-id="b789d-107">Source Link provides source control metadata to create a great debugging experience.</span></span>

## <a name="source-link-demo"></a><span data-ttu-id="b789d-108">Demo del collegamento all'origine</span><span class="sxs-lookup"><span data-stu-id="b789d-108">Source Link demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-source-link"></a><span data-ttu-id="b789d-109">Uso del collegamento all'origine</span><span class="sxs-lookup"><span data-stu-id="b789d-109">Using Source Link</span></span>

<span data-ttu-id="b789d-110">Le istruzioni per l'uso del collegamento all'origine sono reperibili nel repository GitHub [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="b789d-110">Instructions for using Source Link can be found on the [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="b789d-111">È possibile usare [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) per confermare che i metadati di collegamento all'origine siano stati incorporati correttamente nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b789d-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the Source Link metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="b789d-112">Controllare che i metadati di `Repository` siano presenti con un identificatore di commit e che i file con estensione PDB si trovino con la dll di ogni destinazione.</span><span class="sxs-lookup"><span data-stu-id="b789d-112">Check the `Repository` metadata is present with a commit identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="b789d-113">![Collegamento all'origine in Esplora pacchetti NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "Collegamento all'origine in Esplora pacchetti NuGet")</span><span class="sxs-lookup"><span data-stu-id="b789d-113">![Source Link in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "Source Link in NuGet Package Explorer")</span></span>

<span data-ttu-id="b789d-114">✔️ PROVARE a usare il collegamento di origine per aggiungere metadati del controllo del codice sorgente agli assembly e ai pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="b789d-114">✔️ CONSIDER using Source Link to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="b789d-115">È possibile migliorare ulteriormente l'esperienza di debug di uno sviluppatore tramite l'aggiunta di attributi del debugger ai tipi in uso.</span><span class="sxs-lookup"><span data-stu-id="b789d-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
>
> * <span data-ttu-id="b789d-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> può personalizzare la modalità di visualizzazione di una classe o di un campo nelle finestre delle variabili del debugger.</span><span class="sxs-lookup"><span data-stu-id="b789d-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="b789d-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> indica al debugger di eseguire il codice un'istruzione alla volta anziché eseguire un'istruzione nel codice.</span><span class="sxs-lookup"><span data-stu-id="b789d-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="b789d-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controlla se viene visualizzato un membro nelle finestre delle variabili del debugger.</span><span class="sxs-lookup"><span data-stu-id="b789d-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="b789d-119">✔️ CONSIGLIABILE pubblicare i file di simboli (`*.pdb`).</span><span class="sxs-lookup"><span data-stu-id="b789d-119">✔️ CONSIDER publishing symbol files (`*.pdb`).</span></span>

> <span data-ttu-id="b789d-120">Per ottenere un'esperienza di debug ottimale, la libreria deve pubblicare i file di simboli oltre a usare il collegamento all'origine.</span><span class="sxs-lookup"><span data-stu-id="b789d-120">For the best debugging experience your library should publish symbol files as well as use Source Link.</span></span> <span data-ttu-id="b789d-121">Per altre informazioni sui file di simboli e i pacchetti di simboli, vedere [Pacchetti di simboli](./nuget.md#symbol-packages).</span><span class="sxs-lookup"><span data-stu-id="b789d-121">For more information about symbol files and symbol packages, see [Symbol packages](./nuget.md#symbol-packages).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b789d-122">[Precedente](dependencies.md)
>[Successivo](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="b789d-122">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>

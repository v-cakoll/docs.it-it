---
title: Librerie SourceLink e .NET
description: Procedure consigliate per l'uso di SourceLink per migliorare il debug per le librerie .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 3bc72e158a5773b656095f9ce58b442469f91e67
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128928"
---
# <a name="sourcelink"></a><span data-ttu-id="446d3-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="446d3-103">SourceLink</span></span>

<span data-ttu-id="446d3-104">SourceLink è una tecnologia che consente il debug del codice sorgente degli assembly .NET da NuGet da parte degli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="446d3-104">SourceLink is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="446d3-105">SourceLink viene eseguito durante la creazione del pacchetto NuGet e incorpora i metadati di controllo dell'origine all'interno degli assembly e del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="446d3-105">SourceLink executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="446d3-106">Gli sviluppatori che scaricano il pacchetto e dispongono di SourceLink abilitato in Visual Studio possono eseguire l'istruzione del relativo codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="446d3-106">Developers who download the package and have SourceLink enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="446d3-107">SourceLink fornisce i metadati di controllo dell'origine per creare una straordinaria esperienza di debug.</span><span class="sxs-lookup"><span data-stu-id="446d3-107">SourceLink provides source control metadata to create a great debugging experience.</span></span>

## <a name="sourcelink-demo"></a><span data-ttu-id="446d3-108">Demo di SourceLink</span><span class="sxs-lookup"><span data-stu-id="446d3-108">SourceLink demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a><span data-ttu-id="446d3-109">Uso di SourceLink</span><span class="sxs-lookup"><span data-stu-id="446d3-109">Using SourceLink</span></span>

<span data-ttu-id="446d3-110">Le istruzioni per l'uso di SourceLink sono reperibili nel repository GitHub [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="446d3-110">Instructions for using SourceLink can be found on the [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="446d3-111">È possibile usare [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) per confermare che i metadati di SourceLink sono stati incorporati efficacemente nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="446d3-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the SourceLink metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="446d3-112">Controllare che i metadati `Repository` siano presenti con un identificatore di commento e che i file con estensione .pdb si trovino insieme al .dll di ogni file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="446d3-112">Check the `Repository` metadata is present with a comment identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="446d3-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span><span class="sxs-lookup"><span data-stu-id="446d3-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span></span>

<span data-ttu-id="446d3-114">**✔️ VALUTARE** l'uso di SourceLink per aggiungere metadati di controllo del codice sorgente agli assembly e ai pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="446d3-114">**✔️ CONSIDER** using SourceLink to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="446d3-115">È possibile migliorare ulteriormente l'esperienza di debug di uno sviluppatore tramite l'aggiunta di attributi del debugger ai tipi in uso.</span><span class="sxs-lookup"><span data-stu-id="446d3-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
> * <span data-ttu-id="446d3-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> può personalizzare la modalità di visualizzazione di una classe o di un campo nelle finestre delle variabili del debugger.</span><span class="sxs-lookup"><span data-stu-id="446d3-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="446d3-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> indica al debugger di eseguire il codice un'istruzione alla volta anziché eseguire un'istruzione nel codice.</span><span class="sxs-lookup"><span data-stu-id="446d3-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="446d3-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controlla se viene visualizzato un membro nelle finestre delle variabili del debugger.</span><span class="sxs-lookup"><span data-stu-id="446d3-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="446d3-119">**✔️ VALUTARE** l'inclusione dei file di simboli (`*.pdb`) nel pacchetto NuGet principale.</span><span class="sxs-lookup"><span data-stu-id="446d3-119">**✔️ CONSIDER** including symbol files (`*.pdb`) in the NuGet package.</span></span>

> <span data-ttu-id="446d3-120">In genere, i file di simboli vengono pubblicati in un [pacchetto di simboli](./nuget.md#symbol-packages).</span><span class="sxs-lookup"><span data-stu-id="446d3-120">Ordinarily, you'd publish symbol files in a [symbol package](./nuget.md#symbol-packages).</span></span> <span data-ttu-id="446d3-121">Attualmente l'host pubblico principale per i pacchetti di simboli non supporta i file di simboli portatili (`*.pdb`) creati dai progetti in stile SDK e i pacchetti di simboli non sono utili.</span><span class="sxs-lookup"><span data-stu-id="446d3-121">Currently the main public host for symbol packages doesn't support the portable symbol files (`*.pdb`) created by SDK-style projects, and symbol packages aren't useful.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="446d3-122">[Precedente](dependencies.md)
>[Successivo](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="446d3-122">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>
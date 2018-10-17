---
title: Librerie SourceLink e .NET
description: Procedure consigliate per l'uso SourceLink per migliorare il debug per le librerie .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: fa4af47eaa5dd1510640c2bf0ebb2187b56efae0
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49370044"
---
# <a name="sourcelink"></a><span data-ttu-id="42a24-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="42a24-103">SourceLink</span></span>

<span data-ttu-id="42a24-104">SourceLink è una tecnologia che consente il debug del codice sorgente degli assembly .NET da NuGet dagli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="42a24-104">SourceLink is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="42a24-105">SourceLink esegue quando si crea il pacchetto NuGet e incorpora i metadati di controllo di origine all'interno di assembly e il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="42a24-105">SourceLink executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="42a24-106">Gli sviluppatori che scarica il pacchetto e avere SourceLink abilitato in Visual Studio possono eseguirne il relativo codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="42a24-106">Developers who download the package and have SourceLink enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="42a24-107">SourceLink fornisce i metadati di controllo di origine per creare una straordinaria esperienza di debug.</span><span class="sxs-lookup"><span data-stu-id="42a24-107">SourceLink provides source control metadata to create a great debugging experience.</span></span>

## <a name="sourcelink-demo"></a><span data-ttu-id="42a24-108">Demo SourceLink</span><span class="sxs-lookup"><span data-stu-id="42a24-108">SourceLink demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a><span data-ttu-id="42a24-109">Usando SourceLink</span><span class="sxs-lookup"><span data-stu-id="42a24-109">Using SourceLink</span></span>

<span data-ttu-id="42a24-110">Istruzioni per l'uso SourceLink sono reperibile nella [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) repository GitHub.</span><span class="sxs-lookup"><span data-stu-id="42a24-110">Instructions for using SourceLink can be found on the [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="42a24-111">È possibile usare [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) per confermare che i metadati SourceLink sono stato incorporato nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="42a24-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the SourceLink metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="42a24-112">Controllare il `Repository` metadati sono presenti con un identificatore di commento e che si trovano con. dll del ogni destinazione file con estensione pdb.</span><span class="sxs-lookup"><span data-stu-id="42a24-112">Check the `Repository` metadata is present with a comment identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="42a24-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span><span class="sxs-lookup"><span data-stu-id="42a24-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span></span>

<span data-ttu-id="42a24-114">**Provare a ✔️** usando SourceLink per aggiungere metadati di controllo di origine per l'assembly e il pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="42a24-114">**✔️ CONSIDER** using SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

<span data-ttu-id="42a24-115">**Provare a ✔️** inclusi i file PDB nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="42a24-115">**✔️ CONSIDER** including PDB files in the NuGet package.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="42a24-116">[Precedente](./dependencies.md)
[Successivo](./publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="42a24-116">[Previous](./dependencies.md)
[Next](./publish-nuget-package.md)</span></span>

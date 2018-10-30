---
title: Portabilità in .NET Core da .NET Framework
description: Informazioni sul processo di trasferimento e sugli strumenti che possono risultare utili durante il trasferimento di un progetto .NET Framework in .NET Core.
author: cartermp
ms.author: mairaw
ms.date: 10/23/2018
ms.openlocfilehash: 0c0ec3d8ab09e34e8dae24623903ca571f2cca6c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50192772"
---
# <a name="porting-to-net-core-from-net-framework"></a><span data-ttu-id="04310-103">Portabilità in .NET Core da .NET Framework</span><span class="sxs-lookup"><span data-stu-id="04310-103">Porting to .NET Core from .NET Framework</span></span>

<span data-ttu-id="04310-104">Se è disponibile codice per .NET Framework, si potrebbe essere interessati a eseguirlo in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="04310-104">If you've got code running on the .NET Framework, you may be interested in running your code on .NET Core.</span></span>  <span data-ttu-id="04310-105">Questo articolo illustra una panoramica del processo di trasferimento e un elenco degli strumenti che possono risultare utili durante il trasferimento in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="04310-105">This article covers an overview of the porting process and a list of the tools you may find helpful when porting to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="04310-106">Panoramica del processo di trasferimento</span><span class="sxs-lookup"><span data-stu-id="04310-106">Overview of the Porting Process</span></span>

<span data-ttu-id="04310-107">Il processo consigliato per la portabilità fa riferimento alla serie di passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="04310-107">The recommended process for porting follows the following series of steps.</span></span>  <span data-ttu-id="04310-108">Ogni parte del processo è descritta più dettagliatamente in ulteriori articoli.</span><span class="sxs-lookup"><span data-stu-id="04310-108">Each of these parts of the process are covered in more detail in further articles.</span></span>

1. <span data-ttu-id="04310-109">Identificare e spiegare le dipendenze di terze parti.</span><span class="sxs-lookup"><span data-stu-id="04310-109">Identify and account for your third-party dependencies.</span></span>

   <span data-ttu-id="04310-110">Questo passaggio comporterà la comprensione delle dipendenze di terze parti, della dipendenza dell'utente da queste ultime, di come verificare se vengono eseguite anche su .NET Core e dei passaggi da eseguire in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="04310-110">This will involve understanding what your third-party dependencies are, how you depend on them, how to see if they also run on .NET Core, and steps you can take if they don't.</span></span>
   
2. <span data-ttu-id="04310-111">Ridestinare tutti i progetti che si desidera trasferire alla versione più recente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="04310-111">Retarget all projects you wish to port to target the latest version of .NET Framework.</span></span>

   <span data-ttu-id="04310-112">Questo passaggio garantisce che si possano usare le alternative di API per le destinazioni specifiche di .NET Framework nei casi in cui .NET Core non supporta un'API specifica.</span><span class="sxs-lookup"><span data-stu-id="04310-112">This ensures that you can use API alternatives for .NET Framework-specific targets in the cases where .NET Core can't support a particular API.</span></span>
   
3. <span data-ttu-id="04310-113">Usare [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) per analizzare gli assembly e sviluppare un piano per eseguire il trasferimento in base ai risultati ottenuti.</span><span class="sxs-lookup"><span data-stu-id="04310-113">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to analyze your assemblies and develop a plan to port based on its results.</span></span>

   <span data-ttu-id="04310-114">Lo strumento API Portability Analyzer analizza gli assembly compilati e genera un report che mostra un riepilogo a elevato livello di portabilità e un'analisi dettagliata di ogni API in uso non disponibile in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="04310-114">The API Portability Analyzer tool will analyze your compiled assemblies and generate a report which shows a high-level portability summary and a breakdown of each API you're using that isn't available on .NET Core.</span></span>  <span data-ttu-id="04310-115">È possibile usare questo report insieme a un'analisi della base di codici per sviluppare un piano per il trasferimento del codice.</span><span class="sxs-lookup"><span data-stu-id="04310-115">You can use this report alongside an analysis of your codebase to develop a plan for how you'll port your code over.</span></span>
   
4. <span data-ttu-id="04310-116">Trasferire il codice di test.</span><span class="sxs-lookup"><span data-stu-id="04310-116">Port your tests code.</span></span>

   <span data-ttu-id="04310-117">Poiché la portabilità in .NET Core è una modifica di rilievo per la base di codici, è consigliabile effettuare la portabilità dei test in modo da eseguirli durante il trasferimento del codice.</span><span class="sxs-lookup"><span data-stu-id="04310-117">Because porting to .NET Core is such a big change to your codebase, it's highly recommended to get your tests ported so that you can run tests as you port code over.</span></span>  <span data-ttu-id="04310-118">Attualmente MSTest, xUnit e NUnit supportano .NET Core.</span><span class="sxs-lookup"><span data-stu-id="04310-118">MSTest, xUnit, and NUnit all support .NET Core today.</span></span>
   
6. <span data-ttu-id="04310-119">Eseguire il piano di portabilità.</span><span class="sxs-lookup"><span data-stu-id="04310-119">Execute your plan for porting!</span></span>

## <a name="tools-to-help"></a><span data-ttu-id="04310-120">Strumenti utili</span><span class="sxs-lookup"><span data-stu-id="04310-120">Tools to help</span></span>

<span data-ttu-id="04310-121">Di seguito è riportato un breve elenco degli strumenti che possono risultare utili:</span><span class="sxs-lookup"><span data-stu-id="04310-121">Here's a short list of the tools you'll find helpful:</span></span>

* <span data-ttu-id="04310-122">NuGet: [Nuget Client](https://dist.nuget.org/index.html) o [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), gestione di pacchetti Microsoft per le implementazioni di .NET.</span><span class="sxs-lookup"><span data-stu-id="04310-122">NuGet - [Nuget Client](https://dist.nuget.org/index.html) or [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), Microsoft's package manager for .NET implementations.</span></span>
* <span data-ttu-id="04310-123">API Portability Analyzer: [strumento da riga di comando](https://github.com/Microsoft/dotnet-apiport/releases) o [estensione di Visual Studio](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b), una toolchain in grado di generare un report sulla portabilità del codice tra .NET Framework e .NET Core, con un'analisi dettagliata dei problemi basata sugli assembly.</span><span class="sxs-lookup"><span data-stu-id="04310-123">Api Portability Analyzer - [command line tool](https://github.com/Microsoft/dotnet-apiport/releases) or [Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b), a toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core, with an assembly-by-assembly breakdown of issues.</span></span>  <span data-ttu-id="04310-124">Per altre informazioni, vedere [Tooling to help you on the process](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/) (Strumenti utili per il processo).</span><span class="sxs-lookup"><span data-stu-id="04310-124">See [Tooling to help you on the process](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/) for more information.</span></span>
* <span data-ttu-id="04310-125">Reverse Package Search: un [servizio Web utile](https://packagesearch.azurewebsites.net) che consente di eseguire le ricerche in base al tipo e di trovare pacchetti contenenti tale tipo.</span><span class="sxs-lookup"><span data-stu-id="04310-125">Reverse Package Search - A [useful web service](https://packagesearch.azurewebsites.net) that allows you to search for a type and find packages containing that type.</span></span>

## <a name="next-steps"></a><span data-ttu-id="04310-126">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="04310-126">Next steps</span></span>

<span data-ttu-id="04310-127">[Analyzing your third-party dependencies](third-party-deps.md) (Analisi delle dipendenze di terze parti)</span><span class="sxs-lookup"><span data-stu-id="04310-127">[Analyzing your third-party dependencies.](third-party-deps.md)</span></span>
   

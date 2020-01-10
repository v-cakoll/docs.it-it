---
title: Porta da .NET Framework a .NET Core
description: Informazioni sul processo di trasferimento e sugli strumenti che possono risultare utili durante il trasferimento di un progetto .NET Framework in .NET Core.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: b5b010acbccf134afe800aa5bb98a0ae6e9ffa25
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777365"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a><span data-ttu-id="a40ad-103">Panoramica del porting da .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="a40ad-103">Overview of porting from .NET Framework to .NET Core</span></span>

<span data-ttu-id="a40ad-104">È possibile che si disponga di codice attualmente in esecuzione sul .NET Framework che si desidera trasferire a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a40ad-104">You might have code that currently runs on the .NET Framework that you're interested in porting to .NET Core.</span></span> <span data-ttu-id="a40ad-105">Questo articolo include:</span><span class="sxs-lookup"><span data-stu-id="a40ad-105">This article provides:</span></span>

* <span data-ttu-id="a40ad-106">Panoramica del processo di porting.</span><span class="sxs-lookup"><span data-stu-id="a40ad-106">An overview of the porting process.</span></span>
* <span data-ttu-id="a40ad-107">Un elenco di strumenti che possono risultare utili quando si trasferisce il codice a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a40ad-107">A list of tools that you may find helpful when you're porting your code to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="a40ad-108">Panoramica del processo di conversione</span><span class="sxs-lookup"><span data-stu-id="a40ad-108">Overview of the porting process</span></span>

<span data-ttu-id="a40ad-109">Quando si trasferisce il progetto a .NET Core, è consigliabile usare il processo seguente:</span><span class="sxs-lookup"><span data-stu-id="a40ad-109">We recommend you use the following process when porting your project to .NET Core:</span></span>

1. <span data-ttu-id="a40ad-110">Ridestinare tutti i progetti che si desidera trasferire alla destinazione .NET Framework 4.7.2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a40ad-110">Retarget all projects you wish to port to target .NET Framework 4.7.2 or higher.</span></span>

   <span data-ttu-id="a40ad-111">Questo passaggio garantisce che si possano usare le alternative alle API per le destinazioni specifiche di .NET Framework quando .NET Core non supporta un'API specifica.</span><span class="sxs-lookup"><span data-stu-id="a40ad-111">This step ensures that you can use API alternatives for .NET Framework-specific targets when .NET Core doesn't support a particular API.</span></span>

2. <span data-ttu-id="a40ad-112">Usare [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) per analizzare gli assembly e verificare se sono portabili a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a40ad-112">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to analyze your assemblies and see if they're portable to .NET Core.</span></span>

   <span data-ttu-id="a40ad-113">Lo strumento API Portability Analyzer analizza gli assembly compilati e genera un report.</span><span class="sxs-lookup"><span data-stu-id="a40ad-113">The API Portability Analyzer tool analyzes your compiled assemblies and generates a report.</span></span> <span data-ttu-id="a40ad-114">Questo report Mostra un riepilogo della portabilità di alto livello e una suddivisione di ogni API in uso non disponibile in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a40ad-114">This report shows a high-level portability summary and a breakdown of each API you're using that isn't available on NET Core.</span></span>

3. <span data-ttu-id="a40ad-115">Installare l' [analizzatore di API .NET](../../standard/analyzers/api-analyzer.md) nei progetti per identificare le API che generano <xref:System.PlatformNotSupportedException> in alcune piattaforme e altri potenziali problemi di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="a40ad-115">Install the [.NET API analyzer](../../standard/analyzers/api-analyzer.md) into your projects to identify APIs throwing <xref:System.PlatformNotSupportedException> on some platforms and some other potential compatibility issues.</span></span>

   <span data-ttu-id="a40ad-116">Questo strumento è simile a Portability Analyzer, ma invece di analizzare gli elementi che possono essere creati in .NET Core, analizza se si usa un'API in modo da generare la <xref:System.PlatformNotSupportedException> in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a40ad-116">This tool is similar to the portability analyzer, but instead of analyzing if things can build on .NET Core, it analyzes if you're using an API in a way that will throw the <xref:System.PlatformNotSupportedException> at run time.</span></span> <span data-ttu-id="a40ad-117">Sebbene questo non sia comune se si passa da .NET Framework 4.7.2 o versione successiva, è opportuno verificare.</span><span class="sxs-lookup"><span data-stu-id="a40ad-117">Although this isn't common if you're moving from .NET Framework 4.7.2 or higher, it's good to check.</span></span>

4. <span data-ttu-id="a40ad-118">Convertire tutte le dipendenze `packages.config` nel formato [PackageReference](/nuget/consume-packages/package-references-in-project-files) con lo [strumento di conversione in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span><span class="sxs-lookup"><span data-stu-id="a40ad-118">Convert all of your `packages.config` dependencies to the [PackageReference](/nuget/consume-packages/package-references-in-project-files) format with the [conversion tool in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span></span>

   <span data-ttu-id="a40ad-119">Questo passaggio prevede la conversione delle dipendenze dal formato legacy `packages.config`.</span><span class="sxs-lookup"><span data-stu-id="a40ad-119">This step involves converting your dependencies from the legacy `packages.config` format.</span></span> <span data-ttu-id="a40ad-120">`packages.config` non funziona in .NET Core, quindi questa conversione è necessaria se sono presenti dipendenze del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a40ad-120">`packages.config` doesn't work on .NET Core, so this conversion is required if you have package dependencies.</span></span>

5. <span data-ttu-id="a40ad-121">Creare nuovi progetti per .NET Core e copiare i file di origine oppure provare a convertire il file di progetto esistente con uno strumento.</span><span class="sxs-lookup"><span data-stu-id="a40ad-121">Create new projects for .NET Core and copy over source files, or attempt to convert your existing project file with a tool.</span></span>

   <span data-ttu-id="a40ad-122">.NET Core usa un [formato di file di progetto](../tools/csproj.md) semplificato (e diverso) rispetto a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a40ad-122">.NET Core uses a simplified (and different) [project file format](../tools/csproj.md) than .NET Framework.</span></span> <span data-ttu-id="a40ad-123">Per continuare è necessario convertire i file di progetto in questo formato.</span><span class="sxs-lookup"><span data-stu-id="a40ad-123">You'll need to convert your project files into this format to continue.</span></span>

6. <span data-ttu-id="a40ad-124">Trasferire il codice di test.</span><span class="sxs-lookup"><span data-stu-id="a40ad-124">Port your test code.</span></span>

   <span data-ttu-id="a40ad-125">Poiché la portabilità in .NET Core è una modifica significativa nella codebase, è consigliabile trasferire i progetti di test in modo da poter eseguire i test quando si trasferisce il codice.</span><span class="sxs-lookup"><span data-stu-id="a40ad-125">Because porting to .NET Core is such a significant change to your codebase, it's highly recommended to port your test projects so that you can run tests as you port your code over.</span></span> <span data-ttu-id="a40ad-126">MSTest, xUnit e NUnit funzionano in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a40ad-126">MSTest, xUnit, and NUnit all work on .NET Core.</span></span>

<span data-ttu-id="a40ad-127">Inoltre, è possibile tentare di trasferire le soluzioni più piccole o i singoli progetti in un'unica operazione al formato di file di progetto .NET Core con lo strumento [DotNet try-Convert](https://github.com/dotnet/try-convert) .</span><span class="sxs-lookup"><span data-stu-id="a40ad-127">Additionally, you can attempt to port smaller solutions or individual projects in one operation to the .NET Core project file format with the [dotnet try-convert](https://github.com/dotnet/try-convert) tool.</span></span> <span data-ttu-id="a40ad-128">`dotnet try-convert` non è garantito che funzioni per tutti i progetti e potrebbe causare modifiche minime al comportamento da cui dipende.</span><span class="sxs-lookup"><span data-stu-id="a40ad-128">`dotnet try-convert` is not guaranteed to work for all your projects, and it may cause subtle changes in behavior that you depended on.</span></span> <span data-ttu-id="a40ad-129">Utilizzarlo come _punto di partenza_ per automatizzare gli elementi di base che possono essere automatizzati.</span><span class="sxs-lookup"><span data-stu-id="a40ad-129">Use it as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="a40ad-130">Non si tratta di una soluzione garantita per la migrazione di un progetto.</span><span class="sxs-lookup"><span data-stu-id="a40ad-130">It isn't a guaranteed solution to migrating a project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a40ad-131">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a40ad-131">Next steps</span></span>

>[!div class="nextstepaction"]
>[<span data-ttu-id="a40ad-132">Tecnologie non disponibili in .NET Core</span><span class="sxs-lookup"><span data-stu-id="a40ad-132">Unavailable technologies on .NET Core</span></span>](net-framework-tech-unavailable.md)

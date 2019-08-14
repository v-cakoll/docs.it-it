---
title: Panoramica degli strumenti di diagnostica -.NET Core
description: Panoramica degli strumenti e delle tecniche disponibili per la diagnosi delle applicazioni .NET Core.
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.topic: overview
ms.openlocfilehash: f107d15fa5584bb5a4834b5f11f1096bec7eb749
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974149"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="f4866-103">Quali strumenti di diagnostica sono disponibili in .NET Core?</span><span class="sxs-lookup"><span data-stu-id="f4866-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="f4866-104">Il software non sempre si comporta come previsto, ma .NET Core offre strumenti e API utili per diagnosticare questi problemi in modo rapido ed efficace.</span><span class="sxs-lookup"><span data-stu-id="f4866-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="f4866-105">Questo articolo consente di trovare i vari strumenti necessari.</span><span class="sxs-lookup"><span data-stu-id="f4866-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggersmanaged-debuggersmd"></a>[<span data-ttu-id="f4866-106">Debugger gestiti</span><span class="sxs-lookup"><span data-stu-id="f4866-106">Managed debuggers</span></span>](managed-debuggers.md)
<span data-ttu-id="f4866-107">I debugger gestiti consentono di interagire con il programma.</span><span class="sxs-lookup"><span data-stu-id="f4866-107">Managed debuggers allow you to interact with your program.</span></span> <span data-ttu-id="f4866-108">La sospensione, l'esecuzione incrementale, l'analisi e la ripresa forniscono informazioni approfondite sul comportamento del codice.</span><span class="sxs-lookup"><span data-stu-id="f4866-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="f4866-109">Un debugger è la prima scelta per la diagnosi dei problemi funzionali che possono essere facilmente riprodotti.</span><span class="sxs-lookup"><span data-stu-id="f4866-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracinglogging-tracingmd"></a>[<span data-ttu-id="f4866-110">Registrazione e traccia</span><span class="sxs-lookup"><span data-stu-id="f4866-110">Logging and tracing</span></span>](logging-tracing.md)
<span data-ttu-id="f4866-111">La registrazione e la traccia sono tecniche correlate.</span><span class="sxs-lookup"><span data-stu-id="f4866-111">Logging and tracing are related techniques.</span></span> <span data-ttu-id="f4866-112">Si riferiscono all'instrumentazione del codice per creare file di log.</span><span class="sxs-lookup"><span data-stu-id="f4866-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="f4866-113">I file registrano i dettagli delle operazioni eseguite da un programma.</span><span class="sxs-lookup"><span data-stu-id="f4866-113">The files record the details of what a program does.</span></span> <span data-ttu-id="f4866-114">Questi dettagli possono essere usati per diagnosticare i problemi più complessi.</span><span class="sxs-lookup"><span data-stu-id="f4866-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="f4866-115">In combinazione con i timestamp, queste tecniche sono utili anche per le analisi delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f4866-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testingtestingindexmd"></a>[<span data-ttu-id="f4866-116">Testing unità</span><span class="sxs-lookup"><span data-stu-id="f4866-116">Unit testing</span></span>](../testing/index.md)
<span data-ttu-id="f4866-117">Il testing unità è un componente chiave dell'integrazione e distribuzione continue di software di alta qualità.</span><span class="sxs-lookup"><span data-stu-id="f4866-117">Unit testing is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="f4866-118">Gli unit test sono progettati per offrire avvisi in anticipo in caso di problemi funzionali.</span><span class="sxs-lookup"><span data-stu-id="f4866-118">Unit tests are designed to give you an early warning when you break something.</span></span>

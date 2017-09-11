---
title: Uso di .NET Compiler SDK - Guida a C#
description: Informazioni sulle API Roslyn per la creazione di strumenti di diagnostica automatica e correzioni del codice
keywords: .NET, .NET Core, C#, Roslyn
ms.date: 06/25/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: abed9e00-2ddc-468e-9cca-d033bd6a7e36
redirect_url: /dotnet/csharp/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b227d67fd5431da328e1686fd9afc6a3b9db035e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="-using-the-net-compiler-sdk"></a><span data-ttu-id="32d3e-104">🔧 Uso di .NET Compiler SDK | Guida a C#</span><span class="sxs-lookup"><span data-stu-id="32d3e-104">🔧 Using the .NET Compiler SDK</span></span>

> <span data-ttu-id="32d3e-105">**Nota**</span><span class="sxs-lookup"><span data-stu-id="32d3e-105">**Note**</span></span>
> 
> <span data-ttu-id="32d3e-106">Questo argomento non è ancora stato scritto.</span><span class="sxs-lookup"><span data-stu-id="32d3e-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="32d3e-107">Microsoft invita gli utenti a inviare commenti e suggerimenti per aiutare a definire l'ambito e l'approccio da adottare.</span><span class="sxs-lookup"><span data-stu-id="32d3e-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="32d3e-108">È possibile tenere traccia dello stato e inviare il proprio input su questo [argomento](https://github.com/dotnet/docs/issues/972) in GitHub.</span><span class="sxs-lookup"><span data-stu-id="32d3e-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/972) at GitHub.</span></span>
> 
> <span data-ttu-id="32d3e-109">Per rivedere le prime bozze e le linee generali dell'argomento, inviare una nota con le proprie informazioni di contatto nell'apposita pagina.</span><span class="sxs-lookup"><span data-stu-id="32d3e-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="32d3e-110">Per altre informazioni su come offrire il proprio contributo, visitare questa pagina di [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="32d3e-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>

<span data-ttu-id="32d3e-111">Questo è un meta-argomento per un'intera sezione.</span><span class="sxs-lookup"><span data-stu-id="32d3e-111">This is a meta-topic for an entire section.</span></span> <span data-ttu-id="32d3e-112">Le aree da trattare includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="32d3e-112">Areas that need to be covered here include:</span></span> 
* <span data-ttu-id="32d3e-113">Introduzione</span><span class="sxs-lookup"><span data-stu-id="32d3e-113">Getting Started</span></span>
* <span data-ttu-id="32d3e-114">Esempi ed esercitazioni</span><span class="sxs-lookup"><span data-stu-id="32d3e-114">Samples and tutorials</span></span>
* <span data-ttu-id="32d3e-115">Contenuto concettuale</span><span class="sxs-lookup"><span data-stu-id="32d3e-115">conceptual content</span></span>
* <span data-ttu-id="32d3e-116">Modello generale delle API</span><span class="sxs-lookup"><span data-stu-id="32d3e-116">overall model of the APIs</span></span>
* <span data-ttu-id="32d3e-117">Collegamenti agli esempi nel repository [roslyn-analizzatori](http://github.com/dotnet/roslyn-analyzers)</span><span class="sxs-lookup"><span data-stu-id="32d3e-117">links to samples on the [roslyn-analyzers](http://github.com/dotnet/roslyn-analyzers) repository</span></span>
* <span data-ttu-id="32d3e-118">Collegamenti ad altri contenuti di riferimento</span><span class="sxs-lookup"><span data-stu-id="32d3e-118">links to other reference content</span></span>


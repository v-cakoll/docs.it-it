---
title: Programmazione simultanea - Guida a C#
description: "Informazioni sulle tecniche per eseguire attività (basate su CPU) in parallelo"
keywords: C#, asincrono, basato su CPU, basato su rete
ms.date: 08/24/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0f8b42de-858a-44a3-87d9-998211f26377
redirect_url: /dotnet/csharp/tutorials/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 00cf3b04178ca48c9f8f35eb16bc216389e6b272
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="-concurrent-programming"></a><span data-ttu-id="799ee-104">🔧 Programmazione simultanea</span><span class="sxs-lookup"><span data-stu-id="799ee-104">🔧 Concurrent Programming</span></span>

> <span data-ttu-id="799ee-105">**Nota**</span><span class="sxs-lookup"><span data-stu-id="799ee-105">**Note**</span></span>
> 
> <span data-ttu-id="799ee-106">Questo argomento non è ancora stato scritto.</span><span class="sxs-lookup"><span data-stu-id="799ee-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="799ee-107">Microsoft invita gli utenti a inviare commenti e suggerimenti per aiutare a definire l'ambito e l'approccio da adottare.</span><span class="sxs-lookup"><span data-stu-id="799ee-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="799ee-108">È possibile tenere traccia dello stato e inviare il proprio input su questo [argomento](https://github.com/dotnet/docs/issues/953) in GitHub.</span><span class="sxs-lookup"><span data-stu-id="799ee-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/953) at GitHub.</span></span>
> 
> <span data-ttu-id="799ee-109">Per rivedere le prime bozze e le linee generali dell'argomento, inviare una nota con le proprie informazioni di contatto nell'apposita pagina.</span><span class="sxs-lookup"><span data-stu-id="799ee-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="799ee-110">Per altre informazioni su come offrire il proprio contributo, visitare questa pagina di [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="799ee-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>


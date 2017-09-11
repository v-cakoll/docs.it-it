---
title: Programmazione asincrona del server - Guida a C#
description: Informazioni sulle tecniche per la ripartizione di carichi di lavoro server usando tecniche di programmazione asincrone
keywords: C#, asincrono, basato su CPU, basato su rete
ms.date: 08/24/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 7402b29b-1093-456d-be4c-f60ecb8926bb
redirect_url: /dotnet/csharp/tutorials/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 390d0eb2c8416165984ffe6c80ed6977e61a2845
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="-asynchronous-server-programming"></a><span data-ttu-id="baae8-104">🔧 Programmazione asincrona del server</span><span class="sxs-lookup"><span data-stu-id="baae8-104">🔧 Asynchronous Server Programming</span></span>

> <span data-ttu-id="baae8-105">**Nota**</span><span class="sxs-lookup"><span data-stu-id="baae8-105">**Note**</span></span>
> 
> <span data-ttu-id="baae8-106">Questo argomento non è ancora stato scritto.</span><span class="sxs-lookup"><span data-stu-id="baae8-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="baae8-107">Microsoft invita gli utenti a inviare commenti e suggerimenti per aiutare a definire l'ambito e l'approccio da adottare.</span><span class="sxs-lookup"><span data-stu-id="baae8-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="baae8-108">È possibile tenere traccia dello stato e inviare il proprio input su questo [argomento](https://github.com/dotnet/docs/issues/952) in GitHub.</span><span class="sxs-lookup"><span data-stu-id="baae8-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/952) at GitHub.</span></span>
> 
> <span data-ttu-id="baae8-109">Per rivedere le prime bozze e le linee generali dell'argomento, inviare una nota con le proprie informazioni di contatto nell'apposita pagina.</span><span class="sxs-lookup"><span data-stu-id="baae8-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="baae8-110">Per altre informazioni su come offrire il proprio contributo, visitare questa pagina di [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="baae8-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>


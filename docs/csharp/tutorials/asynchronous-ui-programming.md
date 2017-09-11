---
title: Programmazione asincrona dell'interfaccia utente - Guida a C#
description: "Informazioni sulle tecniche per mantenere reattiva l'interfaccia utente mentre è in corso un processo di programmazione tramite operazioni asincrone"
keywords: C#, UWP, XAML
ms.date: 08/24/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 7402b29b-1093-456d-be4c-f60ecb8926bb
redirect_url: /dotnet/csharp/tutorials/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f868c798f94acfb1ef468ea91f4245520c4e14b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="-asynchronous-ui-programming"></a><span data-ttu-id="a424e-104">🔧 Programmazione asincrona dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="a424e-104">🔧 Asynchronous UI Programming</span></span>

> <span data-ttu-id="a424e-105">**Nota**</span><span class="sxs-lookup"><span data-stu-id="a424e-105">**Note**</span></span>
> 
> <span data-ttu-id="a424e-106">Questo argomento non è ancora stato scritto.</span><span class="sxs-lookup"><span data-stu-id="a424e-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="a424e-107">Microsoft invita gli utenti a inviare commenti e suggerimenti per aiutare a definire l'ambito e l'approccio da adottare.</span><span class="sxs-lookup"><span data-stu-id="a424e-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="a424e-108">È possibile tenere traccia dello stato e inviare il proprio input su questo [argomento](https://github.com/dotnet/docs/issues/951) in GitHub.</span><span class="sxs-lookup"><span data-stu-id="a424e-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/951) at GitHub.</span></span>
> 
> <span data-ttu-id="a424e-109">Per rivedere le prime bozze e le linee generali dell'argomento, inviare una nota con le proprie informazioni di contatto nell'apposita pagina.</span><span class="sxs-lookup"><span data-stu-id="a424e-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="a424e-110">Per altre informazioni su come offrire il proprio contributo, visitare questa pagina di [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="a424e-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>


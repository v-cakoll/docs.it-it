---
title: Linee guida per le librerie .NET open source
description: Procedure consigliate per gli sviluppatori nella creazione di librerie .NET di qualità.
ms.date: 10/17/2018
ms.openlocfilehash: 4c76dfae6ffc39df7f15381be64e33657067d79d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731432"
---
# <a name="open-source-library-guidance"></a><span data-ttu-id="7f724-103">Linee guida per le librerie open source</span><span class="sxs-lookup"><span data-stu-id="7f724-103">Open-source library guidance</span></span>

<span data-ttu-id="7f724-104">Questo materiale sussidiario offre indicazioni agli sviluppatori per la creazione di librerie .NET di qualità.</span><span class="sxs-lookup"><span data-stu-id="7f724-104">This guidance provides recommendations for developers to create high-quality .NET libraries.</span></span> <span data-ttu-id="7f724-105">Questa documentazione è incentrata sul *cosa* e sul *perché* compilare una libreria .NET, non sul *come* eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="7f724-105">This documentation focuses on the *what* and the *why* when building a .NET library, not the *how*.</span></span>

<span data-ttu-id="7f724-106">Aspetti delle librerie .NET open source di qualità:</span><span class="sxs-lookup"><span data-stu-id="7f724-106">Aspects of high-quality open-source .NET libraries:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="7f724-107">**Inclusive**: le librerie .NET di qualità in genere supportano molti linguaggi di programmazione, piattaforme e applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7f724-107">**Inclusive** - Good .NET libraries strive to support many platforms, programming languages, and applications.</span></span>
> * <span data-ttu-id="7f724-108">**Stabili**: le librerie .NET di qualità coesistono nell'ecosistema .NET e vengono eseguite in applicazioni compilate con molte librerie.</span><span class="sxs-lookup"><span data-stu-id="7f724-108">**Stable** - Good .NET libraries coexist in the .NET ecosystem, running in applications built with many libraries.</span></span>
> * <span data-ttu-id="7f724-109">**Progettate per l'evoluzione**: le librerie .NET di qualità devono migliorare ed evolvere nel tempo, supportando gli utenti esistenti.</span><span class="sxs-lookup"><span data-stu-id="7f724-109">**Designed to evolve** - .NET libraries should improve and evolve over time, while supporting existing users.</span></span>
> * <span data-ttu-id="7f724-110">**Sottoponibili a debug**: le librerie .NET devono usare gli strumenti più aggiornati, in modo da creare un'esperienza di debug ottimale per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7f724-110">**Debuggable** - .NET libraries should use the latest tools to create a great debugging experience for users.</span></span>
> * <span data-ttu-id="7f724-111">**Attendibili**: le librerie .NET devono risultare attendibili per gli sviluppatori grazie alla pubblicazione in NuGet con le procedure di sicurezza consigliate.</span><span class="sxs-lookup"><span data-stu-id="7f724-111">**Trusted** - .NET libraries have developers' trust by publishing to NuGet using security best practices.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7f724-112">Introduzione</span><span class="sxs-lookup"><span data-stu-id="7f724-112">Get Started</span></span>](./get-started.md)

## <a name="types-of-recommendations"></a><span data-ttu-id="7f724-113">Tipi di suggerimenti</span><span class="sxs-lookup"><span data-stu-id="7f724-113">Types of recommendations</span></span>

<span data-ttu-id="7f724-114">Ogni articolo presenta quattro tipi di suggerimenti: **Da fare**, **Da considerare**, **Da evitare** e **Da non fare**.</span><span class="sxs-lookup"><span data-stu-id="7f724-114">Each article presents four types of recommendations: **Do**, **Consider**, **Avoid**, and **Do not**.</span></span> <span data-ttu-id="7f724-115">Il tipo di suggerimento indica quanto è importante che venga osservato.</span><span class="sxs-lookup"><span data-stu-id="7f724-115">The type of recommendation indicates how strongly it should be followed.</span></span>

<span data-ttu-id="7f724-116">È opportuno seguire quasi sempre un suggerimento di tipo **Da fare**.</span><span class="sxs-lookup"><span data-stu-id="7f724-116">You should almost always follow a **Do** recommendation.</span></span> <span data-ttu-id="7f724-117">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="7f724-117">For example:</span></span>

<span data-ttu-id="7f724-118">✔️ distribuire la libreria usando un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="7f724-118">✔️ DO distribute your library using a NuGet package.</span></span>

<span data-ttu-id="7f724-119">In genere è utile osservare le indicazioni di tipo **Da considerare**, ma esistono eccezioni giustificate alla regola e il fatto di non osservarla non deve rappresentare un problema:</span><span class="sxs-lookup"><span data-stu-id="7f724-119">On the other hand, **Consider** recommendations should generally be followed, but there are legitimate exceptions to the rule and you shouldn't feel bad about not following the guidance:</span></span>

<span data-ttu-id="7f724-120">✔️ CONSIDERARE l'uso di [SemVer 2.0.0](https://semver.org/) per la versione del pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="7f724-120">✔️ CONSIDER using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="7f724-121">I suggerimenti di tipo **Da evitare** si riferiscono a operazioni in genere non consigliabili, ma che talvolta possono avere un'utilità:</span><span class="sxs-lookup"><span data-stu-id="7f724-121">**Avoid** recommendations mention things that are generally not a good idea, but breaking the rule sometimes makes sense:</span></span>

<span data-ttu-id="7f724-122">❌ evitare i riferimenti ai pacchetti NuGet che richiedono una versione esatta.</span><span class="sxs-lookup"><span data-stu-id="7f724-122">❌ AVOID NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="7f724-123">E infine, i suggerimenti di tipo **Da non fare** indicano operazioni che quasi sempre è necessario evitare:</span><span class="sxs-lookup"><span data-stu-id="7f724-123">And finally, **Do not** recommendations indicate something you should almost never do:</span></span>

<span data-ttu-id="7f724-124">❌ non pubblicare versioni con nome sicuro e senza nome sicuro della libreria.</span><span class="sxs-lookup"><span data-stu-id="7f724-124">❌ DO NOT publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="7f724-125">Ad esempio, `Contoso.Api` e `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="7f724-125">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="7f724-126">avanti</span><span class="sxs-lookup"><span data-stu-id="7f724-126">Next</span></span>](get-started.md)

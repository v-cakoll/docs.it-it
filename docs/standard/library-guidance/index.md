---
title: Linee guida per le librerie open source
description: Procedure consigliate per gli sviluppatori nella creazione di librerie .NET di qualità.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 50fb745f7eb65abcaca76cebaf9991c48f559e59
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374901"
---
# <a name="open-source-library-guidance"></a><span data-ttu-id="f379b-103">Linee guida per le librerie open source</span><span class="sxs-lookup"><span data-stu-id="f379b-103">Open-source library guidance</span></span>

<span data-ttu-id="f379b-104">Questo materiale sussidiario offre indicazioni agli sviluppatori per la creazione di librerie .NET di qualità.</span><span class="sxs-lookup"><span data-stu-id="f379b-104">This guidance provides recommendations for developers to create high-quality .NET libraries.</span></span> <span data-ttu-id="f379b-105">Questa documentazione è incentrata sul *cosa* e sul *perché* compilare una libreria .NET, non sul *come* eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="f379b-105">This documentation focuses on the *what* and the *why* when building a .NET library, not the *how*.</span></span>

<span data-ttu-id="f379b-106">Aspetti delle librerie .NET open source di qualità:</span><span class="sxs-lookup"><span data-stu-id="f379b-106">Aspects of high-quality open-source .NET libraries:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="f379b-107">**Inclusive**: le librerie .NET di qualità in genere supportano varie piattaforme e applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f379b-107">**Inclusive** - Good .NET libraries strive to support many platforms and applications.</span></span>
> * <span data-ttu-id="f379b-108">**Stabili**: le librerie .NET di qualità coesistono nell'ecosistema .NET e vengono eseguite in applicazioni compilate con molte librerie.</span><span class="sxs-lookup"><span data-stu-id="f379b-108">**Stable** - Good .NET libraries coexist in the .NET ecosystem, running in applications built with many libraries.</span></span>
> * <span data-ttu-id="f379b-109">**Progettate per l'evoluzione**: le librerie .NET di qualità devono migliorare ed evolvere nel tempo, supportando gli utenti esistenti.</span><span class="sxs-lookup"><span data-stu-id="f379b-109">**Designed to evolve** - .NET libraries should improve and evolve over time, while supporting existing users.</span></span>
> * <span data-ttu-id="f379b-110">**Sottoponibili a debug**: le librerie .NET devono usare gli strumenti più aggiornati, in modo da creare un'esperienza di debug ottimale per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f379b-110">**Debuggable** - .NET libraries should use the latest tools to create a great debugging experience for users.</span></span>
> * <span data-ttu-id="f379b-111">**Attendibili**: le librerie .NET devono risultare attendibili per gli sviluppatori grazie alla pubblicazione in NuGet con le procedure di sicurezza consigliate.</span><span class="sxs-lookup"><span data-stu-id="f379b-111">**Trusted** - .NET libraries have developers' trust by publishing to NuGet using security best practices.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f379b-112">Introduzione</span><span class="sxs-lookup"><span data-stu-id="f379b-112">Get Started</span></span>](./get-started.md)

## <a name="recommendations"></a><span data-ttu-id="f379b-113">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="f379b-113">Recommendations</span></span>

<span data-ttu-id="f379b-114">Ogni articolo include un elenco di indicazioni per la libreria .NET, con le notazioni **Da fare**, **Da considerare**, **Da evitare** e **Da non fare**.</span><span class="sxs-lookup"><span data-stu-id="f379b-114">With each article, there is a list of recommendations for your .NET library using **Do**, **Consider**, **Avoid**, and **Do not**.</span></span> <span data-ttu-id="f379b-115">La formulazione di ogni indicazione indica quanto è importante che venga osservata.</span><span class="sxs-lookup"><span data-stu-id="f379b-115">The wording of each recommendation indicates how strongly it should be followed.</span></span>

<span data-ttu-id="f379b-116">Un'indicazione di tipo **Da fare** va seguita nella maggior parte dei casi:</span><span class="sxs-lookup"><span data-stu-id="f379b-116">A **Do** recommendation is one that should almost always be followed:</span></span>

<span data-ttu-id="f379b-117">**✔️ DA FARE** Distribuire la libreria usando un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="f379b-117">**✔️ DO** distribute your library using a NuGet package.</span></span>

<span data-ttu-id="f379b-118">In genere è utile osservare le indicazioni di tipo **Da considerare**, ma esistono eccezioni giustificate alla regola e il fatto di non osservarla non deve rappresentare un problema:</span><span class="sxs-lookup"><span data-stu-id="f379b-118">On the other hand, **Consider** recommendations should generally be followed, but there are legitimate exceptions to the rule and you shouldn't feel bad about not following the guidance:</span></span>

<span data-ttu-id="f379b-119">**✔️ DA CONSIDERARE** Usare [SemVer 2.0.0](https://semver.org/) per la gestione versioni del pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="f379b-119">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="f379b-120">Le indicazioni di tipo **Da evitare** riguardano operazioni in genere non consigliabili, ma che talvolta possono avere un'utilità:</span><span class="sxs-lookup"><span data-stu-id="f379b-120">**Avoid** recommendations are things that are generally not a good idea, but breaking the rule sometimes makes sense:</span></span>

<span data-ttu-id="f379b-121">**❌ DA EVITARE** Riferimenti ai pacchetti NuGet che richiedono una versione esatta.</span><span class="sxs-lookup"><span data-stu-id="f379b-121">**❌ AVOID** NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="f379b-122">Infine **Da non fare** indica un'azione da evitare nella maggior parte dei casi:</span><span class="sxs-lookup"><span data-stu-id="f379b-122">And finally, **do not** indicates something you should almost never do:</span></span>

<span data-ttu-id="f379b-123">**❌ DA NON FARE** Pubblicare versioni con nome sicuro e non sicuro della stessa libreria.</span><span class="sxs-lookup"><span data-stu-id="f379b-123">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="f379b-124">Ad esempio, `Contoso.Api` e `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="f379b-124">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="f379b-125">avanti</span><span class="sxs-lookup"><span data-stu-id="f379b-125">Next</span></span>](./get-started.md)

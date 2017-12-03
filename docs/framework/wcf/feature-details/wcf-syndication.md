---
title: Diffusione WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: syndication [WCF]
ms.assetid: ebf80384-0fc9-4919-a1e8-23ca2a13e300
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 14f2aa18b1fba92f5559b463d90dcfb5b34e2a3f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-syndication"></a><span data-ttu-id="39bd6-102">Diffusione WCF</span><span class="sxs-lookup"><span data-stu-id="39bd6-102">WCF Syndication</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="39bd6-103"> offre supporto per usare in modo semplice feed di diffusione in Atom, RSS o in altri formati personalizzati, in modo da leggerli e crearli, nonché esporli in un endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="39bd6-103"> provides support to easily work with syndication feeds in Atom, RSS or other custom formats, which allows you to read and create them as well as expose them on a service endpoint.</span></span> <span data-ttu-id="39bd6-104">Negli argomenti di questa sezione viene descritto dettagliatamente tale modello di programmazione per la diffusione.</span><span class="sxs-lookup"><span data-stu-id="39bd6-104">The topics in this section describe this programming model for syndication in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="39bd6-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="39bd6-105">In This Section</span></span>  
 [<span data-ttu-id="39bd6-106">Panoramica sulla diffusione WCF</span><span class="sxs-lookup"><span data-stu-id="39bd6-106">WCF Syndication Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 <span data-ttu-id="39bd6-107">Viene fornita una panoramica sul supporto della diffusione fornito da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39bd6-107">Provides an overview of syndication support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="39bd6-108">Architettura di diffusione</span><span class="sxs-lookup"><span data-stu-id="39bd6-108">Architecture of Syndication</span></span>](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)  
 <span data-ttu-id="39bd6-109">Vengono descritte le classi nel modello a oggetti e l'estensibilità della diffusione.</span><span class="sxs-lookup"><span data-stu-id="39bd6-109">Describes the classes in the object model and the extensibility of syndication.</span></span>  
  
 [<span data-ttu-id="39bd6-110">Mapping tra il modello a oggetti di diffusione WCF ad Atom e RSS</span><span class="sxs-lookup"><span data-stu-id="39bd6-110">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 <span data-ttu-id="39bd6-111">Vengono descritte la modalità di rappresentazione dei feed all'interno del modello a oggetti di diffusione WCF e la modalità di conversione degli stessi in feed RSS e Atom.</span><span class="sxs-lookup"><span data-stu-id="39bd6-111">Describes how feeds are represented within the WCF Syndication Object Model and how they are converted to RSS and Atom feeds.</span></span>  
  
 [<span data-ttu-id="39bd6-112">Procedura: creare un Feed RSS di base</span><span class="sxs-lookup"><span data-stu-id="39bd6-112">How to: Create a Basic RSS Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-rss-feed.md)  
 <span data-ttu-id="39bd6-113">Viene illustrato come creare un servizio che rende disponibile un feed RSS di base.</span><span class="sxs-lookup"><span data-stu-id="39bd6-113">Shows how to create a service that makes a basic RSS feed available.</span></span>  
  
 [<span data-ttu-id="39bd6-114">Procedura: creare un Feed Atom di base</span><span class="sxs-lookup"><span data-stu-id="39bd6-114">How to: Create a Basic Atom Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-atom-feed.md)  
 <span data-ttu-id="39bd6-115">Viene illustrato come creare un servizio che rende disponibile un feed ATOM di base.</span><span class="sxs-lookup"><span data-stu-id="39bd6-115">Shows how to create a service that makes a basic ATOM feed available.</span></span>  
  
 [<span data-ttu-id="39bd6-116">Procedura: esporre un Feed come Atom e RSS</span><span class="sxs-lookup"><span data-stu-id="39bd6-116">How to: Expose a Feed as Both Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-feed-as-both-atom-and-rss.md)  
 <span data-ttu-id="39bd6-117">Viene illustrato come creare un servizio che rende lo stesso feed disponibile come ATOM e RSS.</span><span class="sxs-lookup"><span data-stu-id="39bd6-117">Shows how to create a service that makes the same feed available with ATOM and RSS.</span></span>  
  
 [<span data-ttu-id="39bd6-118">Estendibilità della diffusione</span><span class="sxs-lookup"><span data-stu-id="39bd6-118">Syndication Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md)  
 <span data-ttu-id="39bd6-119">Vengono illustrati i metodi per l'aggiunta di elementi e attributi personalizzati a un feed di diffusione.</span><span class="sxs-lookup"><span data-stu-id="39bd6-119">Describes the methods of adding custom elements and attributes to a syndication feed.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="39bd6-120">Riferimento</span><span class="sxs-lookup"><span data-stu-id="39bd6-120">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="39bd6-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="39bd6-121">Related Sections</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39bd6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39bd6-122">See Also</span></span>  
 [<span data-ttu-id="39bd6-123">Modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="39bd6-123">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="39bd6-124">Attendibilità parziale</span><span class="sxs-lookup"><span data-stu-id="39bd6-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)

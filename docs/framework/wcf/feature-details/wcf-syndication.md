---
title: Diffusione WCF
ms.date: 03/30/2017
helpviewer_keywords:
- syndication [WCF]
ms.assetid: ebf80384-0fc9-4919-a1e8-23ca2a13e300
ms.openlocfilehash: 677e8a4b00b36c2f11b27eb65d57be8abf75d6d2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600646"
---
# <a name="wcf-syndication"></a><span data-ttu-id="28b5a-102">Diffusione WCF</span><span class="sxs-lookup"><span data-stu-id="28b5a-102">WCF Syndication</span></span>
<span data-ttu-id="28b5a-103">Windows Communication Foundation (WCF) fornisce il supporto per usare facilmente i feed di diffusione in Atom, RSS o in altri formati personalizzati, che consentono di leggerli e crearli, nonché di esporli in un endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="28b5a-103">Windows Communication Foundation (WCF) provides support to easily work with syndication feeds in Atom, RSS or other custom formats, which allows you to read and create them as well as expose them on a service endpoint.</span></span> <span data-ttu-id="28b5a-104">Negli argomenti di questa sezione viene descritto dettagliatamente tale modello di programmazione per la diffusione.</span><span class="sxs-lookup"><span data-stu-id="28b5a-104">The topics in this section describe this programming model for syndication in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="28b5a-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="28b5a-105">In This Section</span></span>  
 [<span data-ttu-id="28b5a-106">Panoramica della diffusione WCF</span><span class="sxs-lookup"><span data-stu-id="28b5a-106">WCF Syndication Overview</span></span>](wcf-syndication-overview.md)  
 <span data-ttu-id="28b5a-107">Viene fornita una panoramica del supporto della diffusione fornito da WCF.</span><span class="sxs-lookup"><span data-stu-id="28b5a-107">Provides an overview of syndication support provided by WCF.</span></span>  
  
 [<span data-ttu-id="28b5a-108">Architettura di diffusione</span><span class="sxs-lookup"><span data-stu-id="28b5a-108">Architecture of Syndication</span></span>](architecture-of-syndication.md)  
 <span data-ttu-id="28b5a-109">Vengono descritte le classi nel modello a oggetti e l'estensibilità della diffusione.</span><span class="sxs-lookup"><span data-stu-id="28b5a-109">Describes the classes in the object model and the extensibility of syndication.</span></span>  
  
 [<span data-ttu-id="28b5a-110">Modalità di mapping del modello a oggetti di diffusione WCF ad Atom e RSS</span><span class="sxs-lookup"><span data-stu-id="28b5a-110">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>](how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 <span data-ttu-id="28b5a-111">Vengono descritte la modalità di rappresentazione dei feed all'interno del modello a oggetti di diffusione WCF e la modalità di conversione degli stessi in feed RSS e Atom.</span><span class="sxs-lookup"><span data-stu-id="28b5a-111">Describes how feeds are represented within the WCF Syndication Object Model and how they are converted to RSS and Atom feeds.</span></span>  
  
 [<span data-ttu-id="28b5a-112">Procedura: creare un feed RSS di base</span><span class="sxs-lookup"><span data-stu-id="28b5a-112">How to: Create a Basic RSS Feed</span></span>](how-to-create-a-basic-rss-feed.md)  
 <span data-ttu-id="28b5a-113">Viene illustrato come creare un servizio che rende disponibile un feed RSS di base.</span><span class="sxs-lookup"><span data-stu-id="28b5a-113">Shows how to create a service that makes a basic RSS feed available.</span></span>  
  
 [<span data-ttu-id="28b5a-114">Procedura: creare un feed Atom di base</span><span class="sxs-lookup"><span data-stu-id="28b5a-114">How to: Create a Basic Atom Feed</span></span>](how-to-create-a-basic-atom-feed.md)  
 <span data-ttu-id="28b5a-115">Viene illustrato come creare un servizio che rende disponibile un feed ATOM di base.</span><span class="sxs-lookup"><span data-stu-id="28b5a-115">Shows how to create a service that makes a basic ATOM feed available.</span></span>  
  
 [<span data-ttu-id="28b5a-116">Procedura: esporre un feed come Atom e RSS</span><span class="sxs-lookup"><span data-stu-id="28b5a-116">How to: Expose a Feed as Both Atom and RSS</span></span>](how-to-expose-a-feed-as-both-atom-and-rss.md)  
 <span data-ttu-id="28b5a-117">Viene illustrato come creare un servizio che rende lo stesso feed disponibile come ATOM e RSS.</span><span class="sxs-lookup"><span data-stu-id="28b5a-117">Shows how to create a service that makes the same feed available with ATOM and RSS.</span></span>  
  
 [<span data-ttu-id="28b5a-118">Estendibilità della diffusione</span><span class="sxs-lookup"><span data-stu-id="28b5a-118">Syndication Extensibility</span></span>](syndication-extensibility.md)  
 <span data-ttu-id="28b5a-119">Vengono illustrati i metodi per l'aggiunta di elementi e attributi personalizzati a un feed di diffusione.</span><span class="sxs-lookup"><span data-stu-id="28b5a-119">Describes the methods of adding custom elements and attributes to a syndication feed.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="28b5a-120">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="28b5a-120">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="28b5a-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="28b5a-121">Related Sections</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28b5a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28b5a-122">See also</span></span>

- [<span data-ttu-id="28b5a-123">Modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="28b5a-123">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
- [<span data-ttu-id="28b5a-124">Attendibilità parziale</span><span class="sxs-lookup"><span data-stu-id="28b5a-124">Partial Trust</span></span>](partial-trust.md)

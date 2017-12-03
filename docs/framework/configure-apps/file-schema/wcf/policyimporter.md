---
title: '&lt;policyImporter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b56c431c0e8dbab7bd4680a6e692d9b4f6e0eec4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="d9787-102">&lt;policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="d9787-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="d9787-103">Specifica un'unità di importazione dei criteri che controlla l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="d9787-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="d9787-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d9787-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d9787-105">\<client ></span><span class="sxs-lookup"><span data-stu-id="d9787-105">\<client></span></span>  
<span data-ttu-id="d9787-106">\<metadati ></span><span class="sxs-lookup"><span data-stu-id="d9787-106">\<metadata></span></span>  
<span data-ttu-id="d9787-107">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="d9787-107">\<policyImporters></span></span>  
<span data-ttu-id="d9787-108">\<policyImporter ></span><span class="sxs-lookup"><span data-stu-id="d9787-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9787-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9787-109">Syntax</span></span>  
  
```xml  
<metadata>  
   <policyImporters>  
      <policyImporter type="string" />  
   </policyImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9787-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d9787-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d9787-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d9787-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9787-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="d9787-112">Attributes</span></span>  
  
|<span data-ttu-id="d9787-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="d9787-113">Attribute</span></span>|<span data-ttu-id="d9787-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9787-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="d9787-115">Tipo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="d9787-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9787-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d9787-116">Child Elements</span></span>  
 <span data-ttu-id="d9787-117">None</span><span class="sxs-lookup"><span data-stu-id="d9787-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9787-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d9787-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d9787-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9787-119">Element</span></span>|<span data-ttu-id="d9787-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9787-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9787-121">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="d9787-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="d9787-122">Specifica tutte le unità di importazione dei criteri che controllano l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="d9787-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9787-123">Note</span><span class="sxs-lookup"><span data-stu-id="d9787-123">Remarks</span></span>  
 <span data-ttu-id="d9787-124">Un'unità di importazione dei criteri viene usata per la ricerca di asserzioni di criteri personalizzati sulle funzionalità delle associazioni e per allegare un elemento di associazione personalizzato che implementa le funzionalità richieste dall'asserzione.</span><span class="sxs-lookup"><span data-stu-id="d9787-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9787-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9787-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 [<span data-ttu-id="d9787-126">Configurazione di Client WCF</span><span class="sxs-lookup"><span data-stu-id="d9787-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="d9787-127">Client</span><span class="sxs-lookup"><span data-stu-id="d9787-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)

---
title: '&lt;policyImporter&gt;'
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 7483a95accef0a4bc956d919087379363b4762ca
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753027"
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="b37eb-102">&lt;policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="b37eb-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="b37eb-103">Specifica un'unità di importazione dei criteri che controlla l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="b37eb-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="b37eb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b37eb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b37eb-105">\<client></span><span class="sxs-lookup"><span data-stu-id="b37eb-105">\<client></span></span>  
<span data-ttu-id="b37eb-106">\<metadati ></span><span class="sxs-lookup"><span data-stu-id="b37eb-106">\<metadata></span></span>  
<span data-ttu-id="b37eb-107">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="b37eb-107">\<policyImporters></span></span>  
<span data-ttu-id="b37eb-108">\<policyImporter ></span><span class="sxs-lookup"><span data-stu-id="b37eb-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b37eb-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b37eb-109">Syntax</span></span>  
  
```xml  
<metadata>  
   <policyImporters>  
      <policyImporter type="string" />  
   </policyImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b37eb-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b37eb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b37eb-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b37eb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b37eb-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="b37eb-112">Attributes</span></span>  
  
|<span data-ttu-id="b37eb-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="b37eb-113">Attribute</span></span>|<span data-ttu-id="b37eb-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b37eb-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="b37eb-115">Tipo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="b37eb-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b37eb-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b37eb-116">Child Elements</span></span>  
 <span data-ttu-id="b37eb-117">Nessuno</span><span class="sxs-lookup"><span data-stu-id="b37eb-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b37eb-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b37eb-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b37eb-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b37eb-119">Element</span></span>|<span data-ttu-id="b37eb-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b37eb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b37eb-121">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="b37eb-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="b37eb-122">Specifica tutte le unità di importazione dei criteri che controllano l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="b37eb-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b37eb-123">Note</span><span class="sxs-lookup"><span data-stu-id="b37eb-123">Remarks</span></span>  
 <span data-ttu-id="b37eb-124">Un'unità di importazione dei criteri viene usata per la ricerca di asserzioni di criteri personalizzati sulle funzionalità delle associazioni e per allegare un elemento di associazione personalizzato che implementa le funzionalità richieste dall'asserzione.</span><span class="sxs-lookup"><span data-stu-id="b37eb-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b37eb-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b37eb-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 [<span data-ttu-id="b37eb-126">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="b37eb-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="b37eb-127">Client</span><span class="sxs-lookup"><span data-stu-id="b37eb-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)

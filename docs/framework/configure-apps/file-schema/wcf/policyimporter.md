---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 273bd0d5e68a661c639b82264b440b83d8127427
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933796"
---
# <a name="policyimporter"></a><span data-ttu-id="18ad7-101">\<> policyImporter</span><span class="sxs-lookup"><span data-stu-id="18ad7-101">\<policyImporter></span></span>
<span data-ttu-id="18ad7-102">Specifica un'unità di importazione dei criteri che controlla l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="18ad7-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="18ad7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="18ad7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="18ad7-104">\<client></span><span class="sxs-lookup"><span data-stu-id="18ad7-104">\<client></span></span>  
<span data-ttu-id="18ad7-105">\<> metadati</span><span class="sxs-lookup"><span data-stu-id="18ad7-105">\<metadata></span></span>  
<span data-ttu-id="18ad7-106">\<> policyImporters</span><span class="sxs-lookup"><span data-stu-id="18ad7-106">\<policyImporters></span></span>  
<span data-ttu-id="18ad7-107">\<> policyImporter</span><span class="sxs-lookup"><span data-stu-id="18ad7-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18ad7-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18ad7-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18ad7-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="18ad7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="18ad7-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="18ad7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18ad7-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="18ad7-111">Attributes</span></span>  
  
|<span data-ttu-id="18ad7-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="18ad7-112">Attribute</span></span>|<span data-ttu-id="18ad7-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="18ad7-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="18ad7-114">Tipo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="18ad7-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18ad7-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="18ad7-115">Child Elements</span></span>  
 <span data-ttu-id="18ad7-116">Nessuna</span><span class="sxs-lookup"><span data-stu-id="18ad7-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18ad7-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="18ad7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="18ad7-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="18ad7-118">Element</span></span>|<span data-ttu-id="18ad7-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18ad7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18ad7-120">\<> policyImporters</span><span class="sxs-lookup"><span data-stu-id="18ad7-120">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="18ad7-121">Specifica tutte le unità di importazione dei criteri che controllano l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="18ad7-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18ad7-122">Note</span><span class="sxs-lookup"><span data-stu-id="18ad7-122">Remarks</span></span>  
 <span data-ttu-id="18ad7-123">Un'unità di importazione dei criteri viene usata per la ricerca di asserzioni di criteri personalizzati sulle funzionalità delle associazioni e per allegare un elemento di associazione personalizzato che implementa le funzionalità richieste dall'asserzione.</span><span class="sxs-lookup"><span data-stu-id="18ad7-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18ad7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18ad7-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="18ad7-125">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="18ad7-125">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="18ad7-126">Client</span><span class="sxs-lookup"><span data-stu-id="18ad7-126">Clients</span></span>](../../../wcf/feature-details/clients.md)

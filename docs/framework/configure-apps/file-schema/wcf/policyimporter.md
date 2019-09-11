---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4ef5890d52c3f2af42322f023b9a2a23cb583035
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855058"
---
# <a name="policyimporter"></a><span data-ttu-id="07231-101">\<> policyImporter</span><span class="sxs-lookup"><span data-stu-id="07231-101">\<policyImporter></span></span>
<span data-ttu-id="07231-102">Specifica un'unità di importazione dei criteri che controlla l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="07231-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
<span data-ttu-id="07231-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="07231-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="07231-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="07231-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="07231-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> client**](client.md)</span><span class="sxs-lookup"><span data-stu-id="07231-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="07231-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> metadati**](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="07231-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)</span></span>\
<span data-ttu-id="07231-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> policyImporters**](policyimporters.md)</span><span class="sxs-lookup"><span data-stu-id="07231-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)</span></span>  
<span data-ttu-id="07231-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> policyImporter**</span><span class="sxs-lookup"><span data-stu-id="07231-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07231-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07231-109">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07231-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="07231-110">Attributes and Elements</span></span>  
 <span data-ttu-id="07231-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="07231-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07231-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="07231-112">Attributes</span></span>  
  
|<span data-ttu-id="07231-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="07231-113">Attribute</span></span>|<span data-ttu-id="07231-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07231-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="07231-115">Tipo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="07231-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07231-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="07231-116">Child Elements</span></span>  
 <span data-ttu-id="07231-117">Nessuna</span><span class="sxs-lookup"><span data-stu-id="07231-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07231-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="07231-118">Parent Elements</span></span>  
  
|<span data-ttu-id="07231-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="07231-119">Element</span></span>|<span data-ttu-id="07231-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07231-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07231-121">\<> policyImporters</span><span class="sxs-lookup"><span data-stu-id="07231-121">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="07231-122">Specifica tutte le unità di importazione dei criteri che controllano l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="07231-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07231-123">Note</span><span class="sxs-lookup"><span data-stu-id="07231-123">Remarks</span></span>  
 <span data-ttu-id="07231-124">Un'unità di importazione dei criteri viene usata per la ricerca di asserzioni di criteri personalizzati sulle funzionalità delle associazioni e per allegare un elemento di associazione personalizzato che implementa le funzionalità richieste dall'asserzione.</span><span class="sxs-lookup"><span data-stu-id="07231-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07231-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07231-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="07231-126">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="07231-126">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="07231-127">Client</span><span class="sxs-lookup"><span data-stu-id="07231-127">Clients</span></span>](../../../wcf/feature-details/clients.md)

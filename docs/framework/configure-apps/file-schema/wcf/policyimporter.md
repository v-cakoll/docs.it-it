---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4ef5890d52c3f2af42322f023b9a2a23cb583035
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855058"
---
# \<policyImporter>
<span data-ttu-id="ee6bf-101">Specifica un'unità di importazione dei criteri che controlla l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="ee6bf-101">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="ee6bf-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee6bf-102">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee6bf-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ee6bf-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ee6bf-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ee6bf-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee6bf-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="ee6bf-105">Attributes</span></span>  
  
|<span data-ttu-id="ee6bf-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="ee6bf-106">Attribute</span></span>|<span data-ttu-id="ee6bf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee6bf-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="ee6bf-108">Tipo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="ee6bf-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee6bf-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ee6bf-109">Child Elements</span></span>  
 <span data-ttu-id="ee6bf-110">nessuno</span><span class="sxs-lookup"><span data-stu-id="ee6bf-110">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee6bf-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ee6bf-111">Parent Elements</span></span>  
  
|<span data-ttu-id="ee6bf-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee6bf-112">Element</span></span>|<span data-ttu-id="ee6bf-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee6bf-113">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="ee6bf-114">Specifica tutte le unità di importazione dei criteri che controllano l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="ee6bf-114">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee6bf-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="ee6bf-115">Remarks</span></span>  
 <span data-ttu-id="ee6bf-116">Un'unità di importazione dei criteri viene usata per la ricerca di asserzioni di criteri personalizzati sulle funzionalità delle associazioni e per allegare un elemento di associazione personalizzato che implementa le funzionalità richieste dall'asserzione.</span><span class="sxs-lookup"><span data-stu-id="ee6bf-116">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee6bf-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ee6bf-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="ee6bf-118">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="ee6bf-118">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="ee6bf-119">Client</span><span class="sxs-lookup"><span data-stu-id="ee6bf-119">Clients</span></span>](../../../wcf/feature-details/clients.md)

---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 1f34486296465b3ea0b5b05bd9492062c85ad8c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670248"
---
# <a name="wsdlimporter"></a><span data-ttu-id="0f19f-101">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="0f19f-101">\<wsdlImporter></span></span>
<span data-ttu-id="0f19f-102">Specifica tutte le unità di importazione WSDL per l'importazione di metadati Web Services Description Language (WSDL) 1.1 con allegati WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="0f19f-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="0f19f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0f19f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0f19f-104">\<client></span><span class="sxs-lookup"><span data-stu-id="0f19f-104">\<client></span></span>  
<span data-ttu-id="0f19f-105">\<metadata></span><span class="sxs-lookup"><span data-stu-id="0f19f-105">\<metadata></span></span>  
<span data-ttu-id="0f19f-106">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="0f19f-106">\<wsdlImporters></span></span>  
<span data-ttu-id="0f19f-107">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="0f19f-107">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f19f-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f19f-108">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f19f-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0f19f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0f19f-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0f19f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f19f-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="0f19f-111">Attributes</span></span>  
  
|<span data-ttu-id="0f19f-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="0f19f-112">Attribute</span></span>|<span data-ttu-id="0f19f-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f19f-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="0f19f-114">Tipo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="0f19f-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f19f-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0f19f-115">Child Elements</span></span>  
 <span data-ttu-id="0f19f-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0f19f-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f19f-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0f19f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0f19f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="0f19f-118">Element</span></span>|<span data-ttu-id="0f19f-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f19f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f19f-120">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="0f19f-120">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="0f19f-121">Specifica tutte le unità di importazione WSDL per l'importazione di metadati Web Services Description Language (WSDL) 1.1 con allegati WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="0f19f-121">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f19f-122">Note</span><span class="sxs-lookup"><span data-stu-id="0f19f-122">Remarks</span></span>  
 <span data-ttu-id="0f19f-123">Un'unità di importazione WSDL viene usata per importare metadati e per convertire tali informazioni in diverse classi che rappresentano informazioni di contratto e di endpoint.</span><span class="sxs-lookup"><span data-stu-id="0f19f-123">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="0f19f-124">Può importare selettivamente informazioni di contratto e di endpoint e proprietà che espongono qualsiasi errore di importazione e accettano informazioni sul tipo relative al processo di importazione e di conversione.</span><span class="sxs-lookup"><span data-stu-id="0f19f-124">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="0f19f-125">Supporta inoltre l'importazione di informazioni dell'associazione e proprietà che forniscono accesso a qualsiasi documento di criteri, documento WSDL, estensione WSDL e documento di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="0f19f-125">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f19f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f19f-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="0f19f-127">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="0f19f-127">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="0f19f-128">Client</span><span class="sxs-lookup"><span data-stu-id="0f19f-128">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)

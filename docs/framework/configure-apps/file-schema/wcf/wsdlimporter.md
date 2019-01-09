---
title: '&lt;wsdlImporter&gt;'
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 43c1a50c740cd9c75ee641e4ac4d0fa8ea3ca36b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144990"
---
# <a name="ltwsdlimportergt"></a><span data-ttu-id="3a65f-102">&lt;wsdlImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="3a65f-102">&lt;wsdlImporter&gt;</span></span>
<span data-ttu-id="3a65f-103">Specifica tutte le unità di importazione WSDL per l'importazione di metadati Web Services Description Language (WSDL) 1.1 con allegati WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="3a65f-103">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="3a65f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3a65f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3a65f-105">\<client></span><span class="sxs-lookup"><span data-stu-id="3a65f-105">\<client></span></span>  
<span data-ttu-id="3a65f-106">\<metadati ></span><span class="sxs-lookup"><span data-stu-id="3a65f-106">\<metadata></span></span>  
<span data-ttu-id="3a65f-107">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="3a65f-107">\<wsdlImporters></span></span>  
<span data-ttu-id="3a65f-108">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="3a65f-108">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a65f-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a65f-109">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a65f-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3a65f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3a65f-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3a65f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a65f-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="3a65f-112">Attributes</span></span>  
  
|<span data-ttu-id="3a65f-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="3a65f-113">Attribute</span></span>|<span data-ttu-id="3a65f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a65f-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="3a65f-115">Tipo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="3a65f-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a65f-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3a65f-116">Child Elements</span></span>  
 <span data-ttu-id="3a65f-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3a65f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a65f-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3a65f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3a65f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a65f-119">Element</span></span>|<span data-ttu-id="3a65f-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a65f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a65f-121">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="3a65f-121">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="3a65f-122">Specifica tutte le unità di importazione WSDL per l'importazione di metadati Web Services Description Language (WSDL) 1.1 con allegati WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="3a65f-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a65f-123">Note</span><span class="sxs-lookup"><span data-stu-id="3a65f-123">Remarks</span></span>  
 <span data-ttu-id="3a65f-124">Un'unità di importazione WSDL viene usata per importare metadati e per convertire tali informazioni in diverse classi che rappresentano informazioni di contratto e di endpoint.</span><span class="sxs-lookup"><span data-stu-id="3a65f-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="3a65f-125">Può importare selettivamente informazioni di contratto e di endpoint e proprietà che espongono qualsiasi errore di importazione e accettano informazioni sul tipo relative al processo di importazione e di conversione.</span><span class="sxs-lookup"><span data-stu-id="3a65f-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="3a65f-126">Supporta inoltre l'importazione di informazioni dell'associazione e proprietà che forniscono accesso a qualsiasi documento di criteri, documento WSDL, estensione WSDL e documento di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="3a65f-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a65f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a65f-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="3a65f-128">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="3a65f-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="3a65f-129">Client</span><span class="sxs-lookup"><span data-stu-id="3a65f-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)

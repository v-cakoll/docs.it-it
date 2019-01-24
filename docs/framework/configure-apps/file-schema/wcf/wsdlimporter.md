---
title: '&lt;wsdlImporter&gt;'
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 5f3d53111c4d303146701b03d7e7b32833cd9edd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651045"
---
# <a name="ltwsdlimportergt"></a><span data-ttu-id="d1592-102">&lt;wsdlImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="d1592-102">&lt;wsdlImporter&gt;</span></span>
<span data-ttu-id="d1592-103">Specifica tutte le unità di importazione WSDL per l'importazione di metadati Web Services Description Language (WSDL) 1.1 con allegati WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="d1592-103">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="d1592-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d1592-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d1592-105">\<client></span><span class="sxs-lookup"><span data-stu-id="d1592-105">\<client></span></span>  
<span data-ttu-id="d1592-106">\<metadata></span><span class="sxs-lookup"><span data-stu-id="d1592-106">\<metadata></span></span>  
<span data-ttu-id="d1592-107">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="d1592-107">\<wsdlImporters></span></span>  
<span data-ttu-id="d1592-108">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="d1592-108">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1592-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1592-109">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1592-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d1592-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d1592-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d1592-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1592-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="d1592-112">Attributes</span></span>  
  
|<span data-ttu-id="d1592-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="d1592-113">Attribute</span></span>|<span data-ttu-id="d1592-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d1592-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="d1592-115">Tipo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="d1592-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1592-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d1592-116">Child Elements</span></span>  
 <span data-ttu-id="d1592-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d1592-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1592-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d1592-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d1592-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1592-119">Element</span></span>|<span data-ttu-id="d1592-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d1592-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1592-121">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="d1592-121">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="d1592-122">Specifica tutte le unità di importazione WSDL per l'importazione di metadati Web Services Description Language (WSDL) 1.1 con allegati WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="d1592-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1592-123">Note</span><span class="sxs-lookup"><span data-stu-id="d1592-123">Remarks</span></span>  
 <span data-ttu-id="d1592-124">Un'unità di importazione WSDL viene usata per importare metadati e per convertire tali informazioni in diverse classi che rappresentano informazioni di contratto e di endpoint.</span><span class="sxs-lookup"><span data-stu-id="d1592-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="d1592-125">Può importare selettivamente informazioni di contratto e di endpoint e proprietà che espongono qualsiasi errore di importazione e accettano informazioni sul tipo relative al processo di importazione e di conversione.</span><span class="sxs-lookup"><span data-stu-id="d1592-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="d1592-126">Supporta inoltre l'importazione di informazioni dell'associazione e proprietà che forniscono accesso a qualsiasi documento di criteri, documento WSDL, estensione WSDL e documento di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="d1592-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1592-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1592-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="d1592-128">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="d1592-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="d1592-129">Client</span><span class="sxs-lookup"><span data-stu-id="d1592-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)

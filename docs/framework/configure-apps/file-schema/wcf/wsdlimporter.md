---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 317921a66fa3b8d1f0026d676ea674b67732b3df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854766"
---
# \<wsdlImporter>
<span data-ttu-id="5834b-101">Specifica tutte le unità di importazione WSDL per l'importazione di metadati Web Services Description Language (WSDL) 1.1 con allegati WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="5834b-101">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="5834b-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5834b-102">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5834b-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5834b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="5834b-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5834b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5834b-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="5834b-105">Attributes</span></span>  
  
|<span data-ttu-id="5834b-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="5834b-106">Attribute</span></span>|<span data-ttu-id="5834b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5834b-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="5834b-108">Tipo di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="5834b-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5834b-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5834b-109">Child Elements</span></span>  
 <span data-ttu-id="5834b-110">No.</span><span class="sxs-lookup"><span data-stu-id="5834b-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5834b-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5834b-111">Parent Elements</span></span>  
  
|<span data-ttu-id="5834b-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="5834b-112">Element</span></span>|<span data-ttu-id="5834b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5834b-113">Description</span></span>|  
|-------------|-----------------|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="5834b-114">Specifica tutte le unità di importazione WSDL per l'importazione di metadati Web Services Description Language (WSDL) 1.1 con allegati WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="5834b-114">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5834b-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="5834b-115">Remarks</span></span>  
 <span data-ttu-id="5834b-116">Un'unità di importazione WSDL viene usata per importare metadati e per convertire tali informazioni in diverse classi che rappresentano informazioni di contratto e di endpoint.</span><span class="sxs-lookup"><span data-stu-id="5834b-116">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="5834b-117">Può importare selettivamente informazioni di contratto e di endpoint e proprietà che espongono qualsiasi errore di importazione e accettano informazioni sul tipo relative al processo di importazione e di conversione.</span><span class="sxs-lookup"><span data-stu-id="5834b-117">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="5834b-118">Supporta inoltre l'importazione di informazioni dell'associazione e proprietà che forniscono accesso a qualsiasi documento di criteri, documento WSDL, estensione WSDL e documento di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="5834b-118">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5834b-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="5834b-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="5834b-120">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="5834b-120">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="5834b-121">Client</span><span class="sxs-lookup"><span data-stu-id="5834b-121">Clients</span></span>](../../../wcf/feature-details/clients.md)

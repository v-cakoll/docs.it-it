---
title: '&lt;metadati&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e1da05ebd48a3fff7c35510db4093d56831a8fcd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltmetadatagt"></a><span data-ttu-id="b4e0c-102">&lt;metadati&gt;</span><span class="sxs-lookup"><span data-stu-id="b4e0c-102">&lt;metadata&gt;</span></span>
<span data-ttu-id="b4e0c-103">Specifica la modalità di elaborazione dei metadati di servizio.</span><span class="sxs-lookup"><span data-stu-id="b4e0c-103">Specifies how service metadata can be processed.</span></span>  
  
 <span data-ttu-id="b4e0c-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b4e0c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b4e0c-105">\<client ></span><span class="sxs-lookup"><span data-stu-id="b4e0c-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4e0c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4e0c-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
        <metadata>  
                   <policyImporters>  
                          <policyImporter type="string" />  
                   </policyImporters  
                 <wsdlImporters>  
                      <wsdlImporter type="string" />  
                 </wsdlImporters>  
        </metadata>  
    </client>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4e0c-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b4e0c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b4e0c-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b4e0c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4e0c-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="b4e0c-109">Attributes</span></span>  
 <span data-ttu-id="b4e0c-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b4e0c-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b4e0c-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b4e0c-111">Child Elements</span></span>  
  
|<span data-ttu-id="b4e0c-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4e0c-112">Element</span></span>|<span data-ttu-id="b4e0c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4e0c-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4e0c-114">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="b4e0c-114">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="b4e0c-115">Specifica tutte le unità di importazione dei criteri che controllano l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="b4e0c-115">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="b4e0c-116">Un'unità di importazione dei criteri viene usata per la ricerca di asserzioni di criteri personalizzati sulle funzionalità delle associazioni e per allegare un elemento di associazione personalizzato che implementa le funzionalità richieste dall'asserzione.</span><span class="sxs-lookup"><span data-stu-id="b4e0c-116">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="b4e0c-117">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="b4e0c-117">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="b4e0c-118">Specifica tutte le unità di importazione WSDL che importano metadati Web Services Description Language (WSDL) 1.1 con allegati WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="b4e0c-118">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="b4e0c-119">Un'unità di importazione WSDL viene usata per importare metadati e per convertire tali informazioni in diverse classi che rappresentano informazioni di contratto e di endpoint.</span><span class="sxs-lookup"><span data-stu-id="b4e0c-119">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="b4e0c-120">Può importare selettivamente informazioni di contratto e di endpoint e proprietà che espongono qualsiasi errore di importazione e accettano informazioni sul tipo relative al processo di importazione e di conversione.</span><span class="sxs-lookup"><span data-stu-id="b4e0c-120">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="b4e0c-121">Supporta inoltre l'importazione di informazioni dell'associazione e proprietà che forniscono accesso a qualsiasi documento di criteri, documento WSDL, estensione WSDL e documento di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="b4e0c-121">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b4e0c-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b4e0c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b4e0c-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4e0c-123">Element</span></span>|<span data-ttu-id="b4e0c-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4e0c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4e0c-125">\<client ></span><span class="sxs-lookup"><span data-stu-id="b4e0c-125">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="b4e0c-126">La sezione client definisce un elenco di endpoint ai quali un client può connettersi.</span><span class="sxs-lookup"><span data-stu-id="b4e0c-126">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4e0c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4e0c-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="b4e0c-128">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="b4e0c-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="b4e0c-129">Client</span><span class="sxs-lookup"><span data-stu-id="b4e0c-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)

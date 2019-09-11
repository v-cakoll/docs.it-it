---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 028e4d3fbe7bce06caa7497c8f95f3b293a4b068
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855232"
---
# <a name="metadata"></a><span data-ttu-id="1dec2-101">\<> metadati</span><span class="sxs-lookup"><span data-stu-id="1dec2-101">\<metadata></span></span>
<span data-ttu-id="1dec2-102">Specifica la modalità di elaborazione dei metadati di servizio.</span><span class="sxs-lookup"><span data-stu-id="1dec2-102">Specifies how service metadata can be processed.</span></span>  
  
<span data-ttu-id="1dec2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1dec2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1dec2-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1dec2-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1dec2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> client**](client.md)</span><span class="sxs-lookup"><span data-stu-id="1dec2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="1dec2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> metadati**</span><span class="sxs-lookup"><span data-stu-id="1dec2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<metadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dec2-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1dec2-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <metadata>
      <policyImporters>
        <policyImporter type="string" />
      </policyImporters>
      <wsdlImporters>
        <wsdlImporter type="string" />
      </wsdlImporters>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dec2-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1dec2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1dec2-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1dec2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dec2-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="1dec2-110">Attributes</span></span>  
 <span data-ttu-id="1dec2-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1dec2-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1dec2-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1dec2-112">Child Elements</span></span>  
  
|<span data-ttu-id="1dec2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="1dec2-113">Element</span></span>|<span data-ttu-id="1dec2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1dec2-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dec2-115">\<> policyImporters</span><span class="sxs-lookup"><span data-stu-id="1dec2-115">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="1dec2-116">Specifica tutte le unità di importazione dei criteri che controllano l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="1dec2-116">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="1dec2-117">Un'unità di importazione dei criteri viene usata per la ricerca di asserzioni di criteri personalizzati sulle funzionalità delle associazioni e per allegare un elemento di associazione personalizzato che implementa le funzionalità richieste dall'asserzione.</span><span class="sxs-lookup"><span data-stu-id="1dec2-117">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="1dec2-118">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="1dec2-118">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="1dec2-119">Specifica tutte le unità di importazione WSDL che importano metadati Web Services Description Language (WSDL) 1.1 con allegati WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="1dec2-119">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="1dec2-120">Un'unità di importazione WSDL viene usata per importare metadati e per convertire tali informazioni in diverse classi che rappresentano informazioni di contratto e di endpoint.</span><span class="sxs-lookup"><span data-stu-id="1dec2-120">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="1dec2-121">Può importare selettivamente informazioni di contratto e di endpoint e proprietà che espongono qualsiasi errore di importazione e accettano informazioni sul tipo relative al processo di importazione e di conversione.</span><span class="sxs-lookup"><span data-stu-id="1dec2-121">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="1dec2-122">Supporta inoltre l'importazione di informazioni dell'associazione e proprietà che forniscono accesso a qualsiasi documento di criteri, documento WSDL, estensione WSDL e documento di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="1dec2-122">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1dec2-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1dec2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1dec2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="1dec2-124">Element</span></span>|<span data-ttu-id="1dec2-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1dec2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dec2-126">\<client></span><span class="sxs-lookup"><span data-stu-id="1dec2-126">\<client></span></span>](client.md)|<span data-ttu-id="1dec2-127">La sezione client definisce un elenco di endpoint ai quali un client può connettersi.</span><span class="sxs-lookup"><span data-stu-id="1dec2-127">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1dec2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dec2-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="1dec2-129">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="1dec2-129">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="1dec2-130">Client</span><span class="sxs-lookup"><span data-stu-id="1dec2-130">Clients</span></span>](../../../wcf/feature-details/clients.md)

---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 028e4d3fbe7bce06caa7497c8f95f3b293a4b068
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855232"
---
# \<metadata>
<span data-ttu-id="07542-101">Specifica la modalità di elaborazione dei metadati di servizio.</span><span class="sxs-lookup"><span data-stu-id="07542-101">Specifies how service metadata can be processed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<metadata>**  
  
## <a name="syntax"></a><span data-ttu-id="07542-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07542-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07542-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="07542-103">Attributes and Elements</span></span>  
 <span data-ttu-id="07542-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="07542-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07542-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="07542-105">Attributes</span></span>  
 <span data-ttu-id="07542-106">No.</span><span class="sxs-lookup"><span data-stu-id="07542-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="07542-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="07542-107">Child Elements</span></span>  
  
|<span data-ttu-id="07542-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="07542-108">Element</span></span>|<span data-ttu-id="07542-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07542-109">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="07542-110">Specifica tutte le unità di importazione dei criteri che controllano l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="07542-110">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="07542-111">Un'unità di importazione dei criteri viene usata per la ricerca di asserzioni di criteri personalizzati sulle funzionalità delle associazioni e per allegare un elemento di associazione personalizzato che implementa le funzionalità richieste dall'asserzione.</span><span class="sxs-lookup"><span data-stu-id="07542-111">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="07542-112">Specifica tutte le unità di importazione WSDL che importano metadati Web Services Description Language (WSDL) 1.1 con allegati WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="07542-112">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="07542-113">Un'unità di importazione WSDL viene usata per importare metadati e per convertire tali informazioni in diverse classi che rappresentano informazioni di contratto e di endpoint.</span><span class="sxs-lookup"><span data-stu-id="07542-113">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="07542-114">Può importare selettivamente informazioni di contratto e di endpoint e proprietà che espongono qualsiasi errore di importazione e accettano informazioni sul tipo relative al processo di importazione e di conversione.</span><span class="sxs-lookup"><span data-stu-id="07542-114">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="07542-115">Supporta inoltre l'importazione di informazioni dell'associazione e proprietà che forniscono accesso a qualsiasi documento di criteri, documento WSDL, estensione WSDL e documento di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="07542-115">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07542-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="07542-116">Parent Elements</span></span>  
  
|<span data-ttu-id="07542-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="07542-117">Element</span></span>|<span data-ttu-id="07542-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07542-118">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="07542-119">La sezione client definisce un elenco di endpoint ai quali un client può connettersi.</span><span class="sxs-lookup"><span data-stu-id="07542-119">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07542-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="07542-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="07542-121">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="07542-121">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="07542-122">Client</span><span class="sxs-lookup"><span data-stu-id="07542-122">Clients</span></span>](../../../wcf/feature-details/clients.md)

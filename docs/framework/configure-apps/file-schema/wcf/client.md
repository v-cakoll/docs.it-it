---
title: '&lt;client&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 67f91f4462fc8c11b1769d5805a4ad1407385a50
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientgt"></a><span data-ttu-id="6cfcb-102">&lt;client&gt;</span><span class="sxs-lookup"><span data-stu-id="6cfcb-102">&lt;client&gt;</span></span>
<span data-ttu-id="6cfcb-103">L'elemento `client` definisce un elenco di endpoint ai quali può connettersi un client.</span><span class="sxs-lookup"><span data-stu-id="6cfcb-103">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="6cfcb-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6cfcb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6cfcb-105">\<client ></span><span class="sxs-lookup"><span data-stu-id="6cfcb-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cfcb-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6cfcb-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
        <endpoint>  
        </endpoint>  
                <metadata>  
        </metadata>  
    </client>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6cfcb-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6cfcb-107">Attributes and Elements</span></span>  
 <span data-ttu-id="6cfcb-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6cfcb-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6cfcb-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="6cfcb-109">Attributes</span></span>  
 <span data-ttu-id="6cfcb-110">Nessuna</span><span class="sxs-lookup"><span data-stu-id="6cfcb-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6cfcb-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6cfcb-111">Child Elements</span></span>  
  
|<span data-ttu-id="6cfcb-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="6cfcb-112">Element</span></span>|<span data-ttu-id="6cfcb-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6cfcb-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6cfcb-114">\<endpoint ></span><span class="sxs-lookup"><span data-stu-id="6cfcb-114">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="6cfcb-115">Contiene una raccolta di elementi dell'endpoint che specifica a quali endpoint può connettersi questo client.</span><span class="sxs-lookup"><span data-stu-id="6cfcb-115">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="6cfcb-116">\<metadati ></span><span class="sxs-lookup"><span data-stu-id="6cfcb-116">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="6cfcb-117">Contiene impostazioni per l'elaborazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="6cfcb-117">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6cfcb-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6cfcb-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6cfcb-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6cfcb-119">Element</span></span>|<span data-ttu-id="6cfcb-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6cfcb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6cfcb-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6cfcb-121">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="6cfcb-122">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6cfcb-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6cfcb-123">Note</span><span class="sxs-lookup"><span data-stu-id="6cfcb-123">Remarks</span></span>  
 <span data-ttu-id="6cfcb-124">La sezione `client` definisce un elenco di endpoint ai quali può connettersi un client.</span><span class="sxs-lookup"><span data-stu-id="6cfcb-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="6cfcb-125">Ogni endpoint elencato nella sezione client definisce la propria associazione, comportamento e contratto.</span><span class="sxs-lookup"><span data-stu-id="6cfcb-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="6cfcb-126">È identificato in modo univoco dalla combinazione degli attributi `name` e `contract`.</span><span class="sxs-lookup"><span data-stu-id="6cfcb-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="6cfcb-127">Il codice client specifica il `name` al quale connettere un endpoint per il servizio implementato dal client.</span><span class="sxs-lookup"><span data-stu-id="6cfcb-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="6cfcb-128">Se l'attributo `name` è omesso, l'endpoint si comporta come endpoint predefinito per il contratto che implementa.</span><span class="sxs-lookup"><span data-stu-id="6cfcb-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="6cfcb-129">In aggiunta, questa sezione specifica anche impostazioni per l'elaborazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="6cfcb-129">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cfcb-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="6cfcb-130">Example</span></span>  
  
```xml  
<client>  
    <endpoint address="/HelloWorld/"  
              bindingConfiguration="usingDefaults"  
              name="MyBinding"  
              binding="customBinding"  
              contract="HelloWorld">  
    <addressProperties actingAs="http://www.microsoft.com/TestActor"  
             identityData="BasicReadWrite" identityType="Spn" isAddressPrivate="false">  
    </endpoint>  
</client>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6cfcb-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cfcb-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 [<span data-ttu-id="6cfcb-132">Configurazione di Client WCF</span><span class="sxs-lookup"><span data-stu-id="6cfcb-132">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="6cfcb-133">Client</span><span class="sxs-lookup"><span data-stu-id="6cfcb-133">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)

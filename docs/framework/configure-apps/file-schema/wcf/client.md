---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 93365c109f015b2ec72b5216dcb8c46258d022e2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55280904"
---
# <a name="client"></a><span data-ttu-id="842ca-101">\<client></span><span class="sxs-lookup"><span data-stu-id="842ca-101">\<client></span></span>
<span data-ttu-id="842ca-102">L'elemento `client` definisce un elenco di endpoint ai quali può connettersi un client.</span><span class="sxs-lookup"><span data-stu-id="842ca-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="842ca-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="842ca-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="842ca-104">\<client></span><span class="sxs-lookup"><span data-stu-id="842ca-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="842ca-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="842ca-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="842ca-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="842ca-106">Attributes and Elements</span></span>  
 <span data-ttu-id="842ca-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="842ca-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="842ca-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="842ca-108">Attributes</span></span>  
 <span data-ttu-id="842ca-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="842ca-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="842ca-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="842ca-110">Child Elements</span></span>  
  
|<span data-ttu-id="842ca-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="842ca-111">Element</span></span>|<span data-ttu-id="842ca-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="842ca-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="842ca-113">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="842ca-113">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="842ca-114">Contiene una raccolta di elementi dell'endpoint che specifica a quali endpoint può connettersi questo client.</span><span class="sxs-lookup"><span data-stu-id="842ca-114">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="842ca-115">\<metadata></span><span class="sxs-lookup"><span data-stu-id="842ca-115">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="842ca-116">Contiene impostazioni per l'elaborazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="842ca-116">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="842ca-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="842ca-117">Parent Elements</span></span>  
  
|<span data-ttu-id="842ca-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="842ca-118">Element</span></span>|<span data-ttu-id="842ca-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="842ca-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="842ca-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="842ca-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="842ca-121">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="842ca-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="842ca-122">Note</span><span class="sxs-lookup"><span data-stu-id="842ca-122">Remarks</span></span>  
 <span data-ttu-id="842ca-123">La sezione `client` definisce un elenco di endpoint ai quali può connettersi un client.</span><span class="sxs-lookup"><span data-stu-id="842ca-123">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="842ca-124">Ogni endpoint elencato nella sezione client definisce la propria associazione, comportamento e contratto.</span><span class="sxs-lookup"><span data-stu-id="842ca-124">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="842ca-125">È identificato in modo univoco dalla combinazione degli attributi `name` e `contract`.</span><span class="sxs-lookup"><span data-stu-id="842ca-125">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="842ca-126">Il codice client specifica il `name` al quale connettere un endpoint per il servizio implementato dal client.</span><span class="sxs-lookup"><span data-stu-id="842ca-126">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="842ca-127">Se l'attributo `name` è omesso, l'endpoint si comporta come endpoint predefinito per il contratto che implementa.</span><span class="sxs-lookup"><span data-stu-id="842ca-127">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="842ca-128">In aggiunta, questa sezione specifica anche impostazioni per l'elaborazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="842ca-128">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="842ca-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="842ca-129">Example</span></span>  
  
```xml  
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```  
  
## <a name="see-also"></a><span data-ttu-id="842ca-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="842ca-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="842ca-131">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="842ca-131">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="842ca-132">Client</span><span class="sxs-lookup"><span data-stu-id="842ca-132">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)

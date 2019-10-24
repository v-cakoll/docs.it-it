---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7aa3755be97a839cb576d53852b75cfe50e39276
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773938"
---
# <a name="client"></a><span data-ttu-id="ceadc-101">> client di \<</span><span class="sxs-lookup"><span data-stu-id="ceadc-101">\<client></span></span>
<span data-ttu-id="ceadc-102">L'elemento `client` definisce un elenco di endpoint ai quali può connettersi un client.</span><span class="sxs-lookup"><span data-stu-id="ceadc-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>

<span data-ttu-id="ceadc-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ceadc-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ceadc-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ceadc-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ceadc-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<client** ></span><span class="sxs-lookup"><span data-stu-id="ceadc-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ceadc-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ceadc-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="ceadc-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ceadc-107">Attributes and Elements</span></span>
 <span data-ttu-id="ceadc-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ceadc-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ceadc-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="ceadc-109">Attributes</span></span>
 <span data-ttu-id="ceadc-110">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ceadc-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="ceadc-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ceadc-111">Child Elements</span></span>

|<span data-ttu-id="ceadc-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="ceadc-112">Element</span></span>|<span data-ttu-id="ceadc-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ceadc-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ceadc-114">\<endpoint ></span><span class="sxs-lookup"><span data-stu-id="ceadc-114">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="ceadc-115">Contiene una raccolta di elementi endpoint che specificano gli endpoint a cui il client può connettersi.</span><span class="sxs-lookup"><span data-stu-id="ceadc-115">Contains a collection of endpoint elements that specify the endpoints that this client can connect to.</span></span>|
|[<span data-ttu-id="ceadc-116">\<metadati ></span><span class="sxs-lookup"><span data-stu-id="ceadc-116">\<metadata></span></span>](metadata.md)|<span data-ttu-id="ceadc-117">Contiene impostazioni per l'elaborazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="ceadc-117">Contains settings for processing metadata.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ceadc-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ceadc-118">Parent Elements</span></span>

|<span data-ttu-id="ceadc-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ceadc-119">Element</span></span>|<span data-ttu-id="ceadc-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ceadc-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ceadc-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ceadc-121">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="ceadc-122">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ceadc-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ceadc-123">Note</span><span class="sxs-lookup"><span data-stu-id="ceadc-123">Remarks</span></span>
 <span data-ttu-id="ceadc-124">La sezione `client` definisce un elenco di endpoint ai quali può connettersi un client.</span><span class="sxs-lookup"><span data-stu-id="ceadc-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="ceadc-125">Ogni endpoint elencato nella sezione client definisce la propria associazione, comportamento e contratto.</span><span class="sxs-lookup"><span data-stu-id="ceadc-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="ceadc-126">È identificato in modo univoco dalla combinazione degli attributi `name` e `contract`.</span><span class="sxs-lookup"><span data-stu-id="ceadc-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="ceadc-127">Il codice client specifica il `name` al quale connettere un endpoint per il servizio implementato dal client.</span><span class="sxs-lookup"><span data-stu-id="ceadc-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="ceadc-128">Se l'attributo `name` è omesso, l'endpoint si comporta come endpoint predefinito per il contratto che implementa.</span><span class="sxs-lookup"><span data-stu-id="ceadc-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>

 <span data-ttu-id="ceadc-129">In aggiunta, questa sezione specifica anche impostazioni per l'elaborazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="ceadc-129">In addition, this section also specifies settings for processing metadata.</span></span>

## <a name="example"></a><span data-ttu-id="ceadc-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="ceadc-130">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ceadc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ceadc-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="ceadc-132">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="ceadc-132">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="ceadc-133">Client</span><span class="sxs-lookup"><span data-stu-id="ceadc-133">Clients</span></span>](../../../wcf/feature-details/clients.md)

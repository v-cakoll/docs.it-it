---
title: <behavior> di <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: 489678a5adeae3965acae90a847c4b087478354d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140804"
---
# <a name="behavior-of-endpointbehaviors"></a><span data-ttu-id="ef1c8-102">\<behavior> di \<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="ef1c8-102">\<behavior> of \<endpointBehaviors></span></span>
<span data-ttu-id="ef1c8-103">L'elemento `behavior` contiene una raccolta di impostazioni per il comportamento di un endpoint.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-103">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="ef1c8-104">Ogni comportamento è indicizzato in base al relativo `name`.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="ef1c8-105">Gli endpoint possono essere collegati a ciascun comportamento tramite questo nome.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-105">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="ef1c8-106">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-106">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="ef1c8-107">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="ef1c8-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="ef1c8-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef1c8-108">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef1c8-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ef1c8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ef1c8-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef1c8-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="ef1c8-111">Attributes</span></span>  
  
|<span data-ttu-id="ef1c8-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="ef1c8-112">Attribute</span></span>|<span data-ttu-id="ef1c8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef1c8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef1c8-114">name</span><span class="sxs-lookup"><span data-stu-id="ef1c8-114">name</span></span>|<span data-ttu-id="ef1c8-115">Stringa univoca che contiene il nome di configurazione del comportamento.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-115">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="ef1c8-116">Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-116">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="ef1c8-117">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-117">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="ef1c8-118">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="ef1c8-118">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef1c8-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ef1c8-119">Child Elements</span></span>  
  
|<span data-ttu-id="ef1c8-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef1c8-120">Element</span></span>|<span data-ttu-id="ef1c8-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef1c8-121">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="ef1c8-122">Specifica le credenziali usate per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-122">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[\<callbackDebug>](callbackdebug.md)|<span data-ttu-id="ef1c8-123">Specifica il debug del servizio per un oggetto callback di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ef1c8-123">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>|  
|[\<callbackTimeouts>](callbacktimeouts.md)|<span data-ttu-id="ef1c8-124">Specifica il timeout per il callback client.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-124">Specifies the timeout for the client callback.</span></span>|  
|[\<clientVia>](clientvia.md)|<span data-ttu-id="ef1c8-125">Specifica la route che un messaggio deve prendere.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-125">Specifies the route a message should take.</span></span>|  
|[\<dataContractSerializer>](datacontractserializer.md)|<span data-ttu-id="ef1c8-126">Contiene i dati di configurazione per DataContractSerializer.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-126">Contains configuration data for the DataContractSerializer.</span></span>|  
|[\<dispatcherSynchronization>](dispatchersynchronization.md)|<span data-ttu-id="ef1c8-127">Specifica un comportamento dell'endpoint che consente a un servizio di inviare risposte in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-127">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[\<enableWebScript>](enablewebscript.md)|<span data-ttu-id="ef1c8-128">Abilita il comportamento dell'endpoint che rende possibile l'uso del servizio da pagine Web ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-128">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="ef1c8-129">Il comportamento deve essere usato solo in combinazione con l' \<webHttpBinding> associazione standard o con l' \<webMessageEncoding> elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-129">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="ef1c8-130">Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-130">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[\<soapProcessing>](soapprocessing.md)|<span data-ttu-id="ef1c8-131">Definisce il comportamento dell'endpoint client usato per effettuare il marshalling dei messaggi tra versioni del messaggio e tipi di associazione diversi.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-131">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[\<synchronousReceive>](synchronousreceive-element.md)|<span data-ttu-id="ef1c8-132">Specifica il comportamento di run-time per la ricezione di messaggi in un'applicazione client o di servizio.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-132">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="ef1c8-133">Non prevede attributi o elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-133">It does not have any attributes or child elements.</span></span>|  
|[\<transactedBatching>](transactedbatching.md)|<span data-ttu-id="ef1c8-134">Specifica se il batch delle transazioni è supportato per le operazioni di ricezione.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-134">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[\<webHttp>](webhttp.md)|<span data-ttu-id="ef1c8-135">Specifica il WebHttpBehavior in un endpoint tramite configurazione.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-135">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="ef1c8-136">Questo comportamento, se utilizzato in combinazione con l' \<webHttpBinding> associazione standard, Abilita il modello di programmazione Web per un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-136">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a WCF service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef1c8-137">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ef1c8-137">Parent Elements</span></span>  
  
|<span data-ttu-id="ef1c8-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef1c8-138">Element</span></span>|<span data-ttu-id="ef1c8-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef1c8-139">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="ef1c8-140">Raccolta di elementi di comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="ef1c8-140">A collection of endpoint behavior elements.</span></span>|

---
title: <behavior> di <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 115f94fc3f17dc5b4dd1ee3a090f2c9d121f810b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139726"
---
# <a name="behavior-of-servicebehaviors"></a><span data-ttu-id="9d8ee-102">\<behavior> di \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9d8ee-102">\<behavior> of \<serviceBehaviors></span></span>
<span data-ttu-id="9d8ee-103">L'elemento `behavior` contiene una raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-103">The `behavior` element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="9d8ee-104">Ogni comportamento è indicizzato in base al relativo `name`.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="9d8ee-105">I servizi possono collegarsi a ogni comportamento tramite questo nome usando l' `behaviorConfiguration` attributo dell' [\<endpoint>](endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-105">Services can link to each behavior through this name using the `behaviorConfiguration` attribute of the [\<endpoint>](endpoint-element.md) element.</span></span> <span data-ttu-id="9d8ee-106">In questo modo gli endpoint possono condividere configurazioni del comportamento comuni senza ridefinire le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span> <span data-ttu-id="9d8ee-107">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-107">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9d8ee-108">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9d8ee-108">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d8ee-109">Gli elementi di comportamento specifici delle attività del flusso di lavoro di Windows, ad esempio l' [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) elemento, sono documentati nella pagina [ \<behavior> di \<serviceBehaviors> ](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) .</span><span class="sxs-lookup"><span data-stu-id="9d8ee-109">Behavior elements specific to Windows Workflow activities, such as the [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) element, are documented in the [\<behavior> of \<serviceBehaviors>](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) page.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="9d8ee-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d8ee-110">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d8ee-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9d8ee-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9d8ee-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d8ee-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="9d8ee-113">Attributes</span></span>  
  
|<span data-ttu-id="9d8ee-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="9d8ee-114">Attribute</span></span>|<span data-ttu-id="9d8ee-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d8ee-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d8ee-116">name</span><span class="sxs-lookup"><span data-stu-id="9d8ee-116">name</span></span>|<span data-ttu-id="9d8ee-117">Stringa univoca che contiene il nome di configurazione del comportamento.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-117">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="9d8ee-118">Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-118">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="9d8ee-119">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-119">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9d8ee-120">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9d8ee-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d8ee-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9d8ee-121">Child Elements</span></span>  
  
|<span data-ttu-id="9d8ee-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9d8ee-122">Element</span></span>|<span data-ttu-id="9d8ee-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d8ee-123">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-element.md)|<span data-ttu-id="9d8ee-124">Contiene i dati di configurazione per DataContractSerializer.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-124">Contains configuration data for the DataContractSerializer.</span></span>|  
|[\<persistenceProvider>](persistenceprovider.md)|<span data-ttu-id="9d8ee-125">Specifica il tipo di implementazione del provider di persistenza da usare, nonché il timeout da usare per le operazioni di persistenza.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-125">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>|  
|[\<routing>](routing-of-servicebehavior.md)|<span data-ttu-id="9d8ee-126">Fornisce l'accesso in fase di esecuzione al servizio di routing per consentire la modifica dinamica della configurazione di routing.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-126">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>|  
|[\<serviceAuthenticationManager>](serviceauthenticationmanager.md)|<span data-ttu-id="9d8ee-127">Fornisce un elemento di configurazione del flusso di lavoro che stabilisce a livello di servizio la validità di una trasmissione, di un messaggio o di un creatore.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-127">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>|  
|[\<serviceAuthorization>](serviceauthorization-element.md)|<span data-ttu-id="9d8ee-128">Specifica le impostazioni che autorizzano l'accesso alle operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-128">Specifies settings that authorize access to service operations.</span></span>|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="9d8ee-129">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-129">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>|  
|[\<serviceDebug>](servicedebug.md)|<span data-ttu-id="9d8ee-130">Specifica le funzionalità di debug e di informazioni della Guida per un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9d8ee-130">Specifies debugging and help information features for a Windows Communication Foundation (WCF) service.</span></span>|  
|[\<serviceDiscovery>](servicediscovery.md)|<span data-ttu-id="9d8ee-131">Specifica l'individuabilità degli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-131">Specifies the discoverability of service endpoints.</span></span>|  
|[\<serviceMetadata>](servicemetadata.md)|<span data-ttu-id="9d8ee-132">Specifica la pubblicazione dei metadati del servizio e delle informazioni associate.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-132">Specifies the publication of service metadata and associated information.</span></span>|  
|[\<serviceSecurityAudit>](servicesecurityaudit.md)|<span data-ttu-id="9d8ee-133">Specifica impostazioni che abilitano controllo di eventi di sicurezza durante le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-133">Specifies settings that enable auditing of security events during service operations.</span></span>|  
|[\<serviceThrottling>](servicethrottling.md)|<span data-ttu-id="9d8ee-134">Specifica il meccanismo di limitazione di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-134">Specifies the throttling mechanism of a WCF service.</span></span>|  
|[\<serviceTimeouts>](servicetimeouts.md)|<span data-ttu-id="9d8ee-135">Specifica il timeout per un servizio.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-135">Specifies the timeout for a service.</span></span>|  
|[\<workflowRuntime>](workflowruntime.md)|<span data-ttu-id="9d8ee-136">Specifica le impostazioni per un'istanza di WorkflowRuntime per l'hosting di servizi WCF basati sul flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-136">Specifies settings for an instance of WorkflowRuntime for hosting workflow-based WCF services.</span></span>|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="9d8ee-137">Abilita il recupero di informazioni sull'indirizzo di metadati dalle intestazioni del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-137">Enables the retrieval of metadata address information from the request message headers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9d8ee-138">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9d8ee-138">Parent Elements</span></span>  
  
|<span data-ttu-id="9d8ee-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="9d8ee-139">Element</span></span>|<span data-ttu-id="9d8ee-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d8ee-140">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors.md)|<span data-ttu-id="9d8ee-141">Raccolta di elementi di comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="9d8ee-141">A collection of service behavior elements.</span></span>|

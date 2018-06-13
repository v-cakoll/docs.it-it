---
title: '&lt;routing&gt; di &lt;serviceBehavior&gt;'
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 5fb7febe365f73acf09ba74b07215fe9cc659efb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750752"
---
# <a name="ltroutinggt-of-ltservicebehaviorgt"></a><span data-ttu-id="5f003-102">&lt;routing&gt; di &lt;serviceBehavior&gt;</span><span class="sxs-lookup"><span data-stu-id="5f003-102">&lt;routing&gt; of &lt;serviceBehavior&gt;</span></span>
<span data-ttu-id="5f003-103">Fornisce l'accesso in fase di esecuzione al servizio di routing per consentire la modifica dinamica della configurazione di routing.</span><span class="sxs-lookup"><span data-stu-id="5f003-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
 <span data-ttu-id="5f003-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5f003-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5f003-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="5f003-105">\<behaviors></span></span>  
<span data-ttu-id="5f003-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5f003-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5f003-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="5f003-107">\<behavior></span></span>  
<span data-ttu-id="5f003-108">\<routing ></span><span class="sxs-lookup"><span data-stu-id="5f003-108">\<routing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f003-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f003-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String" 
               routeOnHeadersOnly="Boolean" 
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f003-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5f003-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5f003-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5f003-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f003-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="5f003-112">Attributes</span></span>  
  
|<span data-ttu-id="5f003-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="5f003-113">Attribute</span></span>|<span data-ttu-id="5f003-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f003-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5f003-115">filterTable</span><span class="sxs-lookup"><span data-stu-id="5f003-115">filterTable</span></span>|<span data-ttu-id="5f003-116">Stringa che specifica il nome della tabella di routing contenente i filtri per la valutazione da parte del servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="5f003-116">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="5f003-117">Questo valore deve corrispondere il `name` attributo di un [ \<filterTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) elemento il [ \<filterTables >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) sezione.</span><span class="sxs-lookup"><span data-stu-id="5f003-117">This value must match the `name` attribute of a [\<filterTable>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) element in the [\<filterTables>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) section.</span></span>|  
|<span data-ttu-id="5f003-118">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="5f003-118">routeOnHeaderOnly</span></span>|<span data-ttu-id="5f003-119">Valore booleano che specifica se il filtro esaminerà il corpo del messaggio e l'intestazione oppure solo l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="5f003-119">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="5f003-120">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="5f003-120">The default is `true`.</span></span>|  
|<span data-ttu-id="5f003-121">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="5f003-121">soapProcessingEnabled</span></span>|<span data-ttu-id="5f003-122">Valore booleano che specifica se è necessario che si verifichi l'elaborazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="5f003-122">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f003-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5f003-123">Child Elements</span></span>  
 <span data-ttu-id="5f003-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5f003-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5f003-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5f003-125">Parent Elements</span></span>  
  
|<span data-ttu-id="5f003-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f003-126">Element</span></span>|<span data-ttu-id="5f003-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f003-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f003-128">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5f003-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5f003-129">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="5f003-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f003-130">Note</span><span class="sxs-lookup"><span data-stu-id="5f003-130">Remarks</span></span>  
 <span data-ttu-id="5f003-131">Quando viene aggiunto alla configurazione del comportamento del servizio, questo elemento di configurazione abilita il routing del servizio.</span><span class="sxs-lookup"><span data-stu-id="5f003-131">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="5f003-132">È possibile specificare la tabella di routing effettiva per l'uso da parte del servizio in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="5f003-132">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="5f003-133">L'utilizzo di questa sezione di configurazione consente di modificare le impostazioni di routing non appena cambia il modello di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5f003-133">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="5f003-134">In fase di esecuzione è possibile registrare l'estensione di routing personalizzata con le nuove impostazioni del routing e il servizio di routing inizierà a utilizzare le informazioni di configurazione aggiornate per i nuovi messaggi e sessioni, mentre per i messaggi e le sessioni in corso continueranno a essere utilizzate le regole implementate al momento dell'avvio.</span><span class="sxs-lookup"><span data-stu-id="5f003-134">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="5f003-135">In questo modo è possibile eseguire la riconfigurazione indipendente dalla sessione e senza riciclo del servizio di routing in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5f003-135">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
  

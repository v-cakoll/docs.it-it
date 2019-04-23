---
title: <routing> di <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: b7a9be18395ef8878900d754b5aa5afdeee0cff8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202508"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="ff617-102">\<routing > di \<serviceBehavior ></span><span class="sxs-lookup"><span data-stu-id="ff617-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="ff617-103">Fornisce l'accesso in fase di esecuzione al servizio di routing per consentire la modifica dinamica della configurazione di routing.</span><span class="sxs-lookup"><span data-stu-id="ff617-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
 <span data-ttu-id="ff617-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ff617-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ff617-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ff617-105">\<behaviors></span></span>  
<span data-ttu-id="ff617-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ff617-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ff617-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ff617-107">\<behavior></span></span>  
<span data-ttu-id="ff617-108">\<routing></span><span class="sxs-lookup"><span data-stu-id="ff617-108">\<routing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff617-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff617-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff617-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ff617-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ff617-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ff617-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff617-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="ff617-112">Attributes</span></span>  
  
|<span data-ttu-id="ff617-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="ff617-113">Attribute</span></span>|<span data-ttu-id="ff617-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff617-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ff617-115">filterTable</span><span class="sxs-lookup"><span data-stu-id="ff617-115">filterTable</span></span>|<span data-ttu-id="ff617-116">Stringa che specifica il nome della tabella di routing contenente i filtri per la valutazione da parte del servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="ff617-116">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="ff617-117">Questo valore deve corrispondere il `name` attributo di un [ \<filterTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) elemento il [ \<filterTables >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) sezione.</span><span class="sxs-lookup"><span data-stu-id="ff617-117">This value must match the `name` attribute of a [\<filterTable>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) element in the [\<filterTables>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) section.</span></span>|  
|<span data-ttu-id="ff617-118">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="ff617-118">routeOnHeaderOnly</span></span>|<span data-ttu-id="ff617-119">Valore booleano che specifica se il filtro esaminerà il corpo del messaggio e l'intestazione oppure solo l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="ff617-119">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="ff617-120">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="ff617-120">The default is `true`.</span></span>|  
|<span data-ttu-id="ff617-121">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="ff617-121">soapProcessingEnabled</span></span>|<span data-ttu-id="ff617-122">Valore booleano che specifica se è necessario che si verifichi l'elaborazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="ff617-122">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff617-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ff617-123">Child Elements</span></span>  
 <span data-ttu-id="ff617-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ff617-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff617-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ff617-125">Parent Elements</span></span>  
  
|<span data-ttu-id="ff617-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff617-126">Element</span></span>|<span data-ttu-id="ff617-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff617-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff617-128">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ff617-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ff617-129">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="ff617-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff617-130">Note</span><span class="sxs-lookup"><span data-stu-id="ff617-130">Remarks</span></span>  
 <span data-ttu-id="ff617-131">Quando viene aggiunto alla configurazione del comportamento del servizio, questo elemento di configurazione abilita il routing del servizio.</span><span class="sxs-lookup"><span data-stu-id="ff617-131">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="ff617-132">È possibile specificare la tabella di routing effettiva per l'uso da parte del servizio in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="ff617-132">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="ff617-133">L'uso di questa sezione di configurazione consente di modificare le impostazioni di routing non appena cambia il modello di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ff617-133">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="ff617-134">In fase di esecuzione è possibile registrare l'estensione di routing personalizzata con le nuove impostazioni del routing e il servizio di routing inizierà a utilizzare le informazioni di configurazione aggiornate per i nuovi messaggi e sessioni, mentre per i messaggi e le sessioni in corso continueranno a essere utilizzate le regole implementate al momento dell'avvio.</span><span class="sxs-lookup"><span data-stu-id="ff617-134">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="ff617-135">In questo modo è possibile eseguire la riconfigurazione indipendente dalla sessione e senza riciclo del servizio di routing in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ff617-135">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  

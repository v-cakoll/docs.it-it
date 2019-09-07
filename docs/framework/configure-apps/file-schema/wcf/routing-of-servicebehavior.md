---
title: <routing> di <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 0998f4fc61de7099879ba6e122eed1e64588baec
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397738"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="2da25-102">\<> di routing \<di ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="2da25-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="2da25-103">Fornisce l'accesso in fase di esecuzione al servizio di routing per consentire la modifica dinamica della configurazione di routing.</span><span class="sxs-lookup"><span data-stu-id="2da25-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
<span data-ttu-id="2da25-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2da25-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2da25-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2da25-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2da25-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2da25-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="2da25-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2da25-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="2da25-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2da25-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="2da25-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di routing**</span><span class="sxs-lookup"><span data-stu-id="2da25-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2da25-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2da25-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2da25-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2da25-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2da25-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2da25-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2da25-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="2da25-113">Attributes</span></span>  
  
|<span data-ttu-id="2da25-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="2da25-114">Attribute</span></span>|<span data-ttu-id="2da25-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2da25-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2da25-116">filterTable</span><span class="sxs-lookup"><span data-stu-id="2da25-116">filterTable</span></span>|<span data-ttu-id="2da25-117">Stringa che specifica il nome della tabella di routing contenente i filtri per la valutazione da parte del servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="2da25-117">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="2da25-118">Questo valore deve corrispondere all' `name` attributo di un [ \<elemento > FilterTable](filtertable.md) nella [ \<sezione filterTables >](filtertables.md) .</span><span class="sxs-lookup"><span data-stu-id="2da25-118">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="2da25-119">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="2da25-119">routeOnHeaderOnly</span></span>|<span data-ttu-id="2da25-120">Valore booleano che specifica se il filtro esaminerà il corpo del messaggio e l'intestazione oppure solo l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="2da25-120">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="2da25-121">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="2da25-121">The default is `true`.</span></span>|  
|<span data-ttu-id="2da25-122">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="2da25-122">soapProcessingEnabled</span></span>|<span data-ttu-id="2da25-123">Valore booleano che specifica se è necessario che si verifichi l'elaborazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="2da25-123">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2da25-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2da25-124">Child Elements</span></span>  
 <span data-ttu-id="2da25-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2da25-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2da25-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2da25-126">Parent Elements</span></span>  
  
|<span data-ttu-id="2da25-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="2da25-127">Element</span></span>|<span data-ttu-id="2da25-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2da25-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2da25-129">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2da25-129">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="2da25-130">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="2da25-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2da25-131">Note</span><span class="sxs-lookup"><span data-stu-id="2da25-131">Remarks</span></span>  
 <span data-ttu-id="2da25-132">Quando viene aggiunto alla configurazione del comportamento del servizio, questo elemento di configurazione abilita il routing del servizio.</span><span class="sxs-lookup"><span data-stu-id="2da25-132">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="2da25-133">È possibile specificare la tabella di routing effettiva per l'uso da parte del servizio in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="2da25-133">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="2da25-134">L'uso di questa sezione di configurazione consente di modificare le impostazioni di routing non appena cambia il modello di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2da25-134">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="2da25-135">In fase di esecuzione è possibile registrare l'estensione di routing personalizzata con le nuove impostazioni del routing e il servizio di routing inizierà a utilizzare le informazioni di configurazione aggiornate per i nuovi messaggi e sessioni, mentre per i messaggi e le sessioni in corso continueranno a essere utilizzate le regole implementate al momento dell'avvio.</span><span class="sxs-lookup"><span data-stu-id="2da25-135">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="2da25-136">In questo modo è possibile eseguire la riconfigurazione indipendente dalla sessione e senza riciclo del servizio di routing in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2da25-136">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  

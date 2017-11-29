---
title: '&lt;associazioni&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed672ee918ad969feb8be6d20c9206e6b5d12278
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltbindingsgt"></a><span data-ttu-id="b0a65-102">&lt;associazioni&gt;</span><span class="sxs-lookup"><span data-stu-id="b0a65-102">&lt;bindings&gt;</span></span>
<span data-ttu-id="b0a65-103">Questa sezione contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="b0a65-103">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="b0a65-104">Ogni voce è un elemento `binding` che può essere identificato dal relativo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="b0a65-104">Each entry is a `binding` element that can be identified by its unique `name`.</span></span> <span data-ttu-id="b0a65-105">I servizi usano le associazioni collegandole mediante l'oggetto `name`.</span><span class="sxs-lookup"><span data-stu-id="b0a65-105">Services use bindings by linking them using the `name`.</span></span> <span data-ttu-id="b0a65-106">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="b0a65-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b0a65-107">Per ulteriori informazioni sulla configurazione predefinita e senza nome associazioni e comportamenti, vedere [configurazione semplificata](../../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="b0a65-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="system-provided-binding"></a><span data-ttu-id="b0a65-108">Associazione fornita dal sistema</span><span class="sxs-lookup"><span data-stu-id="b0a65-108">System-Provided Binding</span></span>  
 <span data-ttu-id="b0a65-109">Le associazioni fornite dal sistema nascondono la complessità dello stack di messaggistica WCF.</span><span class="sxs-lookup"><span data-stu-id="b0a65-109">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="b0a65-110">Le applicazioni che usano associazioni fornite dal sistema non richiedono il controllo completo sullo stack.</span><span class="sxs-lookup"><span data-stu-id="b0a65-110">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="b0a65-111">Gli attributi esposti in ciascuna associazione fornita dal sistema sono quelli più appropriati per lo scenario di utilizzo gestito dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="b0a65-111">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>  
  
 <span data-ttu-id="b0a65-112">La sezione di configurazione di ciascuna associazione fornita dal sistema può definire varie configurazioni usate per configurare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="b0a65-112">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="b0a65-113">Ogni configurazione è identificata da un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="b0a65-113">Each configuration is identified by a unique name.</span></span>  
  
 <span data-ttu-id="b0a65-114">Non è possibile aggiungere elementi o attributi a un'associazione fornita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="b0a65-114">It is not possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="b0a65-115">A tal scopo, è necessario implementare un'associazione personalizzata come descritto nella sezione "Associazione personalizzata" di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b0a65-115">To do so, you should implement a custom binding as described in the "Custom Binding" section of this topic.</span></span> <span data-ttu-id="b0a65-116">È possibile definire un'associazione personalizzata che riproduce perfettamente un'associazione fornita dal sistema e aggiunge alcune impostazioni sulle quali è desiderabile che l'applicazione utente abbia il controllo.</span><span class="sxs-lookup"><span data-stu-id="b0a65-116">It is possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  
  
 <span data-ttu-id="b0a65-117">Per un elenco di associazioni fornite dal sistema, vedere [associazioni fornite dal sistema](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="b0a65-117">For a list of system-provided bindings, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
## <a name="custom-binding"></a><span data-ttu-id="b0a65-118">Associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="b0a65-118">Custom Binding</span></span>  
 <span data-ttu-id="b0a65-119">Le associazioni personalizzate forniscono il controllo completo dello stack dei messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="b0a65-119">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="b0a65-120">Un'associazione singola definisce lo stack dei messaggi specificando gli elementi di configurazione per gli elementi dello stack nell'ordine in cui vengono visualizzati nello stack.</span><span class="sxs-lookup"><span data-stu-id="b0a65-120">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="b0a65-121">Ogni elemento definisce e configura un elemento dello stack.</span><span class="sxs-lookup"><span data-stu-id="b0a65-121">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="b0a65-122">In ogni associazione personalizzata deve essere presente un solo elemento `transport`.</span><span class="sxs-lookup"><span data-stu-id="b0a65-122">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="b0a65-123">Senza questo elemento, lo stack dei messaggi è incompleto.</span><span class="sxs-lookup"><span data-stu-id="b0a65-123">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="b0a65-124">L'ordine in cui gli elementi vengono visualizzati nello stack è importante, perché è l'ordine in cui le operazioni vengono applicate al messaggio.</span><span class="sxs-lookup"><span data-stu-id="b0a65-124">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="b0a65-125">L'ordine necessario per gli elementi dello stack è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b0a65-125">The required order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="b0a65-126">Transazioni (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="b0a65-126">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="b0a65-127">Messaggistica affidabile (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="b0a65-127">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="b0a65-128">Sicurezza (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="b0a65-128">Security (optional)</span></span>  
  
4.  <span data-ttu-id="b0a65-129">Codificatore</span><span class="sxs-lookup"><span data-stu-id="b0a65-129">Encoder</span></span>  
  
5.  <span data-ttu-id="b0a65-130">Trasporto</span><span class="sxs-lookup"><span data-stu-id="b0a65-130">Transport</span></span>  
  
 <span data-ttu-id="b0a65-131">Le associazioni personalizzate sono identificate dal relativo attributo `name`.</span><span class="sxs-lookup"><span data-stu-id="b0a65-131">Custom bindings are identified by their `name` attribute.</span></span> <span data-ttu-id="b0a65-132">Per ulteriori informazioni sulle associazioni personalizzate, vedere [associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="b0a65-132">For more information on custom bindings, see [Custom Bindings](../../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a65-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0a65-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BindingsSection>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 [<span data-ttu-id="b0a65-134">Associazioni</span><span class="sxs-lookup"><span data-stu-id="b0a65-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b0a65-135">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="b0a65-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="b0a65-136">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b0a65-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="b0a65-137">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="b0a65-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

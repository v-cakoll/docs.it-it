---
title: '&lt;associazione&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 666183d6-4d1f-45c7-ac64-bdf93ee8f36f
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 874a3766a64a9abb7c35efd5ac0a0f698707281e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltbindinggt"></a><span data-ttu-id="002b3-102">&lt;associazione&gt;</span><span class="sxs-lookup"><span data-stu-id="002b3-102">&lt;binding&gt;</span></span>
<span data-ttu-id="002b3-103">È possibile usare l'elemento di `binding` per configurare differenti tipi di associazione predefiniti forniti da Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="002b3-103">You can use the `binding` element to configure different types of predefined bindings provided by Windows Communication Foundation (WCF).</span></span>  
  
## <a name="system-provided-binding"></a><span data-ttu-id="002b3-104">Binding fornito dal sistema</span><span class="sxs-lookup"><span data-stu-id="002b3-104">System-Provided Binding</span></span>  
 <span data-ttu-id="002b3-105">Le associazioni fornite dal sistema nascondono la complessità dello stack di messaggistica WCF.</span><span class="sxs-lookup"><span data-stu-id="002b3-105">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="002b3-106">Le applicazioni che usano associazioni fornite dal sistema non richiedono il controllo completo sullo stack.</span><span class="sxs-lookup"><span data-stu-id="002b3-106">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="002b3-107">Gli attributi esposti in ciascuna associazione fornita dal sistema sono quelli più appropriati per lo scenario di utilizzo gestito dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="002b3-107">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>  
  
 <span data-ttu-id="002b3-108">La sezione di configurazione di ciascuna associazione fornita dal sistema può definire varie configurazioni usate per configurare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="002b3-108">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="002b3-109">Ogni configurazione è identificata da un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="002b3-109">Each configuration is identified by a unique name.</span></span>  
  
 <span data-ttu-id="002b3-110">Non è possibile aggiungere elementi o attributi a un'associazione fornita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="002b3-110">It is not possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="002b3-111">A tal scopo, è necessario implementare un'associazione personalizzata come descritto nella sezione "Associazione personalizzata" di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="002b3-111">To do so, you should implement a custom binding as described in the "Custom Binding" section of this topic.</span></span> <span data-ttu-id="002b3-112">È possibile definire un'associazione personalizzata che riproduce perfettamente un'associazione fornita dal sistema e aggiunge alcune impostazioni sulle quali è desiderabile che l'applicazione utente abbia il controllo.</span><span class="sxs-lookup"><span data-stu-id="002b3-112">It is possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  
  
## <a name="custom-binding"></a><span data-ttu-id="002b3-113">Associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="002b3-113">Custom Binding</span></span>  
 <span data-ttu-id="002b3-114">Le associazioni personalizzate forniscono il controllo completo dello stack dei messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="002b3-114">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="002b3-115">Un'associazione singola definisce lo stack dei messaggi specificando gli elementi di configurazione per gli elementi dello stack nell'ordine in cui vengono visualizzati nello stack.</span><span class="sxs-lookup"><span data-stu-id="002b3-115">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="002b3-116">Ogni elemento definisce e configura un elemento dello stack.</span><span class="sxs-lookup"><span data-stu-id="002b3-116">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="002b3-117">In ogni associazione personalizzata deve essere presente un solo elemento `transport`.</span><span class="sxs-lookup"><span data-stu-id="002b3-117">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="002b3-118">Senza questo elemento, lo stack dei messaggi è incompleto.</span><span class="sxs-lookup"><span data-stu-id="002b3-118">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="002b3-119">L'ordine in cui gli elementi vengono visualizzati nello stack è importante, perché è l'ordine in cui le operazioni vengono applicate al messaggio.</span><span class="sxs-lookup"><span data-stu-id="002b3-119">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="002b3-120">L'ordine consigliato per gli elementi dello stack è il seguente:</span><span class="sxs-lookup"><span data-stu-id="002b3-120">The recommended order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="002b3-121">Transazioni (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="002b3-121">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="002b3-122">Messaggistica affidabile (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="002b3-122">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="002b3-123">Sicurezza (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="002b3-123">Security (optional)</span></span>  
  
4.  <span data-ttu-id="002b3-124">Codificatore</span><span class="sxs-lookup"><span data-stu-id="002b3-124">Encoder</span></span>  
  
5.  <span data-ttu-id="002b3-125">Trasporto</span><span class="sxs-lookup"><span data-stu-id="002b3-125">Transport</span></span>  
  
 <span data-ttu-id="002b3-126">Le associazioni personalizzate sono identificate dal relativo attributo `name`.</span><span class="sxs-lookup"><span data-stu-id="002b3-126">Custom bindings are identified by their `name` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="002b3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="002b3-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BindingsSection>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 [<span data-ttu-id="002b3-128">Associazioni</span><span class="sxs-lookup"><span data-stu-id="002b3-128">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="002b3-129">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="002b3-129">Custom Bindings</span></span>](../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="002b3-130">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="002b3-130">\<customBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

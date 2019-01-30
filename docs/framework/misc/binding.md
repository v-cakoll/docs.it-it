---
title: <binding>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 666183d6-4d1f-45c7-ac64-bdf93ee8f36f
ms.openlocfilehash: fb51eb1962603439b89a203eb668dfb543049170
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271473"
---
# <a name="binding"></a><span data-ttu-id="c00f4-101">\<binding></span><span class="sxs-lookup"><span data-stu-id="c00f4-101">\<binding></span></span>
<span data-ttu-id="c00f4-102">È possibile usare l'elemento di `binding` per configurare differenti tipi di associazione predefiniti forniti da Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c00f4-102">You can use the `binding` element to configure different types of predefined bindings provided by Windows Communication Foundation (WCF).</span></span>  
  
## <a name="system-provided-binding"></a><span data-ttu-id="c00f4-103">Binding fornito dal sistema</span><span class="sxs-lookup"><span data-stu-id="c00f4-103">System-Provided Binding</span></span>  
 <span data-ttu-id="c00f4-104">Le associazioni fornite dal sistema nascondono la complessità dello stack di messaggistica WCF.</span><span class="sxs-lookup"><span data-stu-id="c00f4-104">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="c00f4-105">Le applicazioni che usano associazioni fornite dal sistema non richiedono il controllo completo sullo stack.</span><span class="sxs-lookup"><span data-stu-id="c00f4-105">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="c00f4-106">Gli attributi esposti in ciascuna associazione fornita dal sistema sono quelli più appropriati per lo scenario di utilizzo gestito dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="c00f4-106">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>  
  
 <span data-ttu-id="c00f4-107">La sezione di configurazione di ciascuna associazione fornita dal sistema può definire varie configurazioni usate per configurare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="c00f4-107">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="c00f4-108">Ogni configurazione è identificata da un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="c00f4-108">Each configuration is identified by a unique name.</span></span>  
  
 <span data-ttu-id="c00f4-109">Non è possibile aggiungere elementi o attributi a un'associazione fornita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c00f4-109">It is not possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="c00f4-110">A tal scopo, è necessario implementare un'associazione personalizzata come descritto nella sezione "Associazione personalizzata" di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c00f4-110">To do so, you should implement a custom binding as described in the "Custom Binding" section of this topic.</span></span> <span data-ttu-id="c00f4-111">È possibile definire un'associazione personalizzata che riproduce perfettamente un'associazione fornita dal sistema e aggiunge alcune impostazioni sulle quali è desiderabile che l'applicazione utente abbia il controllo.</span><span class="sxs-lookup"><span data-stu-id="c00f4-111">It is possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  
  
## <a name="custom-binding"></a><span data-ttu-id="c00f4-112">Associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="c00f4-112">Custom Binding</span></span>  
 <span data-ttu-id="c00f4-113">Le associazioni personalizzate forniscono il controllo completo dello stack dei messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="c00f4-113">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="c00f4-114">Un'associazione singola definisce lo stack dei messaggi specificando gli elementi di configurazione per gli elementi dello stack nell'ordine in cui vengono visualizzati nello stack.</span><span class="sxs-lookup"><span data-stu-id="c00f4-114">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="c00f4-115">Ogni elemento definisce e configura un elemento dello stack.</span><span class="sxs-lookup"><span data-stu-id="c00f4-115">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="c00f4-116">In ogni associazione personalizzata deve essere presente un solo elemento `transport`.</span><span class="sxs-lookup"><span data-stu-id="c00f4-116">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="c00f4-117">Senza questo elemento, lo stack dei messaggi è incompleto.</span><span class="sxs-lookup"><span data-stu-id="c00f4-117">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="c00f4-118">L'ordine in cui gli elementi vengono visualizzati nello stack è importante, perché è l'ordine in cui le operazioni vengono applicate al messaggio.</span><span class="sxs-lookup"><span data-stu-id="c00f4-118">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="c00f4-119">L'ordine consigliato per gli elementi dello stack è il seguente:</span><span class="sxs-lookup"><span data-stu-id="c00f4-119">The recommended order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="c00f4-120">Transazioni (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="c00f4-120">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="c00f4-121">Messaggistica affidabile (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="c00f4-121">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="c00f4-122">Sicurezza (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="c00f4-122">Security (optional)</span></span>  
  
4.  <span data-ttu-id="c00f4-123">Codificatore</span><span class="sxs-lookup"><span data-stu-id="c00f4-123">Encoder</span></span>  
  
5.  <span data-ttu-id="c00f4-124">Trasporto</span><span class="sxs-lookup"><span data-stu-id="c00f4-124">Transport</span></span>  
  
 <span data-ttu-id="c00f4-125">Le associazioni personalizzate sono identificate dal relativo attributo `name`.</span><span class="sxs-lookup"><span data-stu-id="c00f4-125">Custom bindings are identified by their `name` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00f4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c00f4-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- [<span data-ttu-id="c00f4-127">Associazioni</span><span class="sxs-lookup"><span data-stu-id="c00f4-127">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="c00f4-128">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="c00f4-128">Custom Bindings</span></span>](../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c00f4-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c00f4-129">\<customBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

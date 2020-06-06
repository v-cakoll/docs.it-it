---
title: <bindings>
ms.date: 01/22/2018
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: fe8f620668e35183890b8bba1f254a74c962f8d3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139670"
---
# \<bindings>

<span data-ttu-id="1ecbc-101">È possibile utilizzare l' `bindings` elemento per configurare una raccolta di associazioni standard e personalizzate per Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1ecbc-101">You can use the `bindings` element to configure a collection of standard and custom bindings for Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="1ecbc-102">Ogni voce è un elemento `binding` che può essere identificato dal relativo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-102">Each entry is a `binding` element that can be identified by its unique `name`.</span></span> <span data-ttu-id="1ecbc-103">I servizi usano le associazioni collegandole mediante l'oggetto `name`.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-103">Services use bindings by linking them using the `name`.</span></span> <span data-ttu-id="1ecbc-104">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-104">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="1ecbc-105">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="1ecbc-105">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="system-provided-bindings"></a><span data-ttu-id="1ecbc-106">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="1ecbc-106">System-provided bindings</span></span>

<span data-ttu-id="1ecbc-107">Le associazioni fornite dal sistema nascondono la complessità dello stack di messaggistica WCF.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-107">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="1ecbc-108">Le applicazioni che usano associazioni fornite dal sistema non richiedono il controllo completo sullo stack.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-108">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="1ecbc-109">Gli attributi esposti in ciascuna associazione fornita dal sistema sono quelli più appropriati per lo scenario di utilizzo gestito dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-109">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>

<span data-ttu-id="1ecbc-110">La sezione di configurazione di ciascuna associazione fornita dal sistema può definire varie configurazioni usate per configurare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-110">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="1ecbc-111">Ogni configurazione è identificata da un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-111">Each configuration is identified by a unique name.</span></span>

<span data-ttu-id="1ecbc-112">Non è possibile aggiungere elementi o attributi a un'associazione fornita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-112">It isn't possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="1ecbc-113">A tale scopo, è necessario implementare un'associazione personalizzata come descritto nella sezione [associazioni personalizzate](#custom-bindings) .</span><span class="sxs-lookup"><span data-stu-id="1ecbc-113">To do so, you should implement a custom binding as described in the [Custom bindings](#custom-bindings) section.</span></span> <span data-ttu-id="1ecbc-114">È possibile definire un'associazione personalizzata che simula perfettamente un'associazione fornita dal sistema e aggiunge alcune impostazioni che l'applicazione utente vuole avere il controllo.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-114">It's possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  

<span data-ttu-id="1ecbc-115">Per un elenco delle associazioni fornite dal sistema, vedere [associazioni fornite dal sistema](../../../wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="1ecbc-115">For a list of system-provided bindings, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>

## <a name="custom-bindings"></a><span data-ttu-id="1ecbc-116">Binding personalizzati</span><span class="sxs-lookup"><span data-stu-id="1ecbc-116">Custom bindings</span></span>

<span data-ttu-id="1ecbc-117">Le associazioni personalizzate forniscono il controllo completo dello stack dei messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-117">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="1ecbc-118">Un'associazione singola definisce lo stack dei messaggi specificando gli elementi di configurazione per gli elementi dello stack nell'ordine in cui vengono visualizzati nello stack.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-118">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="1ecbc-119">Ogni elemento definisce e configura un elemento dello stack.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-119">Each element defines and configures one element of the stack.</span></span> <span data-ttu-id="1ecbc-120">In ogni associazione personalizzata deve essere presente un solo elemento `transport`.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-120">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="1ecbc-121">Senza questo elemento, lo stack dei messaggi è incompleto.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-121">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="1ecbc-122">L'ordine in cui gli elementi vengono visualizzati nello stack è importante, perché è l'ordine in cui le operazioni vengono applicate al messaggio.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-122">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="1ecbc-123">L'ordine necessario per gli elementi dello stack è il seguente:</span><span class="sxs-lookup"><span data-stu-id="1ecbc-123">The required order of stack elements is the following:</span></span>  

1. <span data-ttu-id="1ecbc-124">Transazioni (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="1ecbc-124">Transactions (optional)</span></span>  

2. <span data-ttu-id="1ecbc-125">Messaggistica affidabile (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="1ecbc-125">Reliable messaging (optional)</span></span>  

3. <span data-ttu-id="1ecbc-126">Sicurezza (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="1ecbc-126">Security (optional)</span></span>  

4. <span data-ttu-id="1ecbc-127">Codificatore</span><span class="sxs-lookup"><span data-stu-id="1ecbc-127">Encoder</span></span>  

5. <span data-ttu-id="1ecbc-128">Trasporto</span><span class="sxs-lookup"><span data-stu-id="1ecbc-128">Transport</span></span>  

 <span data-ttu-id="1ecbc-129">Le associazioni personalizzate sono identificate dal relativo attributo `name`.</span><span class="sxs-lookup"><span data-stu-id="1ecbc-129">Custom bindings are identified by their `name` attribute.</span></span> <span data-ttu-id="1ecbc-130">Per ulteriori informazioni sulle associazioni personalizzate, vedere [associazioni personalizzate](../../../wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="1ecbc-130">For more information on custom bindings, see [Custom Bindings](../../../wcf/extending/custom-bindings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1ecbc-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1ecbc-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>
- [<span data-ttu-id="1ecbc-132">Binding</span><span class="sxs-lookup"><span data-stu-id="1ecbc-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1ecbc-133">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1ecbc-133">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)

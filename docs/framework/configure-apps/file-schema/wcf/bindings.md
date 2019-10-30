---
title: <bindings>
ms.date: 01/22/2018
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: cd4c4cd4c1bfe7920c438eddc15aba00d995b8cb
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039613"
---
# <a name="bindings"></a><span data-ttu-id="123f4-101">associazioni di \<</span><span class="sxs-lookup"><span data-stu-id="123f4-101">\<bindings></span></span>

<span data-ttu-id="123f4-102">È possibile utilizzare l'elemento `bindings` per configurare una raccolta di associazioni standard e personalizzate per Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="123f4-102">You can use the `bindings` element to configure a collection of standard and custom bindings for Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="123f4-103">Ogni voce è un elemento `binding` che può essere identificato dal relativo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="123f4-103">Each entry is a `binding` element that can be identified by its unique `name`.</span></span> <span data-ttu-id="123f4-104">I servizi usano le associazioni collegandole mediante l'oggetto `name`.</span><span class="sxs-lookup"><span data-stu-id="123f4-104">Services use bindings by linking them using the `name`.</span></span> <span data-ttu-id="123f4-105">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="123f4-105">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="123f4-106">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="123f4-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="system-provided-bindings"></a><span data-ttu-id="123f4-107">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="123f4-107">System-provided bindings</span></span>

<span data-ttu-id="123f4-108">Le associazioni fornite dal sistema nascondono la complessità dello stack di messaggistica WCF.</span><span class="sxs-lookup"><span data-stu-id="123f4-108">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="123f4-109">Le applicazioni che usano associazioni fornite dal sistema non richiedono il controllo completo sullo stack.</span><span class="sxs-lookup"><span data-stu-id="123f4-109">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="123f4-110">Gli attributi esposti in ciascuna associazione fornita dal sistema sono quelli più appropriati per lo scenario di utilizzo gestito dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="123f4-110">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>

<span data-ttu-id="123f4-111">La sezione di configurazione di ciascuna associazione fornita dal sistema può definire varie configurazioni usate per configurare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="123f4-111">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="123f4-112">Ogni configurazione è identificata da un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="123f4-112">Each configuration is identified by a unique name.</span></span>

<span data-ttu-id="123f4-113">Non è possibile aggiungere elementi o attributi a un'associazione fornita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="123f4-113">It isn't possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="123f4-114">A tale scopo, è necessario implementare un'associazione personalizzata come descritto nella sezione [associazioni personalizzate](#custom-bindings) .</span><span class="sxs-lookup"><span data-stu-id="123f4-114">To do so, you should implement a custom binding as described in the [Custom bindings](#custom-bindings) section.</span></span> <span data-ttu-id="123f4-115">È possibile definire un'associazione personalizzata che simula perfettamente un'associazione fornita dal sistema e aggiunge alcune impostazioni che l'applicazione utente vuole avere il controllo.</span><span class="sxs-lookup"><span data-stu-id="123f4-115">It's possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  

<span data-ttu-id="123f4-116">Per un elenco delle associazioni fornite dal sistema, vedere [associazioni fornite dal sistema](../../../wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="123f4-116">For a list of system-provided bindings, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>

## <a name="custom-bindings"></a><span data-ttu-id="123f4-117">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="123f4-117">Custom bindings</span></span>

<span data-ttu-id="123f4-118">Le associazioni personalizzate forniscono il controllo completo dello stack dei messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="123f4-118">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="123f4-119">Un'associazione singola definisce lo stack dei messaggi specificando gli elementi di configurazione per gli elementi dello stack nell'ordine in cui vengono visualizzati nello stack.</span><span class="sxs-lookup"><span data-stu-id="123f4-119">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="123f4-120">Ogni elemento definisce e configura un elemento dello stack.</span><span class="sxs-lookup"><span data-stu-id="123f4-120">Each element defines and configures one element of the stack.</span></span> <span data-ttu-id="123f4-121">In ogni associazione personalizzata deve essere presente un solo elemento `transport`.</span><span class="sxs-lookup"><span data-stu-id="123f4-121">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="123f4-122">Senza questo elemento, lo stack dei messaggi è incompleto.</span><span class="sxs-lookup"><span data-stu-id="123f4-122">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="123f4-123">L'ordine in cui gli elementi vengono visualizzati nello stack è importante, perché è l'ordine in cui le operazioni vengono applicate al messaggio.</span><span class="sxs-lookup"><span data-stu-id="123f4-123">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="123f4-124">L'ordine necessario per gli elementi dello stack è il seguente:</span><span class="sxs-lookup"><span data-stu-id="123f4-124">The required order of stack elements is the following:</span></span>  

1. <span data-ttu-id="123f4-125">Transazioni (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="123f4-125">Transactions (optional)</span></span>  

2. <span data-ttu-id="123f4-126">Messaggistica affidabile (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="123f4-126">Reliable messaging (optional)</span></span>  

3. <span data-ttu-id="123f4-127">Sicurezza (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="123f4-127">Security (optional)</span></span>  

4. <span data-ttu-id="123f4-128">Codificatore</span><span class="sxs-lookup"><span data-stu-id="123f4-128">Encoder</span></span>  

5. <span data-ttu-id="123f4-129">Trasporto</span><span class="sxs-lookup"><span data-stu-id="123f4-129">Transport</span></span>  

 <span data-ttu-id="123f4-130">Le associazioni personalizzate sono identificate dal relativo attributo `name`.</span><span class="sxs-lookup"><span data-stu-id="123f4-130">Custom bindings are identified by their `name` attribute.</span></span> <span data-ttu-id="123f4-131">Per ulteriori informazioni sulle associazioni personalizzate, vedere [associazioni personalizzate](../../../wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="123f4-131">For more information on custom bindings, see [Custom Bindings](../../../wcf/extending/custom-bindings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="123f4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="123f4-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>
- [<span data-ttu-id="123f4-133">Associazioni</span><span class="sxs-lookup"><span data-stu-id="123f4-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="123f4-134">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="123f4-134">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="123f4-135">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="123f4-135">\<customBinding></span></span>](custombinding.md)

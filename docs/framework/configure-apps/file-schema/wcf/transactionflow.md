---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 8247dd62f4dda853487fe52f00f8f548b627c075
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399401"
---
# <a name="transactionflow"></a><span data-ttu-id="e2c0e-101">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="e2c0e-101">\<transactionFlow></span></span>
<span data-ttu-id="e2c0e-102">Specifica il supporto del flusso di transazione per l'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e2c0e-102">Specifies transaction flow support for the custom binding.</span></span>  
  
<span data-ttu-id="e2c0e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e2c0e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e2c0e-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e2c0e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e2c0e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e2c0e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e2c0e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="e2c0e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="e2c0e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="e2c0e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e2c0e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> transactionFlow**</span><span class="sxs-lookup"><span data-stu-id="e2c0e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2c0e-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2c0e-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2c0e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e2c0e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e2c0e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e2c0e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2c0e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="e2c0e-112">Attributes</span></span>  
  
|<span data-ttu-id="e2c0e-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="e2c0e-113">Attribute</span></span>|<span data-ttu-id="e2c0e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2c0e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e2c0e-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="e2c0e-115">transactionProtocol</span></span>|<span data-ttu-id="e2c0e-116">Specifica il protocollo di transazione da usare.</span><span class="sxs-lookup"><span data-stu-id="e2c0e-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="e2c0e-117">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="e2c0e-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e2c0e-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="e2c0e-118">-   OleTransactions</span></span><br /><span data-ttu-id="e2c0e-119">-   WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="e2c0e-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="e2c0e-120">L'impostazione predefinita è OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="e2c0e-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="e2c0e-121">L'attributo è di tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="e2c0e-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2c0e-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e2c0e-122">Child Elements</span></span>  
 <span data-ttu-id="e2c0e-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e2c0e-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2c0e-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e2c0e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e2c0e-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2c0e-125">Element</span></span>|<span data-ttu-id="e2c0e-126">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e2c0e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2c0e-127">\<binding></span><span class="sxs-lookup"><span data-stu-id="e2c0e-127">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="e2c0e-128">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e2c0e-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2c0e-129">Note</span><span class="sxs-lookup"><span data-stu-id="e2c0e-129">Remarks</span></span>  
 <span data-ttu-id="e2c0e-130">Questo elemento consente di abilitare o disabilitare il flusso delle transazioni in arrivo nelle impostazioni di associazione di un endpoint, nonché di specificare il formato del protocollo di transazione desiderato per le transazioni in arrivo.</span><span class="sxs-lookup"><span data-stu-id="e2c0e-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="e2c0e-131">Per altre informazioni sull'uso di questo elemento di configurazione, vedere [configurazione delle transazioni ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md) e [Abilitazione del flusso delle transazioni](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="e2c0e-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="e2c0e-132">Quando viene usato il protocollo `OleTransactions` per propagare transazioni da endpoint a endpoint, il timeout della transazione può essere perso se l'endpoint di destinazione tenta di eseguire nuovamente la propagazione usando un protocollo diverso da `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="e2c0e-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="e2c0e-133">Ciò può provocare un ritardo del timeout di tutti i nodi di livello inferiore dopo l'hop OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="e2c0e-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2c0e-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2c0e-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e2c0e-135">Configurazione delle transazioni ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e2c0e-135">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="e2c0e-136">Attivazione del flusso delle transazioni</span><span class="sxs-lookup"><span data-stu-id="e2c0e-136">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="e2c0e-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="e2c0e-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e2c0e-138">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="e2c0e-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e2c0e-139">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="e2c0e-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e2c0e-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e2c0e-140">\<customBinding></span></span>](custombinding.md)

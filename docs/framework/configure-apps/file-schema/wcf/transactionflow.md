---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: f5bcd142fb2b032ea179bcbba68fee53b98d2d77
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736309"
---
# <a name="transactionflow"></a><span data-ttu-id="a3080-101">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="a3080-101">\<transactionFlow></span></span>
<span data-ttu-id="a3080-102">Specifica il supporto del flusso di transazione per l'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a3080-102">Specifies transaction flow support for the custom binding.</span></span>  
  
<span data-ttu-id="a3080-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a3080-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a3080-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a3080-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a3080-105">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="a3080-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="a3080-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="a3080-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="a3080-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="a3080-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a3080-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<transactionFlow >**</span><span class="sxs-lookup"><span data-stu-id="a3080-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3080-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3080-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3080-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a3080-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a3080-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a3080-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3080-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="a3080-112">Attributes</span></span>  
  
|<span data-ttu-id="a3080-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="a3080-113">Attribute</span></span>|<span data-ttu-id="a3080-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3080-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a3080-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="a3080-115">transactionProtocol</span></span>|<span data-ttu-id="a3080-116">Specifica il protocollo di transazione da usare.</span><span class="sxs-lookup"><span data-stu-id="a3080-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="a3080-117">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="a3080-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a3080-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="a3080-118">-   OleTransactions</span></span><br /><span data-ttu-id="a3080-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="a3080-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="a3080-120">L'impostazione predefinita è OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="a3080-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="a3080-121">L'attributo è di tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="a3080-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3080-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a3080-122">Child Elements</span></span>  
 <span data-ttu-id="a3080-123">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="a3080-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3080-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a3080-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a3080-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3080-125">Element</span></span>|<span data-ttu-id="a3080-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3080-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3080-127">\<binding ></span><span class="sxs-lookup"><span data-stu-id="a3080-127">\<binding></span></span>](bindings.md)|<span data-ttu-id="a3080-128">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a3080-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3080-129">Note</span><span class="sxs-lookup"><span data-stu-id="a3080-129">Remarks</span></span>  
 <span data-ttu-id="a3080-130">Questo elemento consente di abilitare o disabilitare il flusso delle transazioni in arrivo nelle impostazioni di associazione di un endpoint, nonché di specificare il formato del protocollo di transazione desiderato per le transazioni in arrivo.</span><span class="sxs-lookup"><span data-stu-id="a3080-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="a3080-131">Per altre informazioni sull'uso di questo elemento di configurazione, vedere [configurazione delle transazioni ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md) e [Abilitazione del flusso delle transazioni](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="a3080-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="a3080-132">Quando viene usato il protocollo `OleTransactions` per propagare transazioni da endpoint a endpoint, il timeout della transazione può essere perso se l'endpoint di destinazione tenta di eseguire nuovamente la propagazione usando un protocollo diverso da `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="a3080-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="a3080-133">Ciò può provocare un ritardo del timeout di tutti i nodi di livello inferiore dopo l'hop OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="a3080-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3080-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3080-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a3080-135">Configurazione delle transazioni ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a3080-135">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="a3080-136">Attivazione del flusso delle transazioni</span><span class="sxs-lookup"><span data-stu-id="a3080-136">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="a3080-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="a3080-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a3080-138">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="a3080-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a3080-139">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="a3080-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a3080-140">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="a3080-140">\<customBinding></span></span>](custombinding.md)

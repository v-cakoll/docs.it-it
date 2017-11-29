---
title: '&lt;transactionFlow&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8c40b3a79567ccc1ca5a83631253d3ff6ead0f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lttransactionflowgt"></a><span data-ttu-id="68f98-102">&lt;transactionFlow&gt;</span><span class="sxs-lookup"><span data-stu-id="68f98-102">&lt;transactionFlow&gt;</span></span>
<span data-ttu-id="68f98-103">Specifica il supporto del flusso di transazione per l'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="68f98-103">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="68f98-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="68f98-104">\<system.serviceModel></span></span>  
<span data-ttu-id="68f98-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="68f98-105">\<bindings></span></span>  
<span data-ttu-id="68f98-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="68f98-106">\<customBinding></span></span>  
<span data-ttu-id="68f98-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="68f98-107">\<binding></span></span>  
<span data-ttu-id="68f98-108">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="68f98-108">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68f98-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="68f98-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68f98-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="68f98-110">Attributes and Elements</span></span>  
 <span data-ttu-id="68f98-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="68f98-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68f98-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="68f98-112">Attributes</span></span>  
  
|<span data-ttu-id="68f98-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="68f98-113">Attribute</span></span>|<span data-ttu-id="68f98-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68f98-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="68f98-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="68f98-115">transactionProtocol</span></span>|<span data-ttu-id="68f98-116">Specifica il protocollo di transazione da usare.</span><span class="sxs-lookup"><span data-stu-id="68f98-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="68f98-117">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="68f98-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="68f98-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="68f98-118">-   OleTransactions</span></span><br /><span data-ttu-id="68f98-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="68f98-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="68f98-120">L'impostazione predefinita è OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="68f98-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="68f98-121">L'attributo è di tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="68f98-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68f98-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="68f98-122">Child Elements</span></span>  
 <span data-ttu-id="68f98-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="68f98-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68f98-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="68f98-124">Parent Elements</span></span>  
  
|<span data-ttu-id="68f98-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="68f98-125">Element</span></span>|<span data-ttu-id="68f98-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68f98-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68f98-127">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="68f98-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="68f98-128">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="68f98-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68f98-129">Note</span><span class="sxs-lookup"><span data-stu-id="68f98-129">Remarks</span></span>  
 <span data-ttu-id="68f98-130">Questo elemento consente di abilitare o disabilitare il flusso delle transazioni in arrivo nelle impostazioni di associazione di un endpoint, nonché di specificare il formato del protocollo di transazione desiderato per le transazioni in arrivo.</span><span class="sxs-lookup"><span data-stu-id="68f98-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="68f98-131">Per ulteriori informazioni sull'utilizzo di questo elemento di configurazione, vedere [configurazione delle transazioni ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) e [abilitazione del flusso di transazione](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="68f98-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="68f98-132">Quando viene usato il protocollo `OleTransactions` per propagare transazioni da endpoint a endpoint, il timeout della transazione può essere perso se l'endpoint di destinazione tenta di eseguire nuovamente la propagazione usando un protocollo diverso da `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="68f98-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="68f98-133">Ciò può provocare un ritardo del timeout di tutti i nodi di livello inferiore dopo l'hop OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="68f98-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68f98-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68f98-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="68f98-135">Configurazione delle transazioni ServiceModel</span><span class="sxs-lookup"><span data-stu-id="68f98-135">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 [<span data-ttu-id="68f98-136">Attivazione del flusso delle transazioni</span><span class="sxs-lookup"><span data-stu-id="68f98-136">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 [<span data-ttu-id="68f98-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="68f98-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="68f98-138">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="68f98-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="68f98-139">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="68f98-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="68f98-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="68f98-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

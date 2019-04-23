---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 626ae03d622221ab3e956bd03898b6cc30482c98
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179153"
---
# <a name="transactionflow"></a><span data-ttu-id="77247-101">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="77247-101">\<transactionFlow></span></span>
<span data-ttu-id="77247-102">Specifica il supporto del flusso di transazione per l'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="77247-102">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="77247-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="77247-103">\<system.serviceModel></span></span>  
<span data-ttu-id="77247-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="77247-104">\<bindings></span></span>  
<span data-ttu-id="77247-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="77247-105">\<customBinding></span></span>  
<span data-ttu-id="77247-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="77247-106">\<binding></span></span>  
<span data-ttu-id="77247-107">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="77247-107">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77247-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77247-108">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77247-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="77247-109">Attributes and Elements</span></span>  
 <span data-ttu-id="77247-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="77247-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77247-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="77247-111">Attributes</span></span>  
  
|<span data-ttu-id="77247-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="77247-112">Attribute</span></span>|<span data-ttu-id="77247-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77247-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77247-114">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="77247-114">transactionProtocol</span></span>|<span data-ttu-id="77247-115">Specifica il protocollo di transazione da usare.</span><span class="sxs-lookup"><span data-stu-id="77247-115">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="77247-116">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="77247-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="77247-117">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="77247-117">-   OleTransactions</span></span><br /><span data-ttu-id="77247-118">-   WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="77247-118">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="77247-119">L'impostazione predefinita è OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="77247-119">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="77247-120">L'attributo è di tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="77247-120">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77247-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="77247-121">Child Elements</span></span>  
 <span data-ttu-id="77247-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="77247-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77247-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="77247-123">Parent Elements</span></span>  
  
|<span data-ttu-id="77247-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="77247-124">Element</span></span>|<span data-ttu-id="77247-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77247-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77247-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="77247-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="77247-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="77247-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77247-128">Note</span><span class="sxs-lookup"><span data-stu-id="77247-128">Remarks</span></span>  
 <span data-ttu-id="77247-129">Questo elemento consente di abilitare o disabilitare il flusso delle transazioni in arrivo nelle impostazioni di associazione di un endpoint, nonché di specificare il formato del protocollo di transazione desiderato per le transazioni in arrivo.</span><span class="sxs-lookup"><span data-stu-id="77247-129">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="77247-130">Per altre informazioni sull'uso di questo elemento di configurazione, vedere [configurazione delle transazioni ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) e [abilitazione della transazione propagata](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="77247-130">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="77247-131">Quando viene usato il protocollo `OleTransactions` per propagare transazioni da endpoint a endpoint, il timeout della transazione può essere perso se l'endpoint di destinazione tenta di eseguire nuovamente la propagazione usando un protocollo diverso da `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="77247-131">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="77247-132">Ciò può provocare un ritardo del timeout di tutti i nodi di livello inferiore dopo l'hop OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="77247-132">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77247-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77247-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="77247-134">Configurazione delle transazioni ServiceModel</span><span class="sxs-lookup"><span data-stu-id="77247-134">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="77247-135">Attivazione del flusso delle transazioni</span><span class="sxs-lookup"><span data-stu-id="77247-135">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="77247-136">Associazioni</span><span class="sxs-lookup"><span data-stu-id="77247-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="77247-137">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="77247-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="77247-138">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="77247-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="77247-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="77247-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

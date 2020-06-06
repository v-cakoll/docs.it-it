---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: f5bcd142fb2b032ea179bcbba68fee53b98d2d77
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736309"
---
# \<transactionFlow>
<span data-ttu-id="2ed50-101">Specifica il supporto del flusso di transazione per l'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2ed50-101">Specifies transaction flow support for the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**  
  
## <a name="syntax"></a><span data-ttu-id="2ed50-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ed50-102">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ed50-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2ed50-103">Attributes and Elements</span></span>  
 <span data-ttu-id="2ed50-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2ed50-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ed50-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="2ed50-105">Attributes</span></span>  
  
|<span data-ttu-id="2ed50-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="2ed50-106">Attribute</span></span>|<span data-ttu-id="2ed50-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ed50-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ed50-108">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="2ed50-108">transactionProtocol</span></span>|<span data-ttu-id="2ed50-109">Specifica il protocollo di transazione da usare.</span><span class="sxs-lookup"><span data-stu-id="2ed50-109">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="2ed50-110">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ed50-110">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2ed50-111">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="2ed50-111">-   OleTransactions</span></span><br /><span data-ttu-id="2ed50-112">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="2ed50-112">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="2ed50-113">L'impostazione predefinita è OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="2ed50-113">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="2ed50-114">L'attributo è di tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="2ed50-114">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ed50-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2ed50-115">Child Elements</span></span>  
 <span data-ttu-id="2ed50-116">No.</span><span class="sxs-lookup"><span data-stu-id="2ed50-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ed50-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2ed50-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2ed50-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ed50-118">Element</span></span>|<span data-ttu-id="2ed50-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ed50-119">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="2ed50-120">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2ed50-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ed50-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="2ed50-121">Remarks</span></span>  
 <span data-ttu-id="2ed50-122">Questo elemento consente di abilitare o disabilitare il flusso delle transazioni in arrivo nelle impostazioni di associazione di un endpoint, nonché di specificare il formato del protocollo di transazione desiderato per le transazioni in arrivo.</span><span class="sxs-lookup"><span data-stu-id="2ed50-122">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="2ed50-123">Per altre informazioni sull'uso di questo elemento di configurazione, vedere [configurazione delle transazioni ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md) e [Abilitazione del flusso delle transazioni](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="2ed50-123">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="2ed50-124">Quando viene usato il protocollo `OleTransactions` per propagare transazioni da endpoint a endpoint, il timeout della transazione può essere perso se l'endpoint di destinazione tenta di eseguire nuovamente la propagazione usando un protocollo diverso da `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="2ed50-124">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="2ed50-125">Ciò può provocare un ritardo del timeout di tutti i nodi di livello inferiore dopo l'hop OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="2ed50-125">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed50-126">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2ed50-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2ed50-127">Configurazione delle transazioni ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2ed50-127">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="2ed50-128">Attivazione del flusso delle transazioni</span><span class="sxs-lookup"><span data-stu-id="2ed50-128">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="2ed50-129">Binding</span><span class="sxs-lookup"><span data-stu-id="2ed50-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2ed50-130">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="2ed50-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2ed50-131">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="2ed50-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)

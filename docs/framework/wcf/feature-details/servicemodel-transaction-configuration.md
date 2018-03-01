---
title: Configurazione delle transazioni ServiceModel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactions [WCF], ServiceModel configuration
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 650f34c37917a7f7ce407df1a3af42d177593c33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="servicemodel-transaction-configuration"></a><span data-ttu-id="3f2ed-102">Configurazione delle transazioni ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3f2ed-102">ServiceModel Transaction Configuration</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="3f2ed-103"> fornisce tre attributi per configurare le transazioni di un servizio: `transactionFlow`, `transactionProtocol`e `transactionTimeout`.</span><span class="sxs-lookup"><span data-stu-id="3f2ed-103"> provides three attributes for configuring transactions for a service: `transactionFlow`, `transactionProtocol`, and `transactionTimeout`.</span></span>  
  
## <a name="configuring-transactionflow"></a><span data-ttu-id="3f2ed-104">Configurazione di transactionFlow</span><span class="sxs-lookup"><span data-stu-id="3f2ed-104">Configuring transactionFlow</span></span>  
 <span data-ttu-id="3f2ed-105">La maggior parte delle associazioni predefinite fornite in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contiene gli attributi `transactionFlow` e `transactionProtocol`. Ciò consente di configurare un'associazione in modo che accetti transazioni in ingresso presso un endpoint specifico tramite un determinato protocollo di flusso delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="3f2ed-105">Most of the predefined bindings [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides contain the `transactionFlow` and `transactionProtocol` attributes, so that you can configure the binding to accept incoming transactions for a specific endpoint using a specific transaction flow protocol.</span></span> <span data-ttu-id="3f2ed-106">È inoltre possibile utilizzare l'elemento `transactionFlow` e il relativo attributo `transactionProtocol` per compilare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3f2ed-106">In addition, you can use the `transactionFlow` element and its `transactionProtocol` attribute to build your own custom binding.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="3f2ed-107">Imposta gli elementi di configurazione, vedere [ \<associazione >](../../../../docs/framework/misc/binding.md) e [Schema di configurazione WCF](../../../../docs/framework/configure-apps/file-schema/wcf/index.md).</span><span class="sxs-lookup"><span data-stu-id="3f2ed-107"> setting the configuration elements, see [\<binding>](../../../../docs/framework/misc/binding.md) and [WCF Configuration Schema](../../../../docs/framework/configure-apps/file-schema/wcf/index.md).</span></span>  
  
 <span data-ttu-id="3f2ed-108">L'attributo `transactionFlow` specifica se il flusso delle transazioni è attivo presso gli endpoint di servizio che utilizzano l'associazione.</span><span class="sxs-lookup"><span data-stu-id="3f2ed-108">The `transactionFlow` attribute specifies whether transaction flow is enabled for service endpoints that use the binding.</span></span>  
  
## <a name="configuring-transactionprotocol"></a><span data-ttu-id="3f2ed-109">Configurazione di transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="3f2ed-109">Configuring transactionProtocol</span></span>  
 <span data-ttu-id="3f2ed-110">L'attributo `transactionProtocol` specifica il protocollo di transazione da utilizzare presso gli endpoint di servizio che utilizzano l'associazione.</span><span class="sxs-lookup"><span data-stu-id="3f2ed-110">The `transactionProtocol` attribute specifies the transaction protocol to use with service endpoints that use the binding.</span></span>  
  
 <span data-ttu-id="3f2ed-111">Gli elementi seguenti rappresentano un esempio di sezione di configurazione in cui l'associazione specificata viene impostata in modo da supportare il flusso delle transazioni. Tali elementi sono inoltre un esempio di utilizzo del protocollo WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="3f2ed-111">The following is an example of a configuration section that configures the specified binding to support transaction flow, as well as a use the WS-AtomicTransaction protocol.</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding name="test"  
      closeTimeout="00:00:10"  
      openTimeout="00:00:20"   
      receiveTimeout="00:00:30"  
      sendTimeout="00:00:40"  
      transactionFlow="true"  
      transactionProtocol="WSAtomicTransactionOctober2004"  
      hostNameComparisonMode="WeakWildcard"  
      maxBufferSize="1001"  
      maxConnections="123"   
      maxReceivedMessageSize="1000">  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="configuring-transactiontimeout"></a><span data-ttu-id="3f2ed-112">Configurazione di transactionTimeout</span><span class="sxs-lookup"><span data-stu-id="3f2ed-112">Configuring transactionTimeout</span></span>  
 <span data-ttu-id="3f2ed-113">Per configurare l'attributo `transactionTimeout` del servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è possibile impostare l'elemento `behavior` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3f2ed-113">You can configure the `transactionTimeout` attribute for your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service in the `behavior` element of the configuration file.</span></span> <span data-ttu-id="3f2ed-114">Nell'esempio di codice seguente viene illustrato come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="3f2ed-114">The following code demonstrates how to do this.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>  
         <behavior name="NewBehavior" transactionTimeout="00:01:00" /> <!-- 1 minute timeout -->  
      </behaviors>  
   </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="3f2ed-115">L'attributo `transactionTimeout` specifica il timeout di completamento di una nuova transazione creata nel servizio.</span><span class="sxs-lookup"><span data-stu-id="3f2ed-115">The `transactionTimeout` attribute specifies the time period within which a new transaction created at the service must complete.</span></span> <span data-ttu-id="3f2ed-116">Questo attributo viene utilizzato come timeout dell'ambito <xref:System.Transactions.TransactionScope> delle operazioni che creano una nuova transazione. Inoltre, se viene applicato l'attributo <xref:System.ServiceModel.OperationBehaviorAttribute>, la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> viene impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="3f2ed-116">It is used as the <xref:System.Transactions.TransactionScope> time-out for any operation that establishes a new transaction, and if <xref:System.ServiceModel.OperationBehaviorAttribute> is applied, the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property is set to `true`.</span></span>  
  
 <span data-ttu-id="3f2ed-117">Il timeout corrisponde al periodo di tempo che va dalla creazione della transazione al completamento della fase 1 del protocollo di commit a due fasi.</span><span class="sxs-lookup"><span data-stu-id="3f2ed-117">The time-out specifies the duration of time from the creation of the transaction to the completion of phase 1 in the two-phase commit protocol.</span></span>  
  
 <span data-ttu-id="3f2ed-118">Se si imposta questo attributo all'interno della sezione di configurazione di un `service`, è necessario applicare almeno un metodo del servizio corrispondente avente un attributo <xref:System.ServiceModel.OperationBehaviorAttribute> in cui la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="3f2ed-118">If this attribute is set within a `service` configuration section, you should apply at least one method of the corresponding service with <xref:System.ServiceModel.OperationBehaviorAttribute>, in which the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property is set to `true`.</span></span>  
  
 <span data-ttu-id="3f2ed-119">Si noti che il valore di timeout effettivo è il minore fra l'impostazione di configurazione `transactionTimeout` e le proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f2ed-119">Note that the time-out value used is the smaller value between this `transactionTimeout` configuration setting and any <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f2ed-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f2ed-120">See Also</span></span>  
 [<span data-ttu-id="3f2ed-121">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="3f2ed-121">\<binding></span></span>](../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="3f2ed-122">Schema di configurazione di WCF</span><span class="sxs-lookup"><span data-stu-id="3f2ed-122">WCF Configuration Schema</span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/index.md)

---
title: Configurazione delle transazioni ServiceModel
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF], ServiceModel configuration
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
ms.openlocfilehash: 1d04a7bb756cccb33b436c1f57decc0249764828
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600335"
---
# <a name="servicemodel-transaction-configuration"></a><span data-ttu-id="9870a-102">Configurazione delle transazioni ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9870a-102">ServiceModel Transaction Configuration</span></span>
<span data-ttu-id="9870a-103">Windows Communication Foundation (WCF) fornisce tre attributi per la configurazione delle transazioni per un servizio: `transactionFlow` , `transactionProtocol` e `transactionTimeout` .</span><span class="sxs-lookup"><span data-stu-id="9870a-103">Windows Communication Foundation (WCF) provides three attributes for configuring transactions for a service: `transactionFlow`, `transactionProtocol`, and `transactionTimeout`.</span></span>  
  
## <a name="configuring-transactionflow"></a><span data-ttu-id="9870a-104">Configurazione di transactionFlow</span><span class="sxs-lookup"><span data-stu-id="9870a-104">Configuring transactionFlow</span></span>  
 <span data-ttu-id="9870a-105">La maggior parte delle associazioni predefinite fornite da WCF contiene gli `transactionFlow` `transactionProtocol` attributi e, in modo che sia possibile configurare l'associazione in modo che accetti le transazioni in ingresso per un endpoint specifico utilizzando un protocollo di flusso di transazione specifico.</span><span class="sxs-lookup"><span data-stu-id="9870a-105">Most of the predefined bindings WCF provides contain the `transactionFlow` and `transactionProtocol` attributes, so that you can configure the binding to accept incoming transactions for a specific endpoint using a specific transaction flow protocol.</span></span> <span data-ttu-id="9870a-106">È inoltre possibile utilizzare l'elemento `transactionFlow` e il relativo attributo `transactionProtocol` per compilare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="9870a-106">In addition, you can use the `transactionFlow` element and its `transactionProtocol` attribute to build your own custom binding.</span></span> <span data-ttu-id="9870a-107">Per ulteriori informazioni sull'impostazione degli elementi di configurazione, vedere [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) e [schema di configurazione WCF](../../configure-apps/file-schema/wcf/index.md).</span><span class="sxs-lookup"><span data-stu-id="9870a-107">For more information about setting the configuration elements, see [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) and [WCF Configuration Schema](../../configure-apps/file-schema/wcf/index.md).</span></span>  
  
 <span data-ttu-id="9870a-108">L'attributo `transactionFlow` specifica se il flusso delle transazioni è attivo presso gli endpoint di servizio che utilizzano l'associazione.</span><span class="sxs-lookup"><span data-stu-id="9870a-108">The `transactionFlow` attribute specifies whether transaction flow is enabled for service endpoints that use the binding.</span></span>  
  
## <a name="configuring-transactionprotocol"></a><span data-ttu-id="9870a-109">Configurazione di transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="9870a-109">Configuring transactionProtocol</span></span>  
 <span data-ttu-id="9870a-110">L'attributo `transactionProtocol` specifica il protocollo di transazione da utilizzare presso gli endpoint di servizio che utilizzano l'associazione.</span><span class="sxs-lookup"><span data-stu-id="9870a-110">The `transactionProtocol` attribute specifies the transaction protocol to use with service endpoints that use the binding.</span></span>  
  
 <span data-ttu-id="9870a-111">Gli elementi seguenti rappresentano un esempio di sezione di configurazione in cui l'associazione specificata viene impostata in modo da supportare il flusso delle transazioni. Tali elementi sono inoltre un esempio di utilizzo del protocollo WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="9870a-111">The following is an example of a configuration section that configures the specified binding to support transaction flow, as well as a use the WS-AtomicTransaction protocol.</span></span>  
  
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
  
## <a name="configuring-transactiontimeout"></a><span data-ttu-id="9870a-112">Configurazione di transactionTimeout</span><span class="sxs-lookup"><span data-stu-id="9870a-112">Configuring transactionTimeout</span></span>  
 <span data-ttu-id="9870a-113">È possibile configurare l' `transactionTimeout` attributo per il servizio WCF nell' `behavior` elemento del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9870a-113">You can configure the `transactionTimeout` attribute for your WCF service in the `behavior` element of the configuration file.</span></span> <span data-ttu-id="9870a-114">Nell'esempio di codice seguente viene illustrato come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="9870a-114">The following code demonstrates how to do this.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>  
         <behavior name="NewBehavior" transactionTimeout="00:01:00" /> <!-- 1 minute timeout -->  
      </behaviors>  
   </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="9870a-115">L'attributo `transactionTimeout` specifica il timeout di completamento di una nuova transazione creata nel servizio.</span><span class="sxs-lookup"><span data-stu-id="9870a-115">The `transactionTimeout` attribute specifies the time period within which a new transaction created at the service must complete.</span></span> <span data-ttu-id="9870a-116">Questo attributo viene utilizzato come timeout dell'ambito <xref:System.Transactions.TransactionScope> delle operazioni che creano una nuova transazione. Inoltre, se viene applicato l'attributo <xref:System.ServiceModel.OperationBehaviorAttribute>, la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> viene impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="9870a-116">It is used as the <xref:System.Transactions.TransactionScope> time-out for any operation that establishes a new transaction, and if <xref:System.ServiceModel.OperationBehaviorAttribute> is applied, the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property is set to `true`.</span></span>  
  
 <span data-ttu-id="9870a-117">Il timeout corrisponde al periodo di tempo che va dalla creazione della transazione al completamento della fase 1 del protocollo di commit a due fasi.</span><span class="sxs-lookup"><span data-stu-id="9870a-117">The time-out specifies the duration of time from the creation of the transaction to the completion of phase 1 in the two-phase commit protocol.</span></span>  
  
 <span data-ttu-id="9870a-118">Se si imposta questo attributo all'interno della sezione di configurazione di un `service`, è necessario applicare almeno un metodo del servizio corrispondente avente un attributo <xref:System.ServiceModel.OperationBehaviorAttribute> in cui la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="9870a-118">If this attribute is set within a `service` configuration section, you should apply at least one method of the corresponding service with <xref:System.ServiceModel.OperationBehaviorAttribute>, in which the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property is set to `true`.</span></span>  
  
 <span data-ttu-id="9870a-119">Si noti che il valore di timeout effettivo è il minore fra l'impostazione di configurazione `transactionTimeout` e le proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="9870a-119">Note that the time-out value used is the smaller value between this `transactionTimeout` configuration setting and any <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9870a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9870a-120">See also</span></span>

- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md)
- [<span data-ttu-id="9870a-121">Schema di configurazione di WCF</span><span class="sxs-lookup"><span data-stu-id="9870a-121">WCF Configuration Schema</span></span>](../../configure-apps/file-schema/wcf/index.md)

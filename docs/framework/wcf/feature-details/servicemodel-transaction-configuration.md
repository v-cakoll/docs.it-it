---
title: Configurazione delle transazioni ServiceModel
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF], ServiceModel configuration
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
ms.openlocfilehash: 79772d19ddaec041aa1fac936b9951731507b6e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184461"
---
# <a name="servicemodel-transaction-configuration"></a>Configurazione delle transazioni ServiceModel
Windows Communication Foundation (WCF) fornisce tre attributi per `transactionFlow`la `transactionProtocol`configurazione `transactionTimeout`delle transazioni per un servizio: , e .  
  
## <a name="configuring-transactionflow"></a>Configurazione di transactionFlow  
 La maggior parte delle associazioni predefinite `transactionFlow` `transactionProtocol` fornite da WCF contiene gli attributi e , in modo che sia possibile configurare l'associazione per accettare le transazioni in ingresso per un endpoint specifico usando un protocollo del flusso di transazioni specifico. È inoltre possibile utilizzare l'elemento `transactionFlow` e il relativo attributo `transactionProtocol` per compilare un'associazione personalizzata. Per ulteriori informazioni sull'impostazione degli elementi di configurazione, vedere [ \<>di associazione](../../configure-apps/file-schema/wcf/bindings.md) e Schema di [configurazione WCF](../../../../docs/framework/configure-apps/file-schema/wcf/index.md).  
  
 L'attributo `transactionFlow` specifica se il flusso delle transazioni è attivo presso gli endpoint di servizio che utilizzano l'associazione.  
  
## <a name="configuring-transactionprotocol"></a>Configurazione di transactionProtocol  
 L'attributo `transactionProtocol` specifica il protocollo di transazione da utilizzare presso gli endpoint di servizio che utilizzano l'associazione.  
  
 Gli elementi seguenti rappresentano un esempio di sezione di configurazione in cui l'associazione specificata viene impostata in modo da supportare il flusso delle transazioni. Tali elementi sono inoltre un esempio di utilizzo del protocollo WS-AtomicTransaction.  
  
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
  
## <a name="configuring-transactiontimeout"></a>Configurazione di transactionTimeout  
 È possibile `transactionTimeout` configurare l'attributo `behavior` per il servizio WCF nell'elemento del file di configurazione. Nell'esempio di codice seguente viene illustrato come eseguire questa operazione.  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>  
         <behavior name="NewBehavior" transactionTimeout="00:01:00" /> <!-- 1 minute timeout -->  
      </behaviors>  
   </system.serviceModel>  
</configuration>  
```  
  
 L'attributo `transactionTimeout` specifica il timeout di completamento di una nuova transazione creata nel servizio. Questo attributo viene utilizzato come timeout dell'ambito <xref:System.Transactions.TransactionScope> delle operazioni che creano una nuova transazione. Inoltre, se viene applicato l'attributo <xref:System.ServiceModel.OperationBehaviorAttribute>, la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> viene impostata su `true`.  
  
 Il timeout corrisponde al periodo di tempo che va dalla creazione della transazione al completamento della fase 1 del protocollo di commit a due fasi.  
  
 Se si imposta questo attributo all'interno della sezione di configurazione di un `service`, è necessario applicare almeno un metodo del servizio corrispondente avente un attributo <xref:System.ServiceModel.OperationBehaviorAttribute> in cui la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è impostata su `true`.  
  
 Si noti che il valore di timeout effettivo è il minore fra l'impostazione di configurazione `transactionTimeout` e le proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.  
  
## <a name="see-also"></a>Vedere anche

- [\<>di associazione](../../configure-apps/file-schema/wcf/bindings.md)
- [Schema di configurazione WCFWCF Configuration Schema](../../../../docs/framework/configure-apps/file-schema/wcf/index.md)

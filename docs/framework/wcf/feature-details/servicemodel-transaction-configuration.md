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
# <a name="servicemodel-transaction-configuration"></a>Configurazione delle transazioni ServiceModel
Windows Communication Foundation (WCF) fornisce tre attributi per la configurazione delle transazioni per un servizio: `transactionFlow` , `transactionProtocol` e `transactionTimeout` .  
  
## <a name="configuring-transactionflow"></a>Configurazione di transactionFlow  
 La maggior parte delle associazioni predefinite fornite da WCF contiene gli `transactionFlow` `transactionProtocol` attributi e, in modo che sia possibile configurare l'associazione in modo che accetti le transazioni in ingresso per un endpoint specifico utilizzando un protocollo di flusso di transazione specifico. È inoltre possibile utilizzare l'elemento `transactionFlow` e il relativo attributo `transactionProtocol` per compilare un'associazione personalizzata. Per ulteriori informazioni sull'impostazione degli elementi di configurazione, vedere [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) e [schema di configurazione WCF](../../configure-apps/file-schema/wcf/index.md).  
  
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
 È possibile configurare l' `transactionTimeout` attributo per il servizio WCF nell' `behavior` elemento del file di configurazione. Nell'esempio di codice seguente viene illustrato come eseguire questa operazione.  
  
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

- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md)
- [Schema di configurazione di WCF](../../configure-apps/file-schema/wcf/index.md)

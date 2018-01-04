---
title: Configurazione delle transazioni ServiceModel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: transactions [WCF], ServiceModel configuration
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 650f34c37917a7f7ce407df1a3af42d177593c33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="servicemodel-transaction-configuration"></a>Configurazione delle transazioni ServiceModel
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] fornisce tre attributi per configurare le transazioni di un servizio: `transactionFlow`, `transactionProtocol`e `transactionTimeout`.  
  
## <a name="configuring-transactionflow"></a>Configurazione di transactionFlow  
 La maggior parte delle associazioni predefinite fornite in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contiene gli attributi `transactionFlow` e `transactionProtocol`. Ciò consente di configurare un'associazione in modo che accetti transazioni in ingresso presso un endpoint specifico tramite un determinato protocollo di flusso delle transazioni. È inoltre possibile utilizzare l'elemento `transactionFlow` e il relativo attributo `transactionProtocol` per compilare un'associazione personalizzata. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Imposta gli elementi di configurazione, vedere [ \<associazione >](../../../../docs/framework/misc/binding.md) e [Schema di configurazione WCF](../../../../docs/framework/configure-apps/file-schema/wcf/index.md).  
  
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
 Per configurare l'attributo `transactionTimeout` del servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è possibile impostare l'elemento `behavior` del file di configurazione. Nell'esempio di codice seguente viene illustrato come eseguire questa operazione.  
  
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
 [\<associazione >](../../../../docs/framework/misc/binding.md)  
 [Schema di configurazione di WCF](../../../../docs/framework/configure-apps/file-schema/wcf/index.md)

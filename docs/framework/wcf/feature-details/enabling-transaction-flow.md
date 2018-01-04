---
title: Attivazione del flusso delle transazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: transactions [WCF], enabling flow
ms.assetid: a03f5041-5049-43f4-897c-e0292d4718f7
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 814df9ff4fb11b0aa59270ac251b5dbd9ed7fe96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="enabling-transaction-flow"></a>Attivazione del flusso delle transazioni
In [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sono disponibili opzioni estremamente flessibili per il controllo del flusso delle transazioni. Le impostazioni del flusso delle transazioni di un servizio possono essere espresse con una determinata combinazione di attributi e configurazione.  
  
## <a name="transaction-flow-settings"></a>Impostazioni del flusso delle transazioni  
 Le impostazioni del flusso delle transazioni vengono generate per un endpoint del servizio come esito dell'intersezione dei tre valori seguenti:  
  
-   L'attributo <xref:System.ServiceModel.TransactionFlowAttribute> specificato per ogni metodo contenuto nel contratto di servizio.  
  
-   La proprietà `TransactionFlow` nella  specifica associazione.  
  
-   La proprietà `TransactionFlowProtocol` nella  specifica associazione. La proprietà `TransactionFlowProtocol` di associazione consente di scegliere fra due protocolli di transazione diversi che è possibile utilizzare per propagare una transazione. Questi valori vengono descritti brevemente nelle sezioni seguenti.  
  
### <a name="ws-atomictransaction-protocol"></a>Protocollo WS-AtomicTransaction  
 Il protocollo WS-AtomicTransaction (WS-AT) è utile per scenari in cui è richiesta l'interoperabilità con stack del protocollo di terze parti.  
  
### <a name="oletransactions-protocol"></a>Protocollo OleTransactions  
 Il protocollo OleTransactions è utile per gli scenari in cui l'interoperabilità con stack del protocollo di terze parti non è necessario e il distributore di un servizio sa in anticipo che il servizio del protocollo WS-AT è disattivato localmente o che la topologia di rete esistente non favorisce l'utilizzo di WS-AT.  
  
 Nella tabella seguente sono mostrati i tipi diversi di flussi delle transazioni che possono essere generati utilizzando queste varie combinazioni.  
  
|TransactionFlow<br /><br /> binding|Proprietà di associazione TransactionFlow|Proprietà di associazione TransactionFlowProtocol|Tipo del flusso delle transazioni|  
|---------------------------------|--------------------------------------|----------------------------------------------|------------------------------|  
|Obbligatorio|true|WS-AT|La transazione deve essere propagata nel formato WS-AT interoperativo.|  
|Obbligatorio|true|OleTransactions|La transazione deve essere propagata nel formato OleTransactions di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].|  
|Obbligatorio|False|Non applicabile|Non applicabile perché questa configurazione non è valida.|  
|Allowed|true|WS-AT|La transazione può essere propagata nel formato WS-AT interoperativo.|  
|Allowed|true|OleTransactions|La transazione può essere propagata nel formato OleTransactions di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].|  
|Allowed|False|Qualsiasi valore|Una transazione non è propagata.|  
|NotAllowed|Qualsiasi valore|Qualsiasi valore|Una transazione non è propagata.|  
  
 Nella tabella seguente viene fornito un riepilogo del risultato di elaborazione dei messaggi.  
  
|Messaggio in arrivo.|Impostazioni di TransactionFlow|Intestazione della transazione|Risultato di elaborazione del messaggio|  
|----------------------|-----------------------------|------------------------|-------------------------------|  
|La transazione corrisponde al formato previsto del protocollo|Consentito o obbligatorio|`MustUnderstand` è uguale a `true`.|Process|  
|La transazione non corrisponde al formato previsto del protocollo|Obbligatorio|`MustUnderstand` è uguale a `false`.|Rifiutato perché una transazione è obbligatoria|  
|La transazione non corrisponde al formato previsto del protocollo|Allowed|`MustUnderstand` è uguale a `false`.|Rifiutato perché l'intestazione non è compresa|  
|Transazione che utilizza qualsiasi formato di protocollo|NotAllowed|`MustUnderstand` è uguale a `false`.|Rifiutato perché l'intestazione non è compresa|  
|Nessuna transazione|Obbligatorio|N/D|Rifiutato perché una transazione è obbligatoria|  
|Nessuna transazione|Allowed|N/D|Process|  
|Nessuna transazione|NotAllowed|N/D|Processo|  
  
 Mentre ogni metodo di un contratto può disporre di requisiti diversi per il flusso delle transazioni, l'impostazione del protocollo relativo al flusso delle transazioni è limitato all'ambito del livello dell'associazione. Tutti i metodi che condividono lo stesso endpoint, e di conseguenza la stessa associazione, condividono inoltre lo stesso criterio che ammette o richiede un flusso di transazioni, nonché, se opportuno, lo stesso protocollo di transazione.  
  
## <a name="enabling-transaction-flow-at-the-method-level"></a>Attivazione del flusso delle transazioni a livello di metodo  
 I requisiti del flusso delle transazioni non sono sempre gli stessi per tutti i metodi di un contratto di servizio. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], quindi, fornisce un meccanismo basato su un attributo che consente l'espressione di preferenze relativamente al flusso delle transazioni di ogni metodo. <xref:System.ServiceModel.TransactionFlowAttribute>, infatti, consente di specificare il livello al quale un'operazione del servizio accetta un'intestazione di transazione. Se si desidera attivare il flusso delle transazioni, è necessario contrassegnare i metodi del contratto di servizio con questo attributo. L'attributo accetta uno dei valori dell'enumerazione <xref:System.ServiceModel.TransactionFlowOption>, in cui il valore predefinito è <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>. Se si specifica qualsiasi valore ad eccezione di <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>, è necessario che il metodo non sia unidirezionale. Gli sviluppatori possono utilizzare questo attributo per specificare i requisiti del flusso delle transazioni a livello di metodo o i vincoli in fase di progettazione.  
  
## <a name="enabling-transaction-flow-at-the-endpoint-level"></a>Attivazione del flusso delle transazioni a livello di endpoint  
 Oltre all'impostazione del flusso di transazioni a livello di metodo fornita dall'attributo <xref:System.ServiceModel.TransactionFlowAttribute>, in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è inoltre disponibile un'impostazione a livello di endpoint per il flusso di transazioni che consente agli amministratori di controllare il flusso a un livello superiore.  
  
 Questa possibilità è data da <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, che consente di attivare o disattivare il flusso delle transazioni in arrivo nelle impostazioni di associazione di un endpoint, nonché di specificare il formato del protocollo di transazione desiderato per le transazioni in arrivo.  
  
 Se nell'associazione il flusso delle transazioni è disattivato ma una delle operazioni di un contratto di servizio richiede una transazione in arrivo, in fase di avvio del servizio viene generata un'eccezione di convalida.  
  
 La maggior parte delle associazioni permanenti fornite in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contiene gli attributi `transactionFlow` e `transactionProtocol` che consentono di configurare l'associazione specifica perché accetti transazioni in arrivo. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Imposta gli elementi di configurazione, vedere [ \<associazione >](../../../../docs/framework/misc/binding.md).  
  
 Gli amministratori o i distributori possono avvalersi del flusso delle transazioni a livello di endpoint per configurare i requisiti del flusso o i vincoli in fase di distribuzione utilizzando il file di configurazione.  
  
## <a name="security"></a>Sicurezza  
 Per garantire la protezione e l'integrità del sistema, è necessario proteggere gli scambi di messaggi durante la propagazione delle transazioni tra applicazioni. È necessario non propagare o divulgare dettagli delle transazioni ad applicazioni non autorizzate a partecipare alla stessa transazione.  
  
 Durante la generazione di client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a servizi Web ignoti o non attendibili tramite lo scambio di metadati, le chiamate alle operazioni in questi servizi Web devono, se possibile, sopprimere la transazione corrente. Nell'esempio riportato di seguito viene illustrato come procedere.  
  
```  
//client code which has an ambient transaction  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Suppress))  
{  
    // No transaction will flow to this operation  
    untrustedProxy.Operation1(...);  
    scope.Complete();  
}  
//remainder of client code  
```  
  
 I servizi, inoltre, devono essere configurati per accettare transazioni in arrivo solo dai client che hanno autenticato e autorizzato. Le transazioni in arrivo devono essere accettate solo se provengono da client estremamente attendibili.  
  
## <a name="policy-assertions"></a>Asserzioni di criteri  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vengono utilizzate asserzioni di criteri per controllare il flusso delle transazioni. Le asserzioni di criteri possono trovarsi nel documento dei criteri di un servizio, generato aggregando contratti, configurazione e attributi. Il client può ottenere il documento dei criteri del servizio utilizzando un GET HTTP o un request/reply di WS-MetadataExchange. I client possono quindi elaborare il documento dei criteri per determinare quali operazioni di un contratto di servizio possono supportare o richiedere il flusso delle transazioni.  
  
 Le asserzioni di criteri di un flusso di transazioni incidono sul flusso stesso specificando le intestazioni SOAP che un client deve inviare a un servizio per rappresentare una transazione. Tutte le intestazioni di transazione devono essere contrassegnate con `MustUnderstand` uguale a `true`. Qualsiasi messaggio con un'intestazione contrassegnata diversamente viene rifiutato con un errore SOAP.  
  
 In una singola operazione può essere presente solo un'asserzione di criteri correlata alla transazione. I documenti di criteri con più di un'asserzione della transazione su un'operazione vengono considerati non validi e vengono rifiutati da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. In ogni tipo di porta, inoltre, può essere presente solo un protocollo di transazione. Documenti di criteri con le operazioni che fanno riferimento a più di un protocollo di transazione all'interno di un tipo di porta singola vengono considerati non validi e vengono rifiutati dal [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). I documenti di criteri con asserzioni di transazione presenti nei messaggi di output o nei messaggi di input unidirezionali vengono inoltre considerati non validi.

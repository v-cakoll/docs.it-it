---
title: Specifica del comportamento in fase di esecuzione dei client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- behaviors [WCF], system-provided client
ms.assetid: d16d3405-be70-4edb-8f62-b5f614ddeca5
ms.openlocfilehash: f9c22d25bedc36b3515538a8785b488aaa547990
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143239"
---
# <a name="specifying-client-run-time-behavior"></a>Specifica del comportamento in fase di esecuzione dei client
I client Windows Communication Foundation (WCF), ad esempio i servizi Windows Communication Foundation (WCF), possono essere configurati per modificare il comportamento in fase di esecuzione in base all'applicazione client. Sono disponibili tre attributi per la specifica del comportamento in fase di esecuzione dei client. Gli oggetti callback dei client duplex possono usare gli attributi <xref:System.ServiceModel.CallbackBehaviorAttribute> e <xref:System.ServiceModel.Description.CallbackDebugBehavior> per modificare il proprio comportamento in fase di esecuzione. L'altro attributo, <xref:System.ServiceModel.Description.ClientViaBehavior>, può essere usato per separare la destinazione logica dalla destinazione di rete immediata. Inoltre, i tipi di callback dei client duplex possono usare alcuni dei comportamenti del lato servizi. Per ulteriori informazioni, vedere [Specifica del comportamento in fase di esecuzione del servizio](specifying-service-run-time-behavior.md).  
  
## <a name="using-the-callbackbehaviorattribute"></a>Uso di CallbackBehaviorAttribute  
 È possibile configurare o estendere il comportamento di esecuzione dell'implementazione di un contratto di callback in un'applicazione client usando la classe <xref:System.ServiceModel.CallbackBehaviorAttribute>. Questo attributo esegue, per la classe di callback, una funzione simile a quella della classe <xref:System.ServiceModel.ServiceBehaviorAttribute>, fatta eccezione per il comportamento di creazione di istanze e le impostazioni di transazione.  
  
 La classe <xref:System.ServiceModel.CallbackBehaviorAttribute> deve essere applicata alla classe che implementa il contratto di callback. Se viene applicata all'implementazione di un contratto non duplex, viene generata un'eccezione <xref:System.InvalidOperationException> in fase di esecuzione. Nell'esempio di codice seguente vengono mostrate una classe <xref:System.ServiceModel.CallbackBehaviorAttribute> su un oggetto callback che usa l'oggetto <xref:System.Threading.SynchronizationContext> per determinare il thread su cui eseguire il marshalling, la proprietà <xref:System.ServiceModel.CallbackBehaviorAttribute.ValidateMustUnderstand%2A> per applicare la convalida del messaggio e la proprietà <xref:System.ServiceModel.CallbackBehaviorAttribute.IncludeExceptionDetailInFaults%2A> per restituire eccezioni come oggetti <xref:System.ServiceModel.FaultException> al servizio a scopo di debug.  
  
 [!code-csharp[CallbackBehaviorAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/callbackbehaviorattribute/cs/client.cs#3)]
 [!code-vb[CallbackBehaviorAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/callbackbehaviorattribute/vb/client.vb#3)]  
  
## <a name="using-callbackdebugbehavior-to-enable-the-flow-of-managed-exception-information"></a>Uso di CallbackDebugBehavior per abilitare il flusso di informazioni sulle eccezioni gestite  
 È possibile abilitare il flusso di informazioni sulle eccezioni gestite in un oggetto callback client diretto al servizio a scopo di debug impostando la proprietà <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> su `true` a livello di programmazione o da un file di configurazione dell'applicazione.  
  
 La restituzione ai servizi delle informazioni sulle eccezioni gestite può rappresentare un rischio per la protezione, poiché i dettagli delle eccezioni espongono informazioni sull'implementazione del client interno utilizzabili da servizi non autorizzati. Inoltre, sebbene le proprietà <xref:System.ServiceModel.Description.CallbackDebugBehavior> possono essere impostate anche a livello di programmazione, può essere facile dimenticare di disattivare <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> quando si esegue la distribuzione.  
  
 A causa dei problemi di sicurezza coinvolti, è consigliato:  
  
- Usare un file di configurazione dell'applicazione per impostare il valore della proprietà <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> su `true`.  
  
- Si procede in questo modo solo negli scenari di debug controllati.  
  
 Esempio di codice seguente viene illustrato un file di configurazione client che indica a WCF di restituire informazioni sulle eccezioni gestite da un oggetto callback client nei messaggi SOAP.  
  
 [!code-xml[SCA.CallbackContract#4](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.callbackcontract/cs/client.exe.config#4)]  

## <a name="using-the-clientviabehavior-behavior"></a>Utilizzo del comportamento ClientViaBehavior  
 È possibile usare il comportamento <xref:System.ServiceModel.Description.ClientViaBehavior> per specificare l'URI (Uniform Resource Identifier) per il quale deve essere creato il canale del trasporto. Usare questo comportamento quando la destinazione di rete immediata non è il processore desiderato del messaggio. Questo consente conversazioni multihop quando l'applicazione chiamante non conosce necessariamente la destinazione finale o quando l'intestazione `Via` della destinazione non è un indirizzo.  
  
## <a name="see-also"></a>Vedere anche

- [Specifica del comportamento in fase di esecuzione del servizio](specifying-service-run-time-behavior.md)

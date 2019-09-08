---
title: Utilizzo di un servizio dati in un'applicazione client (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, getting started
ms.assetid: 90872d0c-e989-4490-b3e9-54afb10d33d4
ms.openlocfilehash: 050c1a67a367a6dd5175c535fe89fb0010ae8cbc
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790290"
---
# <a name="using-a-data-service-in-a-client-application-wcf-data-services"></a>Utilizzo di un servizio dati in un'applicazione client (WCF Data Services)
È possibile accedere a un servizio che espone [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] un feed fornendo un URI a una Web browser. L'URI fornisce l'indirizzo di una risorsa e i messaggi di richiesta vengono inviati a questi indirizzi per accedere ai dati sottostanti rappresentati dalla risorsa o per modificarli. Il browser invia un comando GET HTTP e restituisce la risorsa richiesta come feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Per ulteriori informazioni, vedere [accesso al servizio da un Web browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
 Sebbene l'uso di un browser possa risultare utile per verificare che un servizio [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] restituisca i dati previsti, l'accesso ai servizi [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] di produzione che consentono inoltre di creare, aggiornare ed eliminare dati viene in genere eseguito tramite linguaggi di codice delle applicazioni o di script in una pagina Web. In questo argomento viene fornita una panoramica su come [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] accedere ai feed da un'applicazione client.  
  
## <a name="accessing-and-changing-data-using-rest-semantics"></a>Accesso ai dati e relativa modifica tramite la semantica REST  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]consente di garantire l'interoperabilità tra [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] i servizi che espongono [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed e applicazioni che utilizzano feed. Le applicazioni accedono ai dati in [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]un servizio basato su e li modificano inviando messaggi di richiesta di un'azione http specifica e con un URI che indirizza una risorsa di entità sulla quale deve essere eseguita l'azione. I dati di entità necessari vengono forniti come payload codificato in modo appropriato nel corpo del messaggio.  
  
### <a name="http-actions"></a>Azioni HTTP  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] supporta le azioni HTTP riportate di seguito per l'esecuzione di operazioni di creazione, lettura, aggiornamento ed eliminazione sui dati di entità rappresentati dalla risorsa indirizzata.  
  
- **Http Get** : questa è l'azione predefinita quando si accede a una risorsa da un browser. Nel messaggio di richiesta non viene fornito alcun payload e viene restituito un metodo di risposta con un payload contenente i dati richiesti.  
  
- **Http post** -inserisce i nuovi dati di entità nella risorsa fornita. I dati da inserire vengono forniti nel payload del messaggio di richiesta. Il payload del messaggio di risposta contiene i dati per l'entità appena creata, inclusi i valori della chiave generati automaticamente. L'intestazione contiene inoltre l'URI che indirizza la nuova risorsa di entità.  
  
- **Http delete** -Elimina i dati dell'entità rappresentati dalla risorsa specificata. Nei messaggi di richiesta o di risposta non è presente un payload.  
  
- **PUT http** : sostituisce i dati di entità esistenti in corrispondenza della risorsa richiesta con i nuovi dati forniti nel payload del messaggio di richiesta.  
  
- **Merge http** : a causa delle inefficienze nell'esecuzione di un'eliminazione seguita da un inserimento nell'origine dati solo per modificare i dati di [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] entità, introduce una nuova azione di Unione http. Il payload del messaggio di richiesta contiene le proprietà che devono essere modificate nella risorsa di entità indirizzata. Poiché l'azione MERGE HTTP non è definita nella specifica HTTP, è possibile che sia necessaria elaborazione aggiuntiva per indirizzare una richiesta MERGE HTTP tramite server non dotati di supporto per [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 Per ulteriori informazioni, vedere [OData: Operazioni](https://go.microsoft.com/fwlink/?LinkId=185792).  
  
### <a name="payload-formats"></a>Formati payload  
 Per una richiesta PUT HTTP, POST HTTP o MERGE HTTP, il payload di un messaggio di richiesta contiene i dati di entità da inviare al servizio dati. Il contenuto del payload dipende dal formato dei dati del messaggio. Tale payload è inoltre incluso nelle risposte HTTP a tutte le azioni, tranne DELETE. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]supporta i formati di payload seguenti per l'accesso e la modifica dei dati con il servizio:  
  
- **Atom** : codifica dei messaggi basata su XML definita da [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] come estensione del protocollo di pubblicazione Atom (AtomPub) per abilitare lo scambio di dati su http per feed Web, podcast, wiki e funzionalità Internet basate su XML. Per ulteriori informazioni, vedere [OData: Formato](https://go.microsoft.com/fwlink/?LinkId=185794)Atom.  
  
- **JSON** -JavaScript Object Notation (JSON) è un formato di interscambio dati leggero basato su un subset del linguaggio di programmazione JavaScript. Per ulteriori informazioni, vedere [OData: Formato](https://go.microsoft.com/fwlink/?LinkId=185795)JSON.  
  
 Il formato del messaggio per il payload deve essere incluso nell'intestazione del messaggio di richiesta HTTP. Per ulteriori informazioni, vedere [OData: Operazioni](https://go.microsoft.com/fwlink/?LinkID=185792).  
  
## <a name="accessing-and-changing-data-using-client-libraries"></a>Accesso ai dati e relativa modifica tramite le librerie client  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]include librerie client che consentono di utilizzare più facilmente un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed da applicazioni client basate su .NET Framework e Silverlight. Queste librerie semplificano l'invio e la ricezione di messaggi HTTP, oltre a convertire il payload del messaggio in oggetti CLR che rappresentano dati di entità. Le librerie client rendono disponibili le due classi principali <xref:System.Data.Services.Client.DataServiceContext> e <xref:System.Data.Services.Client.DataServiceQuery%601> che consentono di eseguire una query su un servizio dati e di usare quindi i dati di entità restituiti come oggetti CLR. Per ulteriori informazioni, vedere [WCF Data Services libreria client](wcf-data-services-client-library.md) e [WCF Data Services (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)).  
  
 È possibile usare la finestra di dialogo **Aggiungi riferimento al servizio** in Visual Studio per aggiungere un riferimento a un servizio dati. Questo strumento richiede i metadati del servizio a un servizio dati a cui viene fatto riferimento e genera l'oggetto <xref:System.Data.Services.Client.DataServiceContext> che rappresenta un servizio dati, oltre a generare le classi del servizio dati client che rappresentano entità. Per ulteriori informazioni, vedere [generazione della libreria client del servizio dati](generating-the-data-service-client-library-wcf-data-services.md).  
  
 Sono disponibili librerie di programmazione che è possibile usare per utilizzare un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in altri tipi di applicazioni client. Per ulteriori informazioni, vedere [OData SDK](https://go.microsoft.com/fwlink/?LinkId=185796).  
  
## <a name="see-also"></a>Vedere anche

- [Accesso alle risorse di un servizio dati](accessing-data-service-resources-wcf-data-services.md)
- [Guida rapida](quickstart-wcf-data-services.md)

---
title: Utilizzo di un servizio dati in un'applicazione client (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, getting started
ms.assetid: 90872d0c-e989-4490-b3e9-54afb10d33d4
ms.openlocfilehash: db802e127cacec2243741310b8a885c7ffcd24e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736994"
---
# <a name="using-a-data-service-in-a-client-application-wcf-data-services"></a>Utilizzo di un servizio dati in un'applicazione client (WCF Data Services)
È possibile accedere a un servizio che espone un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed specificando un URI a un Web browser. L'URI fornisce l'indirizzo di una risorsa e i messaggi di richiesta vengono inviati a questi indirizzi per accedere ai dati sottostanti rappresentati dalla risorsa o per modificarli. Il browser invia un comando GET HTTP e restituisce la risorsa richiesta come feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Per altre informazioni, vedere [accesso al servizio da un Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
 Sebbene l'uso di un browser possa risultare utile per verificare che un servizio [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] restituisca i dati previsti, l'accesso ai servizi [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] di produzione che consentono inoltre di creare, aggiornare ed eliminare dati viene in genere eseguito tramite linguaggi di codice delle applicazioni o di script in una pagina Web. In questo argomento viene fornita una panoramica di come accedere a [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed da un'applicazione client.  
  
## <a name="accessing-and-changing-data-using-rest-semantics"></a>Accesso ai dati e relativa modifica tramite la semantica REST  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] garantisce l'interoperabilità tra servizi che espongono [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] newsfeed e le applicazioni che utilizzano [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed. Applicazioni di accedere e modificare i dati in un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-servizio basato su inviando messaggi di richiesta di un'azione HTTP specifica e utilizzando un URI che indirizza una risorsa di entità sulla quale deve essere eseguita l'azione. I dati di entità necessari vengono forniti come payload codificato in modo appropriato nel corpo del messaggio.  
  
### <a name="http-actions"></a>Azioni HTTP  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] supporta le azioni HTTP riportate di seguito per l'esecuzione di operazioni di creazione, lettura, aggiornamento ed eliminazione sui dati di entità rappresentati dalla risorsa indirizzata.  
  
-   **HTTP GET** -si tratta dell'azione predefinita quando si accede a una risorsa da un browser. Nel messaggio di richiesta non viene fornito alcun payload e viene restituito un metodo di risposta con un payload contenente i dati richiesti.  
  
-   **Richiesta HTTP POST** -inserisce nuovi dati di entità nella risorsa fornita. I dati da inserire vengono forniti nel payload del messaggio di richiesta. Il payload del messaggio di risposta contiene i dati per l'entità appena creata, inclusi i valori della chiave generati automaticamente. L'intestazione contiene inoltre l'URI che indirizza la nuova risorsa di entità.  
  
-   **HTTP DELETE** -Elimina i dati di entità rappresentati dalla risorsa specificata. Nei messaggi di richiesta o di risposta non è presente un payload.  
  
-   **PUT HTTP** : sostituisce i dati di entità in corrispondenza della risorsa richiesta con i nuovi dati forniti nel payload del messaggio di richiesta esistenti.  
  
-   **MERGE HTTP** : a causa delle inefficienze durante l'esecuzione di un'eliminazione seguita da un'operazione di inserimento nell'origine dati allo scopo di modificare i dati di entità, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] introduce una nuova azione MERGE HTTP. Il payload del messaggio di richiesta contiene le proprietà che devono essere modificate nella risorsa di entità indirizzata. Poiché l'azione MERGE HTTP non è definita nella specifica HTTP, è possibile che sia necessaria elaborazione aggiuntiva per indirizzare una richiesta MERGE HTTP tramite server non dotati di supporto per [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 Per altre informazioni, vedere [OData: Operazioni](https://go.microsoft.com/fwlink/?LinkId=185792).  
  
### <a name="payload-formats"></a>Formati payload  
 Per una richiesta PUT HTTP, POST HTTP o MERGE HTTP, il payload di un messaggio di richiesta contiene i dati di entità da inviare al servizio dati. Il contenuto del payload dipende dal formato dei dati del messaggio. Tale payload è inoltre incluso nelle risposte HTTP a tutte le azioni, tranne DELETE. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] supporta i formati di payload seguenti per l'accesso e modifica dei dati con il servizio:  
  
-   **Atom** -codifica di messaggi basati su XML definita da [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] come estensione al protocollo di pubblicazione Atom (AtomPub) per scambio di dati su HTTP per feed Web, podcast, Wiki e funzionalità Internet basate su XML. Per altre informazioni, vedere [OData: Formato Atom](https://go.microsoft.com/fwlink/?LinkId=185794).  
  
-   **JSON** -JavaScript Object Notation (JSON) è un formato di interscambio dei dati leggero basato su un subset del linguaggio di programmazione JavaScript. Per altre informazioni, vedere [OData: Formato JSON](https://go.microsoft.com/fwlink/?LinkId=185795).  
  
 Il formato del messaggio per il payload deve essere incluso nell'intestazione del messaggio di richiesta HTTP. Per altre informazioni, vedere [OData: Operazioni](https://go.microsoft.com/fwlink/?LinkID=185792).  
  
## <a name="accessing-and-changing-data-using-client-libraries"></a>Accesso ai dati e relativa modifica tramite le librerie client  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] include librerie client che consentono di usare più facilmente un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed da .NET Framework e applicazioni client basate su Silverlight. Queste librerie semplificano l'invio e la ricezione di messaggi HTTP, oltre a convertire il payload del messaggio in oggetti CLR che rappresentano dati di entità. Le librerie client rendono disponibili le due classi principali <xref:System.Data.Services.Client.DataServiceContext> e <xref:System.Data.Services.Client.DataServiceQuery%601> che consentono di eseguire una query su un servizio dati e di usare quindi i dati di entità restituiti come oggetti CLR. Per altre informazioni, vedere [libreria Client di WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md) e [WCF Data Services (Silverlight)](https://msdn.microsoft.com/library/c0cd9f4b-1372-48e4-9935-c8421239da30).  
  
 È possibile usare la **Aggiungi riferimento al servizio** finestra di dialogo in Visual Studio per aggiungere un riferimento a un servizio dati. Questo strumento richiede i metadati del servizio a un servizio dati a cui viene fatto riferimento e genera l'oggetto <xref:System.Data.Services.Client.DataServiceContext> che rappresenta un servizio dati, oltre a generare le classi del servizio dati client che rappresentano entità. Per altre informazioni, vedere [generazione della libreria Client di servizio dati](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).  
  
 Sono disponibili librerie di programmazione disponibili che è possibile usare per utilizzare un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in altri tipi di applicazioni client. Per altre informazioni, vedere la [OData SDK](https://go.microsoft.com/fwlink/?LinkId=185796).  
  
## <a name="see-also"></a>Vedere anche
- [Accesso alle risorse di un servizio dati](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
- [Guida rapida](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

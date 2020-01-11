---
title: Utilizzo di un servizio dati in un'applicazione client (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, getting started
ms.assetid: 90872d0c-e989-4490-b3e9-54afb10d33d4
ms.openlocfilehash: 41d3af831ff3c99e7f3000593db52d307d37ac38
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900900"
---
# <a name="using-a-data-service-in-a-client-application-wcf-data-services"></a>Utilizzo di un servizio dati in un'applicazione client (WCF Data Services)
È possibile accedere a un servizio che espone un feed di Open Data Protocol (OData) fornendo un URI a una Web browser. L'URI fornisce l'indirizzo di una risorsa e i messaggi di richiesta vengono inviati a questi indirizzi per accedere ai dati sottostanti rappresentati dalla risorsa o per modificarli. Il browser invia un comando HTTP GET e restituisce la risorsa richiesta come feed OData. Per ulteriori informazioni, vedere [accesso al servizio da un Web browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
 Sebbene un Web browser possa risultare utile per verificare che un servizio OData restituisca i dati previsti, i servizi OData di produzione che consentono di creare, aggiornare ed eliminare i dati sono in genere accessibili dal codice dell'applicazione o dai linguaggi di scripting in una pagina Web. In questo argomento viene fornita una panoramica su come accedere ai feed OData da un'applicazione client.  
  
## <a name="accessing-and-changing-data-using-rest-semantics"></a>Accesso ai dati e relativa modifica tramite la semantica REST  
 OData consente di garantire l'interoperabilità tra i servizi che espongono feed OData e applicazioni che utilizzano feed OData. Le applicazioni accedono ai dati in un servizio basato su OData e li modificano inviando messaggi di richiesta di un'azione HTTP specifica e con un URI che indirizza una risorsa di entità sulla quale deve essere eseguita l'azione. I dati di entità necessari vengono forniti come payload codificato in modo appropriato nel corpo del messaggio.  
  
### <a name="http-actions"></a>Azioni HTTP  
 OData supporta le azioni HTTP seguenti per eseguire operazioni di creazione, lettura, aggiornamento ed eliminazione sui dati di entità rappresentati dalla risorsa interessata:  
  
- **Http Get** : questa è l'azione predefinita quando si accede a una risorsa da un browser. Nel messaggio di richiesta non viene fornito alcun payload e viene restituito un metodo di risposta con un payload contenente i dati richiesti.  
  
- **Http post** -inserisce i nuovi dati di entità nella risorsa fornita. I dati da inserire vengono forniti nel payload del messaggio di richiesta. Il payload del messaggio di risposta contiene i dati per l'entità appena creata, inclusi i valori della chiave generati automaticamente. L'intestazione contiene inoltre l'URI che indirizza la nuova risorsa di entità.  
  
- **Http delete** -Elimina i dati dell'entità rappresentati dalla risorsa specificata. Nei messaggi di richiesta o di risposta non è presente un payload.  
  
- **PUT http** : sostituisce i dati di entità esistenti in corrispondenza della risorsa richiesta con i nuovi dati forniti nel payload del messaggio di richiesta.  
  
- **Merge http** : a causa delle inefficienze nell'esecuzione di un'eliminazione seguita da un inserimento nell'origine dati solo per modificare i dati di entità, OData introduce una nuova azione di merge http. Il payload del messaggio di richiesta contiene le proprietà che devono essere modificate nella risorsa di entità indirizzata. Poiché l'Unione HTTP non è definita nella specifica HTTP, potrebbe essere necessaria un'elaborazione aggiuntiva per indirizzare una richiesta MERGE HTTP tramite server non compatibili con OData.  
  
 Per ulteriori informazioni, vedere [OData: operazioni](https://www.odata.org/documentation/odata-version-2-0/operations/).
  
### <a name="payload-formats"></a>Formati payload  
 Per una richiesta PUT HTTP, POST HTTP o MERGE HTTP, il payload di un messaggio di richiesta contiene i dati di entità da inviare al servizio dati. Il contenuto del payload dipende dal formato dei dati del messaggio. Tale payload è inoltre incluso nelle risposte HTTP a tutte le azioni, tranne DELETE. OData supporta i formati di payload seguenti per l'accesso e la modifica dei dati con il servizio:  
  
- **Atom** : codifica dei messaggi basata su XML definita da OData come estensione del protocollo di pubblicazione Atom (AtomPub) per abilitare lo scambio di dati su http per feed Web, podcast, wiki e funzionalità Internet basate su XML. Per ulteriori informazioni, vedere [OData: formato Atom](https://www.odata.org/documentation/odata-version-2-0/atom-format/).
  
- **JSON** -JavaScript Object Notation (JSON) è un formato di interscambio dati leggero basato su un subset del linguaggio di programmazione JavaScript. Per altre informazioni, vedere [OData: formato JSON](https://www.odata.org/documentation/odata-version-2-0/json-format/).
  
 Il formato del messaggio per il payload deve essere incluso nell'intestazione del messaggio di richiesta HTTP. Per ulteriori informazioni, vedere [OData: operazioni](https://www.odata.org/documentation/odata-version-2-0/operations/).
  
## <a name="accessing-and-changing-data-using-client-libraries"></a>Accesso ai dati e relativa modifica tramite le librerie client  
 WCF Data Services include librerie client che consentono di utilizzare più facilmente un feed OData da applicazioni client .NET Framework e basate su Silverlight. Queste librerie semplificano l'invio e la ricezione di messaggi HTTP, oltre a convertire il payload del messaggio in oggetti CLR che rappresentano dati di entità. Le librerie client rendono disponibili le due classi principali <xref:System.Data.Services.Client.DataServiceContext> e <xref:System.Data.Services.Client.DataServiceQuery%601> che consentono di eseguire una query su un servizio dati e di usare quindi i dati di entità restituiti come oggetti CLR. Per ulteriori informazioni, vedere [WCF Data Services libreria client](wcf-data-services-client-library.md) e [WCF Data Services (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)).  
  
 È possibile usare la finestra di dialogo **Aggiungi riferimento al servizio** in Visual Studio per aggiungere un riferimento a un servizio dati. Questo strumento richiede i metadati del servizio a un servizio dati a cui viene fatto riferimento e genera l'oggetto <xref:System.Data.Services.Client.DataServiceContext> che rappresenta un servizio dati, oltre a generare le classi del servizio dati client che rappresentano entità. Per ulteriori informazioni, vedere [generazione della libreria client del servizio dati](generating-the-data-service-client-library-wcf-data-services.md).  
  
 Sono disponibili librerie di programmazione che è possibile usare per utilizzare un feed OData in altri tipi di applicazioni client. Per ulteriori informazioni su OData SDK, vedere [OData SDK-codice di esempio](https://www.odata.org/ecosystem/#sdk).
  
## <a name="see-also"></a>Vedere anche

- [Accesso alle risorse di un servizio dati](accessing-data-service-resources-wcf-data-services.md)
- [Guida rapida](quickstart-wcf-data-services.md)

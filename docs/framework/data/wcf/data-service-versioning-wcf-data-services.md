---
title: Controllo delle versioni del servizio dati (WCF Data Services)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- versioning, WCF Data Services
- versioning [WCF Data Services]
- WCF Data Services, versioning
ms.assetid: e3e899cc-7f25-4f67-958f-063f01f79766
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6d800b35a69c08ab9f7bd90165691eab7d8743f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="data-service-versioning-wcf-data-services"></a>Controllo delle versioni del servizio dati (WCF Data Services)
Il [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] consente di creare servizi dati in modo che i client possono accedere ai dati come risorse usando URI basati su un modello di dati. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] supporta inoltre la definizione di operazioni del servizio. Dopo la distribuzione iniziale e, potenzialmente, più volte durante il loro ciclo di vita, potrebbe essere necessario cambiare questi servizi dati per molteplici ragioni, ad esempio perché cambiano le esigenze aziendali, i requisiti IT o per risolvere altri problemi. Quando si apportano modifiche a un servizio dati esistente, è necessario valutare se definire una nuova versione del servizio dati e il modo migliore per ridurre l'impatto sulle applicazioni client esistenti. In questo argomento vengono fornite informazioni su quando e come creare una nuova versione di un servizio dati. Viene inoltre descritto il modo in cui in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] viene gestito uno scambio tra client e servizi dati che supportano versioni diverse del protocollo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
## <a name="versioning-a-wcf-data-service"></a>Controllo delle versioni di un'istanza di WCF Data Services  
 Una volta che un servizio dati viene distribuito e i dati vengono usati, le modifiche apportate al servizio dati potrebbero provocare problemi di compatibilità con le applicazioni client esistenti. Tuttavia, perché le modifiche spesso sono richieste dalle esigenze aziendali complessive relative al servizio, è necessario considerare quando e come creare una nuova versione del servizio dati con il minimo impatto sulle applicazioni client.  
  
### <a name="data-model-changes-that-recommend-a-new-data-service-version"></a>Modifiche al modello di dati per cui è consigliabile usare una nuova versione del servizio dati  
 Quando si valuta se pubblicare una nuova versione di un servizio dati, è importante capire come i tipi diversi di modifiche possano influire sulle applicazioni client. Le modifiche a un servizio dati che potrebbero richiedere la creazione di una nuova versione di un servizio dati possono essere divise nelle due categorie seguenti:  
  
-   Modifiche al contratto del servizio, ossia aggiornamenti alle operazioni del servizio e all'accessibilità di set di entità (feed), modifiche alle versioni e altre modifiche ai comportamenti del servizio.  
  
-   Modifiche al contratto dati, ossia modifiche al modello di dati o ai formati o alle personalizzazioni di feed.  
  
 Nella tabella seguente sono contenute informazioni dettagliate sui tipi di modifiche che è necessario valutare per pubblicare una nuova versione del servizio dati:  
  
|Tipo di modifica|Nuova versione richiesta|Nuova versione non necessaria|  
|--------------------|----------------------------|----------------------------|  
|Operazioni di servizio|-Aggiungi nuovo parametro<br />-Modificare il tipo restituito<br />-Operazione di rimozione del servizio|-Consente di eliminare un parametro esistente<br />-Operazione di aggiunta del nuovo servizio|  
|Comportamenti del servizio|-Disabilita le richieste di conteggio<br />-Disabilita supporto della proiezione<br />-Incrementare la versione del servizio dati richiesta|-Abilitare le richieste di conteggio<br />-Abilitare il supporto di proiezione<br />-Diminuire la versione del servizio dati richiesta|  
|Autorizzazioni del set di entità|-Consente di limitare le autorizzazioni di set di entità<br />-Modificare il codice di risposta (nuovo valore della prima cifra) <sup>1</sup>|-Ridurre le autorizzazioni del set di entità<br />-Modificare il codice di risposta (stesso valore della prima cifra)|  
|Proprietà delle entità|-Rimuovere proprietà esistente o relazione<br />-Aggiungere proprietà che non ammette valori null<br />-Consente di modificare una proprietà esistente|-Aggiungere proprietà nullable<sup>2</sup>|  
|Set di entità|-Rimuovere i set di entità|-Aggiungere un tipo derivato<br />-Modificare il tipo di base<br />-Aggiungere set di entità|  
|Personalizzazione di feed|-Modificare il mapping di proprietà di entità||  
  
 <sup>1</sup> può dipendere da quanto un'applicazione client si basa sul ricevimento di un codice di errore specifico.  
  
 <sup>2</sup> è possibile impostare il <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> proprietà `true` in modo che il client ignori qualsiasi nuova proprietà inviata dal servizio dati che non sono definiti nel client. Tuttavia, quando vengono eseguiti inserimenti, le proprietà non incluse dal client nella richiesta POST vengono impostate sui valori predefiniti. Per gli aggiornamenti, qualsiasi dato esistente in una proprietà sconosciuto al client potrebbe essere sovrascritto da valori predefiniti. In questo caso, è necessario inviare l'aggiornamento come una richiesta MERGE (impostazione predefinita). Per ulteriori informazioni, vedere [gestione del contesto del servizio dati](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md).  
  
### <a name="how-to-version-a-data-service"></a>Come controllare le versioni di un servizio dati  
 Se necessario, una nuova versione del servizio dati viene definita creando una nuova istanza del servizio con un contratto di servizio o un modello di dati aggiornato. Questo nuovo servizio viene quindi esposto tramite un nuovo endpoint dell'URI che lo differenzia dalla versione precedente. Ad esempio:  
  
-   Versione obsoleta: `http://services.odata.org/Northwind/v1/Northwind.svc/`  
  
-   Nuova versione: `http://services.odata.org/Northwind/v2/Northwind.svc/`  
  
 Quando si aggiorna un servizio dati, sarà necessario inoltre aggiornare i client in base ai nuovi metadati del servizio dati e usare il nuovo URI radice. Quando possibile, è necessario gestire la versione precedente del servizio dati per supportare i client non ancora aggiornati per usare la nuova versione. Quando non sono più necessarie, le versioni precedenti di un servizio dati possono essere rimosse. È opportuno valutare la gestione dell'URI dell'endpoint del servizio dati in file di configurazione esterno.  
  
## <a name="odata-protocol-versions"></a>Versioni del protocollo OData  
 Nuove versioni di [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] vengono rilasciati, le applicazioni client potrebbero non essere utilizzando la stessa versione del [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocollo supportato dal servizio dati. È possibile che un'applicazione client meno recente acceda a un servizio dati che supporta una versione più recente di [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Un'applicazione client può inoltre usare una versione più recente di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] libreria client, che supporta una versione più recente di [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] rispetto a quello del servizio dati che si accede.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] sfrutta il supporto fornito da [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] per gestire tali scenari di controllo delle versioni. È inoltre disponibile il supporto per la generazione e l'utilizzo di metadati del modello di dati per creare le classi del servizio dati client quando il client utilizza una versione diversa di [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] rispetto al servizio dati utilizzato. Per ulteriori informazioni, vedere [OData: controllo delle versioni protocollo](http://go.microsoft.com/fwlink/?LinkId=186071).  
  
### <a name="version-negotiation"></a>Negoziazione della versione  
 Il servizio dati può essere configurato per definire la versione più recente del [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocollo che verrà utilizzato dal servizio, indipendentemente dalla versione richiesta dal client. È possibile eseguire questa operazione specificando un <xref:System.Data.Services.Common.DataServiceProtocolVersion> valore per il <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> proprietà del <xref:System.Data.Services.DataServiceBehavior> utilizzato dal servizio dati. Per ulteriori informazioni, vedere [configurazione del servizio dati](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Quando un'applicazione usa le librerie client [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] per accedere a un servizio dati, le intestazioni delle librerie vengono impostate automaticamente sui valori corretti, a seconda della versione di [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] e delle caratteristiche usate nell'applicazione. Per impostazione predefinita, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] utilizza la versione minima del protocollo che supporta l'operazione richiesta.  
  
 Nella tabella seguente sono contenuti i dettagli delle versioni di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] e [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] che includono il supporto [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] per versioni specifiche del protocollo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
|Versione del protocollo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]|Supporto introdotto in…|  
|-----------------------------------------------------------------------------------|----------------------------|  
|Versione 1|-   [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] Service Pack 1 (SP1)<br />-   [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] versione 3|  
|Versione 2|-   [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]<br />-L'aggiornamento di [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] SP1. È possibile scaricare e installare l'aggiornamento di [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=158125).<br />-   [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] versione 4|  
|Versione 3|-È possibile scaricare e installare una versione preliminare che supporta [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] versione 3 dal [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=203885).|  
  
### <a name="metadata-versions"></a>Versioni di metadati  
 Per impostazione predefinita, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] usa la versione 1.1 di CSDL per rappresentare un modello di dati. Questo comportamento viene applicato sempre nel caso di modelli di dati basati su un provider di reflection o un provider del servizio dati personalizzato. Tuttavia, quando il modello di dati è definito tramite [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)], viene restituita la stessa versione di CSDL usata da [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]. La versione del linguaggio CSDL è determinata dallo spazio dei nomi del [elemento dello Schema](http://msdn.microsoft.com/library/396074d8-f99c-4f50-a073-68bce848224f). Per altre informazioni, vedere la specifica [ \[MC-CSDL\]: formato di File di definizione dello Schema concettuale](http://go.microsoft.com/fwlink/?LinkId=159072).  
  
 L'elemento `DataServices` dei metadati restituiti contiene inoltre un attributo `DataServiceVersion` che corrisponde al valore dell'intestazione `DataServiceVersion` nel messaggio di risposta. Le applicazioni client, ad esempio il **Aggiungi riferimento al servizio** finestra di dialogo in Visual Studio, usare queste informazioni per generare il servizio dati client classi che funzionano correttamente con la versione di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] che funge da host del servizio dati. Per ulteriori informazioni, vedere [OData: controllo delle versioni protocollo](http://go.microsoft.com/fwlink/?LinkId=186071).  
  
## <a name="see-also"></a>Vedere anche  
 [Provider di servizi dati](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Definizione di WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)

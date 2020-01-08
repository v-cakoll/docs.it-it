---
title: Controllo delle versioni del servizio dati (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- versioning, WCF Data Services
- versioning [WCF Data Services]
- WCF Data Services, versioning
ms.assetid: e3e899cc-7f25-4f67-958f-063f01f79766
ms.openlocfilehash: 341cd8e21b84b220236947bca50311e5a1a75c72
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346116"
---
# <a name="data-service-versioning-wcf-data-services"></a>Controllo delle versioni del servizio dati (WCF Data Services)
Il Open Data Protocol (OData) consente di creare servizi dati in modo che i client possano accedere ai dati come risorse usando gli URI basati su un modello di dati. OData supporta inoltre la definizione di operazioni del servizio. Dopo la distribuzione iniziale e, potenzialmente, più volte durante il loro ciclo di vita, potrebbe essere necessario cambiare questi servizi dati per molteplici ragioni, ad esempio perché cambiano le esigenze aziendali, i requisiti IT o per risolvere altri problemi. Quando si apportano modifiche a un servizio dati esistente, è necessario valutare se definire una nuova versione del servizio dati e il modo migliore per ridurre l'impatto sulle applicazioni client esistenti. In questo argomento vengono fornite informazioni su quando e come creare una nuova versione di un servizio dati. Viene inoltre descritto il modo in cui WCF Data Services gestisce uno scambio tra client e servizi dati che supportano versioni diverse del protocollo OData.

## <a name="versioning-a-wcf-data-service"></a>Controllo delle versioni di un'istanza di WCF Data Services
 Una volta che un servizio dati viene distribuito e i dati vengono usati, le modifiche apportate al servizio dati potrebbero provocare problemi di compatibilità con le applicazioni client esistenti. Tuttavia, perché le modifiche spesso sono richieste dalle esigenze aziendali complessive relative al servizio, è necessario considerare quando e come creare una nuova versione del servizio dati con il minimo impatto sulle applicazioni client.

### <a name="data-model-changes-that-recommend-a-new-data-service-version"></a>Modifiche al modello di dati per cui è consigliabile usare una nuova versione del servizio dati
 Quando si valuta se pubblicare una nuova versione di un servizio dati, è importante capire come i tipi diversi di modifiche possano influire sulle applicazioni client. Le modifiche a un servizio dati che potrebbero richiedere la creazione di una nuova versione di un servizio dati possono essere divise nelle due categorie seguenti:

- Modifiche al contratto del servizio, ossia aggiornamenti alle operazioni del servizio e all'accessibilità di set di entità (feed), modifiche alle versioni e altre modifiche ai comportamenti del servizio.

- Modifiche al contratto dati, ossia modifiche al modello di dati o ai formati o alle personalizzazioni di feed.

 Nella tabella seguente sono contenute informazioni dettagliate sui tipi di modifiche che è necessario valutare per pubblicare una nuova versione del servizio dati:

|Tipo di modifica|Nuova versione richiesta|Nuova versione non necessaria|
|--------------------|----------------------------|----------------------------|
|Operazioni relative ai servizi|-Aggiungi nuovo parametro<br />-Modifica tipo restituito<br />-Rimuovi operazione del servizio|-Elimina parametro esistente<br />-Aggiungi nuova operazione del servizio|
|Comportamenti del servizio|-Disabilita richieste conteggio<br />-Disabilita supporto proiezione<br />-Aumentare la versione del servizio dati richiesta|-Abilita richieste count<br />-Abilita supporto proiezione<br />-Ridurre la versione del servizio dati richiesta|
|Autorizzazioni del set di entità|-Limitare le autorizzazioni del set di entità<br />-Modificare il codice di risposta (nuovo valore della prima cifra) <sup>1</sup>|-Autorizzazioni set di entità relax<br />-Modificare il codice di risposta (stesso valore della prima cifra)|
|Proprietà delle entità|-Rimuovere la proprietà o la relazione esistente<br />-Aggiungi proprietà che non ammette i valori null<br />-Modifica proprietà esistente|-Aggiungere la proprietà Nullable<sup>2</sup>|
|Set di entità|-Rimuovi set di entità|-Aggiungi tipo derivato<br />-Modifica tipo di base<br />-Aggiungi set di entità|
|Personalizzazione di feed|-Modificare il mapping di proprietà-entità||

 <sup>1</sup> questo può dipendere dal modo in cui un'applicazione client si basa sulla ricezione di un codice di errore specifico.

 <sup>2</sup> è possibile impostare la proprietà <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> su `true` per fare in modo che il client ignori le nuove proprietà inviate dal servizio dati che non sono definite nel client. Tuttavia, quando vengono eseguiti inserimenti, le proprietà non incluse dal client nella richiesta POST vengono impostate sui valori predefiniti. Per gli aggiornamenti, qualsiasi dato esistente in una proprietà sconosciuto al client potrebbe essere sovrascritto da valori predefiniti. In questo caso, è necessario inviare l'aggiornamento come una richiesta MERGE (impostazione predefinita). Per ulteriori informazioni, vedere [gestione del contesto del servizio dati](managing-the-data-service-context-wcf-data-services.md).

### <a name="how-to-version-a-data-service"></a>Come controllare le versioni di un servizio dati
 Se necessario, una nuova versione del servizio dati viene definita creando una nuova istanza del servizio con un contratto di servizio o un modello di dati aggiornato. Questo nuovo servizio viene quindi esposto tramite un nuovo endpoint dell'URI che lo differenzia dalla versione precedente. Ad esempio:

- Versione obsoleta: `http://services.odata.org/Northwind/v1/Northwind.svc/`

- Nuova versione: `http://services.odata.org/Northwind/v2/Northwind.svc/`

 Quando si aggiorna un servizio dati, sarà necessario inoltre aggiornare i client in base ai nuovi metadati del servizio dati e usare il nuovo URI radice. Quando possibile, è necessario gestire la versione precedente del servizio dati per supportare i client non ancora aggiornati per usare la nuova versione. Quando non sono più necessarie, le versioni precedenti di un servizio dati possono essere rimosse. È opportuno valutare la gestione dell'URI dell'endpoint del servizio dati in file di configurazione esterno.

## <a name="odata-protocol-versions"></a>Versioni del protocollo OData
 Quando vengono rilasciate nuove versioni di OData, le applicazioni client potrebbero non utilizzare la stessa versione del protocollo OData supportato dal servizio dati. Un'applicazione client precedente può accedere a un servizio dati che supporta una versione più recente di OData. Un'applicazione client può inoltre utilizzare una versione più recente della libreria client di WCF Data Services, che supporta una versione più recente di OData rispetto al servizio dati a cui si accede.

 WCF Data Services sfrutta il supporto fornito da OData per gestire tali scenari di controllo delle versioni. È inoltre disponibile il supporto per la generazione e l'utilizzo di metadati del modello di dati per creare classi del servizio dati client quando il client utilizza una versione diversa di OData rispetto al servizio dati utilizzato da. Per ulteriori informazioni, vedere la sezione relativa al controllo delle versioni del protocollo nell'articolo relativo alla [Panoramica di OData](https://www.odata.org/documentation/odata-version-2-0/overview/) .

### <a name="version-negotiation"></a>Negoziazione della versione
 Il servizio dati può essere configurato per definire la versione più recente del protocollo OData che verrà usato dal servizio, indipendentemente dalla versione richiesta dal client. È possibile eseguire questa operazione specificando un valore <xref:System.Data.Services.Common.DataServiceProtocolVersion> per la proprietà <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> del <xref:System.Data.Services.DataServiceBehavior> utilizzato dal servizio dati. Per ulteriori informazioni, vedere [configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md).

 Quando un'applicazione usa le librerie client di WCF Data Services per accedere a un servizio dati, le librerie impostano automaticamente tali intestazioni sui valori corretti, a seconda della versione di OData e delle funzionalità usate nell'applicazione. Per impostazione predefinita, WCF Data Services utilizza la versione del protocollo più bassa che supporta l'operazione richiesta.

 Nella tabella seguente vengono illustrate in dettaglio le versioni di .NET Framework e Silverlight che includono WCF Data Services supporto per versioni specifiche del protocollo OData.

|Versione del protocollo OData|Supporto introdotto in…|
|-----------------------------------------------------------------------------------|----------------------------|
|Versione 1|-.NET Framework 3,5 Service Pack 1 (SP1)<br />-Silverlight versione 3|
|Versione 2|-.NET Framework 4<br />-Aggiornamento a .NET Framework 3,5 SP1. È possibile scaricare e installare l'aggiornamento dall' [area download Microsoft](https://go.microsoft.com/fwlink/?LinkId=158125).<br />-Silverlight versione 4|
|Versione 3|-È possibile scaricare e installare una versione non definitiva che supporta OData versione 3 dall' [area download Microsoft](https://go.microsoft.com/fwlink/?LinkId=203885).|

### <a name="metadata-versions"></a>Versioni di metadati
 Per impostazione predefinita, WCF Data Services USA la versione 1,1 di CSDL per rappresentare un modello di dati. Questo comportamento viene applicato sempre nel caso di modelli di dati basati su un provider di reflection o un provider del servizio dati personalizzato. Tuttavia, quando il modello di dati è definito tramite Entity Framework, viene restituita la stessa versione di CSDL utilizzata da Entity Framework. La versione di CSDL è determinata dallo spazio dei nomi dell' [elemento schema (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#schema-element-csdl).

 L'elemento `DataServices` dei metadati restituiti contiene inoltre un attributo `DataServiceVersion` che corrisponde al valore dell'intestazione `DataServiceVersion` nel messaggio di risposta. Le applicazioni client, ad esempio la finestra di dialogo **Aggiungi riferimento al servizio** in Visual Studio, utilizzano queste informazioni per generare classi del servizio dati client che funzionano correttamente con la versione di WCF Data Services che ospitano il servizio dati. Per ulteriori informazioni, vedere la sezione relativa al controllo delle versioni del protocollo nell'articolo relativo alla [Panoramica di OData](https://www.odata.org/documentation/odata-version-2-0/overview/) .

## <a name="see-also"></a>Vedere anche

- [Provider di servizi dati](data-services-providers-wcf-data-services.md)
- [Definizione di WCF Data Services](defining-wcf-data-services.md)

---
title: Controllo delle versioni del servizio dati (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- versioning, WCF Data Services
- versioning [WCF Data Services]
- WCF Data Services, versioning
ms.assetid: e3e899cc-7f25-4f67-958f-063f01f79766
ms.openlocfilehash: f82ab4c98e724bbed658a6c77de9c5a5d5c3390f
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121532"
---
# <a name="data-service-versioning-wcf-data-services"></a>Controllo delle versioni del servizio dati (WCF Data Services)
Il protocollo OData (Open Data Protocol) consente di creare servizi dati in modo che i client possano accedere ai dati come risorse utilizzando URI basati su un modello di dati. OData supporta anche la definizione di operazioni del servizio. Dopo la distribuzione iniziale e, potenzialmente, più volte durante il loro ciclo di vita, potrebbe essere necessario cambiare questi servizi dati per molteplici ragioni, ad esempio perché cambiano le esigenze aziendali, i requisiti IT o per risolvere altri problemi. Quando si apportano modifiche a un servizio dati esistente, è necessario valutare se definire una nuova versione del servizio dati e il modo migliore per ridurre l'impatto sulle applicazioni client esistenti. In questo argomento vengono fornite informazioni su quando e come creare una nuova versione di un servizio dati. Viene inoltre descritto come WCF Data ServicesWCF Data Services gestisce uno scambio tra client e servizi dati che supportano versioni diverse del protocollo OData.

## <a name="versioning-a-wcf-data-service"></a>Controllo delle versioni di un'istanza di WCF Data Services
 Una volta che un servizio dati viene distribuito e i dati vengono usati, le modifiche apportate al servizio dati potrebbero provocare problemi di compatibilità con le applicazioni client esistenti. Tuttavia, perché le modifiche spesso sono richieste dalle esigenze aziendali complessive relative al servizio, è necessario considerare quando e come creare una nuova versione del servizio dati con il minimo impatto sulle applicazioni client.

### <a name="data-model-changes-that-recommend-a-new-data-service-version"></a>Modifiche al modello di dati per cui è consigliabile usare una nuova versione del servizio dati
 Quando si valuta se pubblicare una nuova versione di un servizio dati, è importante capire come i tipi diversi di modifiche possano influire sulle applicazioni client. Le modifiche a un servizio dati che potrebbero richiedere la creazione di una nuova versione di un servizio dati possono essere divise nelle due categorie seguenti:

- Modifiche al contratto del servizio, ossia aggiornamenti alle operazioni del servizio e all'accessibilità di set di entità (feed), modifiche alle versioni e altre modifiche ai comportamenti del servizio.

- Modifiche al contratto dati, ossia modifiche al modello di dati o ai formati o alle personalizzazioni di feed.

 Nella tabella seguente sono contenute informazioni dettagliate sui tipi di modifiche che è necessario valutare per pubblicare una nuova versione del servizio dati:

|Tipo di modifica|Nuova versione richiesta|Nuova versione non necessaria|
|--------------------|----------------------------|----------------------------|
|Operazioni di servizio|- Aggiungi nuovo parametro<br />- Modificare il tipo restituito<br />- Rimuovere il funzionamento del servizio|- Elimina parametro esistente<br />- Aggiungere una nuova operazione del servizio- Add new service operation|
|Comportamenti del servizio|- Disabilitare le richieste di conteggio<br />- Disabilitare il supporto di proiezione<br />- Aumentare la versione del servizio dati richiesta- Increase the required data service version|- Abilitare le richieste di conteggio<br />- Abilita supporto di proiezione<br />- Diminuire la versione del servizio dati richiesta- Decrease the required data service version|
|Autorizzazioni del set di entità|- Limitare le autorizzazioni del set di entità- Restrict entity set permissions<br />- Modificare il codice di risposta (nuovo valore della prima cifra) <sup>1</sup>|- Rilassare le autorizzazioni del set di entità- Relax entity set permissions<br />- Modificare il codice di risposta (stesso valore della prima cifra)|
|Proprietà delle entità|- Rimuovere la proprietà o la relazione esistente<br />- Aggiungere proprietà non nullable- non-nullable property<br />- Modificare la proprietà esistente|- Aggiungere la proprietà nullable<sup>2-</sup> Add nullable property 2|
|Set di entità|- Rimuovi set di entità|- Aggiungi tipo derivato<br />- Modificare il tipo di base<br />- Aggiungi set di entità|
|Personalizzazione di feed|- Modificare il mapping delle proprietà di entità- Change entity-property mapping||

 <sup>1</sup> Questo può dipendere da quanto strettamente un'applicazione client si basa sulla ricezione di un codice di errore specifico.

 <sup>2</sup> È possibile <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> impostare la proprietà `true` in modo che il client ignori tutte le nuove proprietà inviate dal servizio dati non definite nel client. Tuttavia, quando vengono eseguiti inserimenti, le proprietà non incluse dal client nella richiesta POST vengono impostate sui valori predefiniti. Per gli aggiornamenti, qualsiasi dato esistente in una proprietà sconosciuto al client potrebbe essere sovrascritto da valori predefiniti. In questo caso, è necessario inviare l'aggiornamento come una richiesta MERGE (impostazione predefinita). Per ulteriori informazioni, vedere [Gestione del contesto del servizio dati](managing-the-data-service-context-wcf-data-services.md).

### <a name="how-to-version-a-data-service"></a>Come controllare le versioni di un servizio dati
 Se necessario, una nuova versione del servizio dati viene definita creando una nuova istanza del servizio con un contratto di servizio o un modello di dati aggiornato. Questo nuovo servizio viene quindi esposto tramite un nuovo endpoint dell'URI che lo differenzia dalla versione precedente. Ad esempio:

- Versione obsoleta: `http://services.odata.org/Northwind/v1/Northwind.svc/`

- Nuova versione: `http://services.odata.org/Northwind/v2/Northwind.svc/`

 Quando si aggiorna un servizio dati, sarà necessario inoltre aggiornare i client in base ai nuovi metadati del servizio dati e usare il nuovo URI radice. Quando possibile, è necessario gestire la versione precedente del servizio dati per supportare i client non ancora aggiornati per usare la nuova versione. Quando non sono più necessarie, le versioni precedenti di un servizio dati possono essere rimosse. È opportuno valutare la gestione dell'URI dell'endpoint del servizio dati in file di configurazione esterno.

## <a name="odata-protocol-versions"></a>Versioni del protocollo OData
 Man mano che vengono rilasciate nuove versioni di OData, le applicazioni client potrebbero non utilizzare la stessa versione del protocollo OData supportata dal servizio dati. Un'applicazione client precedente può accedere a un servizio dati che supporta una versione più recente di OData.An older client application may access a data service that supports a newer version of OData. Un'applicazione client può anche utilizzare una versione più recente della libreria client WCF Data ServicesWCF Data Services, che supporta una versione più recente di OData rispetto al servizio dati a cui si accede.

 WCF Data ServicesWCF Data Services sfrutta il supporto fornito da OData per gestire tali scenari di controllo delle versioni. È inoltre disponibile il supporto per la generazione e l'utilizzo di metadati del modello di dati per creare classi del servizio dati client quando il client utilizza una versione di OData diversa da quella utilizzata dal servizio dati. Per altre informazioni, vedere la sezione Controllo delle versioni del protocollo nell'articolo [OData: Overview.For](https://www.odata.org/documentation/odata-version-2-0/overview/) more information, see the Protocol Versioning section in the OData: Overview article.

### <a name="version-negotiation"></a>Negoziazione della versione
 Il servizio dati può essere configurato per definire la versione più elevata del protocollo OData che verrà utilizzata dal servizio, indipendentemente dalla versione richiesta dal client. A tale scopo, è <xref:System.Data.Services.Common.DataServiceProtocolVersion> possibile <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> specificare <xref:System.Data.Services.DataServiceBehavior> un valore per la proprietà dell'oggetto utilizzato dal servizio dati. Per ulteriori informazioni, vedere [Configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md).

 Quando un'applicazione utilizza le librerie client WCF Data ServicesWCF Data Services per accedere a un servizio dati, le librerie impostano automaticamente queste intestazioni sui valori corretti, a seconda della versione di OData e delle funzionalità utilizzate nell'applicazione. Per impostazione predefinita, WCF Data ServicesWCF Data Services usa la versione del protocollo più bassa che supporta l'operazione richiesta.

 Nella tabella seguente vengono descritte in dettaglio le versioni di .NET Framework e Silverlight che includono il supporto di WCF Data Services per versioni specifiche del protocollo OData.

|Versione protocollo OData|Supporto introdotto in…|
|-----------------------------------------------------------------------------------|----------------------------|
|Versione 1|- .NET Framework 3.5 Service Pack 1 (SP1)<br />- Silverlight versione 3|
|Versione 2|- .NET Framework 4<br />- Silverlight versione 4|

### <a name="metadata-versions"></a>Versioni di metadati
 Per impostazione predefinita, WCF Data ServicesWCF Data Services usa la versione 1.1 di CSDL per rappresentare un modello di dati. Questo comportamento viene applicato sempre nel caso di modelli di dati basati su un provider di reflection o un provider del servizio dati personalizzato. Tuttavia, quando il modello di dati è definito tramite Entity Framework, viene restituita la stessa versione di CSDL utilizzata da Entity Framework. La versione di CSDL è determinata dallo spazio dei nomi [dell'elemento Schema (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#schema-element-csdl).

 L'elemento `DataServices` dei metadati restituiti contiene inoltre un attributo `DataServiceVersion` che corrisponde al valore dell'intestazione `DataServiceVersion` nel messaggio di risposta. Le applicazioni client, ad esempio la finestra di dialogo **Aggiungi riferimento** al servizio in Visual Studio, usano queste informazioni per generare classi del servizio dati client che funzionano correttamente con la versione di WCF Data ServicesWCF Data Services che ospita il servizio dati. Per altre informazioni, vedere la sezione Controllo delle versioni del protocollo nell'articolo [OData: Overview.For](https://www.odata.org/documentation/odata-version-2-0/overview/) more information, see the Protocol Versioning section in the OData: Overview article.

## <a name="see-also"></a>Vedere anche

- [Provider di servizi dati](data-services-providers-wcf-data-services.md)
- [Definizione di WCF Data Services](defining-wcf-data-services.md)

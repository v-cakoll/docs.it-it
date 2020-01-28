---
title: Introduzione al routing
ms.date: 03/30/2017
ms.assetid: bf6ceb38-6622-433b-9ee7-f79bc93497a1
ms.openlocfilehash: 8ce98aab2ed14401fa7c2cbf43eb92a633fa96b0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746475"
---
# <a name="routing-introduction"></a>Introduzione al routing

Il servizio di routing fornisce un intermediario SOAP di collegamento generico in grado di indirizzare i messaggi in base al relativo contenuto. Il servizio di routing consente di creare logica di routing complessa per l'implementazione di scenari quali l'aggregazione dei servizi, il controllo delle versioni dei servizi, il routing prioritario e il routing multicast. Il servizio di routing offre inoltre funzionalità di gestione degli errori che consentono di configurare elenchi di endpoint di backup ai quali vengono inviati i messaggi se si verifica un errore di invio all'endpoint di destinazione primario.

Questo argomento è destinato a coloro i quali non hanno familiarità con il servizio di routing e ne illustra la configurazione di base e l'hosting.

## <a name="configuration"></a>Configurazione di

Il servizio di routing viene implementato come servizio WCF che espone uno o più endpoint servizio i quali ricevono i messaggi dalle applicazioni client e li indirizzano a uno o più endpoint di destinazione. Il servizio include un elemento <xref:System.ServiceModel.Routing.RoutingBehavior> che viene applicato agli endpoint servizio esposti. Questo comportamento viene usato per configurare diversi aspetti del funzionamento del servizio. Per semplificare la configurazione quando si usa un file di configurazione, i parametri vengono specificati in **RoutingBehavior**. Negli scenari basati sul codice, questi parametri vengono specificati come parte di un oggetto <xref:System.ServiceModel.Routing.RoutingConfiguration>, che può quindi essere passato a un **RoutingBehavior**.

Inizialmente, questo comportamento aggiunge agli endpoint client <xref:System.ServiceModel.Routing.SoapProcessingBehavior>, il quale è usato per eseguire l'elaborazione SOAP dei messaggi. Ciò consente al servizio di routing di trasmettere messaggi agli endpoint che richiedono un oggetto **MessageVersion** diverso rispetto all'endpoint su cui è stato ricevuto il messaggio. **RoutingBehavior** registra inoltre un'estensione del servizio, la <xref:System.ServiceModel.Routing.RoutingExtension>, che fornisce un punto di accessibilità per la modifica della configurazione del servizio di routing in fase di esecuzione.

La classe **RoutingConfiguration** fornisce un mezzo coerente per la configurazione e l'aggiornamento della configurazione del servizio di routing.  Contiene i parametri che fungono da impostazioni per il servizio di routing e viene usato per configurare il **RoutingBehavior** all'avvio del servizio o viene passato a **RoutingExtension** per modificare la configurazione del routing in fase di esecuzione.

La logica di routing usata per indirizzare i messaggi in base al contenuto viene definita raggruppando più oggetti <xref:System.ServiceModel.Dispatcher.MessageFilter> in tabelle di filtri (oggetti <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>). I messaggi in arrivo vengono valutati in base ai filtri messaggi contenuti nella tabella dei filtri e per ogni **MessageFilter** che corrisponde al messaggio, che viene inviato a un endpoint di destinazione. La tabella dei filtri da utilizzare per il routing dei messaggi viene specificata utilizzando **RoutingBehavior** nella configurazione o tramite codice tramite l'oggetto **RoutingConfiguration** .

### <a name="defining-endpoints"></a>Definizione di endpoint

Sebbene possa sembrare opportuno iniziare la configurazione definendo la logica di routing che verrà usata, è consigliabile che il primo passaggio consista nel determinare la forma degli endpoint a cui verranno indirizzati i messaggi. Il servizio di routing usa contratti che definiscono la forma dei canali usati per ricevere e inviare messaggi, pertanto la forma del canale di input deve corrispondere a quella del canale di output.  Se ad esempio si esegue il routing a endpoint che usano la forma del canale di tipo request/reply, è necessario usare un contratto compatibile negli endpoint in ingresso, ad esempio <xref:System.ServiceModel.Routing.IRequestReplyRouter>.

Ciò significa che se gli endpoint di destinazione usano contratti con più modelli di comunicazione (ad esempio una combinazione di operazioni unidirezionali e bidirezionali), non è possibile creare un singolo endpoint servizio in grado di ricevere e indirizzare i messaggi a tutti. È necessario determinare quali endpoint dispongono di forme compatibili e definire uno o più endpoint servizio che verranno usati per ricevere i messaggi da indirizzare agli endpoint di destinazione.

> [!NOTE]
> Quando si usano contratti che specificano più modelli di comunicazione (ad esempio una combinazione di operazioni unidirezionali e bidirezionali), una soluzione alternativa è rappresentata dall'uso di un contratto di tipo duplex nel servizio di routing, ad esempio <xref:System.ServiceModel.Routing.IDuplexSessionRouter>. Ciò implica tuttavia che l'associazione deve supportare la comunicazione duplex, il che potrebbe non essere possibile per tutti gli scenari. Negli scenari in cui questa soluzione non è possibile, può risultare necessario eseguire il factoring della comunicazione in più endpoint oppure modificare l'applicazione.

Per ulteriori informazioni sui contratti di routing, vedere [routing dei contratti](routing-contracts.md).

Dopo aver definito l'endpoint del servizio, è possibile usare **RoutingBehavior** per associare un **RoutingConfiguration** specifico all'endpoint. Quando si configura il servizio di routing utilizzando un file di configurazione, **RoutingBehavior** viene utilizzato per specificare la tabella dei filtri che contiene la logica di routing utilizzata per elaborare i messaggi ricevuti sull'endpoint. Se si configura il servizio di routing a livello di codice, è possibile specificare la tabella dei filtri utilizzando **RoutingConfiguration**.

Nell'esempio seguente gli endpoint servizio e client usati dal servizio di routing sono definiti sia a livello di codice sia tramite un file di configurazione.

```xml
<services>
  <!--ROUTING SERVICE -->
  <service behaviorConfiguration="routingData"
            name="System.ServiceModel.Routing.RoutingService">
    <host>
      <baseAddresses>
        <add baseAddress="http://localhost:8000/routingservice/router"/>
      </baseAddresses>
    </host>
    <!-- Define the service endpoints that are receive messages -->
    <endpoint address=""
              binding="wsHttpBinding"
              name="reqReplyEndpoint"
              contract="System.ServiceModel.Routing.IRequestReplyRouter" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="routingData">
      <serviceMetadata httpGetEnabled="True"/>
      <!-- Add the RoutingBehavior and specify the Routing Table to use -->
      <routing filterTableName="routingTable1" />
    </behavior>
  </serviceBehaviors>
</behaviors>
<client>
<!-- Define the client endpoint(s) to route messages to -->
  <endpoint name="CalculatorService"
            address="http://localhost:8000/servicemodelsamples/service"
            binding="wsHttpBinding" contract="*" />
</client>
```

```csharp
//set up some communication defaults
string clientAddress = "http://localhost:8000/servicemodelsamples/service";
string routerAddress = "http://localhost:8000/routingservice/router";
Binding routerBinding = new WSHttpBinding();
Binding clientBinding = new WSHttpBinding();
//add the endpoint the router uses to receive messages
serviceHost.AddServiceEndpoint(
     typeof(IRequestReplyRouter),
     routerBinding,
     routerAddress);
//create the client endpoint the router routes messages to
ContractDescription contract = ContractDescription.GetContract(
     typeof(IRequestReplyRouter));
ServiceEndpoint client = new ServiceEndpoint(
     contract,
     clientBinding,
     new EndpointAddress(clientAddress));
//create a new routing configuration object
RoutingConfiguration rc = new RoutingConfiguration();
….
rc.FilterTable.Add(new MatchAllMessageFilter(), endpointList);
//attach the behavior to the service host
serviceHost.Description.Behaviors.Add(
     new RoutingBehavior(rc));
```

In questo esempio il servizio di routing viene configurato per esporre un singolo endpoint con un indirizzo di `http://localhost:8000/routingservice/router`, che viene utilizzato per ricevere i messaggi da indirizzare. Poiché i messaggi vengono indirizzati agli endpoint di tipo request/reply, l'endpoint servizio usa il contratto <xref:System.ServiceModel.Routing.IRequestReplyRouter>. Questa configurazione definisce anche un endpoint client singolo di `http://localhost:8000/servicemodelsample/service` a cui vengono indirizzati i messaggi. La tabella dei filtri (non mostrata) denominata "routingTable1" contiene la logica di routing usata per indirizzare i messaggi ed è associata all'endpoint del servizio usando **RoutingBehavior** (per un file di configurazione) o **RoutingConfiguration** (per la configurazione a livello di codice).

### <a name="routing-logic"></a>Logica di routing

Per definire la logica di routing usata per indirizzare i messaggi, è necessario stabilire su quali dati contenuti nei messaggi in entrata è possibile intervenire in modo univoco. Se ad esempio tutti gli endpoint di destinazione del routing condividono le stesse azioni SOAP, il valore dell'elemento Action all'interno del messaggio non rappresenta un indicatore utile dell'endpoint specifico a cui deve essere indirizzato il messaggio. Se è necessario indirizzare i messaggi in modo univoco a un endpoint specifico, è consigliabile applicare filtri in base a dati che identificano in modo univoco l'endpoint di destinazione a cui il messaggio viene indirizzato.

Il servizio di routing fornisce diverse implementazioni di **MessageFilter** che controllano valori specifici all'interno del messaggio, ad esempio l'indirizzo, l'azione, il nome dell'endpoint o persino una query XPath. Se nessuna di queste implementazioni soddisfa le proprie esigenze, è possibile creare un'implementazione personalizzata di **MessageFilter** . Per ulteriori informazioni sui filtri messaggi e un confronto delle implementazioni utilizzate dal servizio di routing, vedere [filtri messaggi](message-filters.md) e [scelta di un filtro](choosing-a-filter.md).

Più filtri messaggi sono organizzati insieme in tabelle dei filtri, che associano ogni **MessageFilter** a un endpoint di destinazione. Facoltativamente, è inoltre possibile usare la tabella dei filtri per specificare un elenco di endpoint di backup a cui il servizio di routing tenterà di inviare il messaggio qualora si verifichi un errore di trasmissione.

Per impostazione predefinita, tutti i filtri messaggi all'interno di una tabella vengono valutati contemporaneamente. È tuttavia possibile specificare un oggetto <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.Priority%2A> che impone la valutazione dei filtri messaggi in un ordine specifico. Tutte le voci con priorità massima vengono valutati per primi, mentre i filtri dei messaggi di priorità inferiore non vengono valutati se viene individuata una corrispondenza a un livello di priorità superiore. Per ulteriori informazioni sulle tabelle dei filtri, vedere [filtri messaggi](message-filters.md).

Negli esempi seguenti viene usato <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>, il quale restituisce `true` per tutti i messaggi. Questo **MessageFilter** viene aggiunto alla tabella dei filtri "routingTable1", che associa **MessageFilter** all'endpoint client denominato "CalculatorService". **RoutingBehavior** specifica quindi che questa tabella deve essere utilizzata per indirizzare i messaggi elaborati dall'endpoint del servizio.

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name="routingData">
      <serviceMetadata httpGetEnabled="True"/>
      <!-- Add the RoutingBehavior and specify the Routing Table to use -->
      <routing filterTableName="routingTable1" />
    </behavior>
  </serviceBehaviors>
</behaviors>
<!--ROUTING SECTION -->
<routing>
  <filters>
    <filter name="MatchAllFilter1" filterType="MatchAll" />
  </filters>
  <filterTables>
    <table name="routingTable1">
      <filters>
        <add filterName="MatchAllFilter1" endpointName="CalculatorService" />
      </filters>
    </table>
  </filterTables>
</routing>
```

```csharp
//create a new routing configuration object
RoutingConfiguration rc = new RoutingConfiguration();
//create the endpoint list that contains the endpoints to route to
//in this case we have only one
List<ServiceEndpoint> endpointList = new List<ServiceEndpoint>();
endpointList.Add(client);
//add a MatchAll filter to the Router's filter table
//map it to the endpoint list defined earlier
//when a message matches this filter, it is sent to the endpoint contained in the list
rc.FilterTable.Add(new MatchAllMessageFilter(), endpointList);
```

> [!NOTE]
> Per impostazione predefinita, il servizio di routing valuta solo le intestazioni del messaggio. Per consentire ai filtri di accedere al corpo del messaggio, è necessario impostare <xref:System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly%2A> su `false`.

**Multicast**

Sebbene molte configurazioni del servizio di routing utilizzino logica di filtro esclusiva che indirizza i messaggi a un unico specifico endpoint, potrebbe essere necessario indirizzare il messaggio in questione a più endpoint di destinazione. Per il multicast di un messaggio a più destinazioni, è necessario che siano soddisfatte le condizioni seguenti:

- La forma del canale non deve essere di tipo request/reply (tuttavia può essere unidirezionale o duplex), poiché l'applicazione client può ricevere una sola risposta alla richiesta.

- Più filtri devono restituire `true` in seguito alla valutazione del messaggio.

Se vengono soddisfatte queste condizioni, il messaggio viene indirizzato a tutti gli endpoint di tutti i filtri che restituiscono `true`. Nell'esempio seguente viene definita una configurazione di routing che consente di indirizzare i messaggi a entrambi gli endpoint se l'indirizzo dell'endpoint nel messaggio è `http://localhost:8000/routingservice/router/rounding`.

```xml
<!--ROUTING SECTION -->
<routing>
  <filters>
    <filter name="MatchAllFilter1" filterType="MatchAll" />
    <filter name="RoundingFilter1" filterType="EndpointAddress"
            filterData="http://localhost:8000/routingservice/router/rounding" />
  </filters>
  <filterTables>
    <table name="routingTable1">
      <filters>
        <add filterName="MatchAllFilter1" endpointName="CalculatorService" />
        <add filterName="RoundingFilter1" endpointName="RoundingCalcService" />
      </filters>
    </table>
  </filterTables>
</routing>
```

```csharp
rc.FilterTable.Add(new MatchAllMessageFilter(), calculatorEndpointList);
rc.FilterTable.Add(new EndpointAddressMessageFilter(new EndpointAddress(
    "http://localhost:8000/routingservice/router/rounding")),
    roundingCalcEndpointList);
```

### <a name="soap-processing"></a>Elaborazione SOAP

Per supportare il routing dei messaggi tra protocolli diversi, per impostazione predefinita **RoutingBehavior** aggiunge il <xref:System.ServiceModel.Routing.SoapProcessingBehavior> a tutti gli endpoint client ai quali vengono indirizzati i messaggi. Questo comportamento crea automaticamente un nuovo oggetto **MessageVersion** prima di indirizzare il messaggio all'endpoint, nonché di creare un oggetto **MessageVersion** compatibile per qualsiasi documento di risposta prima di restituirlo all'applicazione client richiedente.

I passaggi necessari per creare un nuovo oggetto **MessageVersion** per il messaggio in uscita sono i seguenti:

**Elaborazione richieste**

- Ottenere l'oggetto **MessageVersion** del canale/binding in uscita.

- Ottenere il reader del corpo per il messaggio originale.

- Creare un nuovo messaggio con la stessa azione, il lettore del corpo e un nuovo elemento **MessageVersion**.

- Se <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>! = **Addressing. None**, copiare le intestazioni into, from, FaultTo e laTesto nel nuovo messaggio.

- Copiare tutte le proprietà del messaggio nel nuovo messaggio.

- Archiviare il messaggio di richiesta originale da usare per l'elaborazione della risposta.

- Restituire il nuovo messaggio di richiesta.

**Elaborazione della risposta**

- Ottiene l'oggetto **MessageVersion** del messaggio di richiesta originale.

- Ottenere il reader del corpo per il messaggio di risposta ricevuto.

- Creare un nuovo messaggio di risposta con la stessa azione, il lettore del corpo e l'oggetto **MessageVersion** del messaggio di richiesta originale.

- Se <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>! = **Addressing. None**, copiare le intestazioni into, from, FaultTo e laTesto nel nuovo messaggio.

- Copiare le proprietà del messaggio nel nuovo messaggio.

- Restituire il nuovo messaggio di risposta.

Per impostazione predefinita, **SoapProcessingBehavior** viene aggiunto automaticamente agli endpoint client dall'<xref:System.ServiceModel.Routing.RoutingBehavior> all'avvio del servizio. Tuttavia, è possibile controllare se l'elaborazione SOAP viene aggiunta a tutti gli endpoint client tramite la proprietà <xref:System.ServiceModel.Routing.RoutingConfiguration.SoapProcessingEnabled%2A>. È inoltre possibile aggiungere il comportamento direttamente a un endpoint specifico e abilitare o disabilitare tale comportamento al livello dell'endpoint se è necessario un controllo più granulare dell'elaborazione SOAP.

> [!NOTE]
> Se l'elaborazione SOAP è disabilitata per un endpoint che richiede un elemento MessageVersion diverso rispetto a quello del messaggio di richiesta originale, è necessario fornire un meccanismo personalizzato per l'esecuzione di eventuali modifiche SOAP da apportare prima dell'invio del messaggio all'endpoint di destinazione.

Negli esempi seguenti, la proprietà **SoapProcessingEnabled** viene usata per impedire che **SoapProcessingBehavior** venga aggiunto automaticamente a tutti gli endpoint client.

```xml
<behaviors>
  <!--default routing service behavior definition-->
  <serviceBehaviors>
    <behavior name="routingConfiguration">
      <routing filterTableName="filterTable1" soapProcessingEnabled="false"/>
    </behavior>
  </serviceBehaviors>
</behaviors>
```

```csharp
//create the default RoutingConfiguration
RoutingConfiguration rc = new RoutingConfiguration();
rc.SoapProcessingEnabled = false;
```

### <a name="dynamic-configuration"></a>configurazione dinamica

Quando si aggiungono ulteriori endpoint client oppure occorre modificare i filtri usati per il routing dei messaggi, è necessario disporre di un modo per aggiornare dinamicamente la configurazione in fase di esecuzione allo scopo di evitare interruzioni del servizio per gli endpoint attualmente definiti per la ricezione dei messaggi tramite il servizio di routing. La modifica di un file di configurazione o del codice dell'applicazione host non è sempre sufficiente poiché tali metodi richiedono il riciclo dell'applicazione, il che potrebbe causare la perdita di eventuali messaggi attualmente in transito nonché tempi di inattività durante l'attesa del riavvio del servizio.

È possibile modificare solo il **RoutingConfiguration** a livello di codice. Sebbene sia possibile configurare inizialmente il servizio usando un file di configurazione, è possibile modificare la configurazione solo in fase di esecuzione costruendo un nuovo **RoutingConfiguration** e passandolo come parametro al metodo <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> esposto dall'estensione del servizio <xref:System.ServiceModel.Routing.RoutingExtension>. Tutti i messaggi attualmente in transito continuano a essere instradati utilizzando la configurazione precedente, mentre i messaggi ricevuti dopo la chiamata a **ApplyConfiguration** utilizzano la nuova configurazione. Nell'esempio seguente viene illustrata la creazione di un'istanza del servizio di routing e successivamente la modifica della configurazione.

```csharp
RoutingConfiguration routingConfig = new RoutingConfiguration();
routingConfig.RouteOnHeadersOnly = true;
routingConfig.FilterTable.Add(new MatchAllMessageFilter(), endpointList);
RoutingBehavior routing = new RoutingBehavior(routingConfig);
routerHost.Description.Behaviors.Add(routing);
routerHost.Open();
// Construct a new RoutingConfiguration
RoutingConfiguration rc2 = new RoutingConfiguration();
ServiceEndpoint clientEndpoint = new ServiceEndpoint();
ServiceEndpoint clientEndpoint2 = new ServiceEndpoint();
// Add filters to the FilterTable in the new configuration
rc2.FilterTable.add(new MatchAllMessageFilter(),
       new List<ServiceEndpoint>() { clientEndpoint });
rc2.FilterTable.add(new MatchAllMessageFilter(),
       new List<ServiceEndpoint>() { clientEndpoint2 });
rc2.RouteOnHeadersOnly = false;
// Apply the new configuration to the Routing Service hosted in
routerHost.routerHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc2);
```

> [!NOTE]
> Per aggiornare il servizio di routing in questo modo è possibile passare solo una nuova configurazione. Non è possibile modificare solo elementi scelti della configurazione corrente o aggiungere nuove voci alla configurazione corrente. È necessario creare e passare una nuova configurazione che sostituisca quella esistente.

> [!NOTE]
> Le eventuali sessioni aperte usando la configurazione precedente continuano a usare quest'ultima. La nuova configurazione viene usata solo dalle nuove sessioni.

## <a name="error-handling"></a>Gestione degli errori

Se si verificano eccezioni <xref:System.ServiceModel.CommunicationException> durante il tentativo di inviare un messaggio, viene eseguita la gestione degli errori. Queste eccezioni indicano in genere che si è verificato un problema durante il tentativo di comunicare con l'endpoint client definito, ad esempio <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException> o <xref:System.ServiceModel.CommunicationObjectFaultedException>. Il codice di gestione degli errori intercetta inoltre e tenta di ritentare l'invio quando si verifica un <xref:System.TimeoutException>, ovvero un'altra eccezione comune non derivata da **CommunicationException**.

Quando si verifica una delle eccezioni precedenti, il servizio di routing esegue il failover a un elenco di endpoint di backup. Se in tutti gli endpoint di backup si verifica un errore di comunicazione oppure un endpoint restituisce un'eccezione indicante un errore all'interno del servizio di destinazione, il servizio di routing restituisce un errore all'applicazione client.

> [!NOTE]
> La funzionalità di gestione degli errori acquisisce e gestisce le eccezioni che si verificano quando si tenta di inviare un messaggio e di chiudere un canale. Il codice di gestione degli errori non è progettato per rilevare o gestire le eccezioni create dagli endpoint dell'applicazione con cui sta comunicando; una <xref:System.ServiceModel.FaultException> generata da un servizio viene visualizzata nel servizio di routing come **FaultMessage** e viene propagata al client.
>
> Se si verifica un errore quando il servizio di routing tenta di inoltrare un messaggio, potrebbe essere generata un'eccezione <xref:System.ServiceModel.FaultException> sul lato client, anziché l'eccezione <xref:System.ServiceModel.EndpointNotFoundException> che verrebbe generata di norma in assenza del servizio di routing. Un servizio di routing potrebbe quindi mascherare eventuali eccezioni e non fornire completa trasparenza a meno che non si esamino le eccezioni annidate.

### <a name="tracing-exceptions"></a>Traccia delle eccezioni

Quando si invia un messaggio a un endpoint in un elenco ha esito negativo, il servizio di routing traccia i dati dell'eccezione risultante e alleghi i dettagli dell'eccezione come proprietà del messaggio denominata **Exceptions**. Ciò consente di mantenere i dati dell'eccezione e l'accesso utente a livello di codice tramite un controllo messaggi.  I dati dell'eccezione vengono archiviati per ciascun messaggio in un dizionario che stabilisce il mapping del nome dell'endpoint ai dettagli dell'eccezione verificatasi durante il tentativo di inviare un messaggio.

### <a name="backup-endpoints"></a>Endpoint di backup

Ogni voce di filtro all'interno della tabella dei filtri può facoltativamente specificare un elenco di endpoint di backup da usare in caso di errore di trasmissione durante l'invio all'endpoint primario. Se si verifica un errore di questo tipo, il servizio di routing tenta di trasmettere il messaggio alla prima voce nell'elenco di endpoint di backup. Se durante il tentativo di invio si verifica un errore di trasmissione, viene eseguito un tentativo con l'endpoint successivo nell'elenco di quelli di backup. Il servizio di routing continua a inviare il messaggio a ogni endpoint nell'elenco finché il messaggio non viene ricevuto correttamente, tutti gli endpoint restituiscono un errore di trasmissione oppure viene restituito un errore non di trasmissione da un endpoint.

Negli esempi seguenti il servizio di routing viene configurato per l'uso di un elenco di backup.

```xml
<routing>
  <filters>
    <!-- Create a MatchAll filter that catches all messages -->
    <filter name="MatchAllFilter1" filterType="MatchAll" />
  </filters>
  <filterTables>
    <!-- Set up the Routing Service's Message Filter Table -->
    <filterTable name="filterTable1">
        <!-- Add an entry that maps the MatchAllMessageFilter to the dead destination -->
        <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->
        <!-- Listed in the backupEndpointList -->
        <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>
    </filterTable>
  </filterTables>
  <!-- Create the backup endpoint list -->
  <backupLists>
    <!-- Add an endpoint list that contains the backup destinations -->
    <backupList name="backupEndpointList">
      <add endpointName="realDestination" />
      <add endpointName="backupDestination" />
    </backupList>
  </backupLists>
</routing>
```

```csharp
//create the endpoint list that contains the service endpoints we want to route to
List<ServiceEndpoint> backupList = new List<ServiceEndpoint>();
//add the endpoints in the order that the Routing Service should contact them
//first add the endpoint that we know is down
//clearly, normally you wouldn't know that this endpoint was down by default
backupList.Add(fakeDestination);
//then add the real Destination endpoint
//the Routing Service attempts to send to this endpoint only if it
//encounters a TimeOutException or CommunicationException when sending
//to the previous endpoint in the list.
backupList.Add(realDestination);
//add the backupDestination endpoint
//the Routing Service attempts to send to this endpoint only if it
//encounters a TimeOutException or CommunicationsException when sending
//to the previous endpoints in the list
backupList.Add(backupDestination);
//create the default RoutingConfiguration option
RoutingConfiguration rc = new RoutingConfiguration();
//add a MatchAll filter to the Routing Configuration's filter table
//map it to the list of endpoints defined above
//when a message matches this filter, it is sent to the endpoints in the list in order
//if an endpoint is down or does not respond (which the first endpoint won't
//since the client does not exist), the Routing Service automatically moves the message
//to the next endpoint in the list and try again.
rc.FilterTable.Add(new MatchAllMessageFilter(), backupList);
```

### <a name="supported-error-patterns"></a>Modelli di errore supportati

Nella tabella seguente vengono descritti i modelli compatibili con l'uso di elenchi di endpoint di backup, insieme a note che descrivono dettagli specifici di gestione degli errori.

|Criterio|Sessione|Transazione|Contesto di ricezione|Elenco di backup supportato|Note|
|-------------|-------------|-----------------|---------------------|---------------------------|-----------|
|Unidirezionale||||Sì|Tenta di inviare di nuovo il messaggio a un endpoint di backup. Se per il messaggio viene usata la trasmissione multicast, solo il messaggio nel canale con errori viene spostato alla relativa destinazione di backup.|
|Unidirezionale||✔️||No|Viene generata un'eccezione e viene eseguito il rollback della transazione.|
|Unidirezionale|||✔️|Sì|Tenta di inviare di nuovo il messaggio a un endpoint di backup. Dopo che il messaggio viene ricevuto correttamente, completare tutti i contesti di ricezione. Se il messaggio non viene ricevuto correttamente da uno o più endpoint, non completare il contesto di ricezione.<br /><br /> Se per il messaggio viene usata la trasmissione multicast, il contesto di ricezione viene completato solo se il messaggio viene ricevuto correttamente da almeno un endpoint (primario o di backup). Se nessuno degli endpoint in uno o più percorsi multicast riceve correttamente il messaggio, non completare il contesto di ricezione.|
|Unidirezionale||✔️|✔️|Sì|Interrompere la transazione precedente, creare una nuova transazione e inviare nuovamente tutti i messaggi. I messaggi per i quali si verifica un errore vengono trasmessi a una destinazione di backup.<br /><br /> Dopo che è stata creata una transazione in cui tutte le trasmissioni hanno esito positivo, completare i contesti di ricezione ed eseguire il commit della transazione.|
|Unidirezionale|✔️|||Sì|Tenta di inviare di nuovo il messaggio a un endpoint di backup. In un scenario multicast vengono inviati di nuovo a destinazioni di backup solo i messaggi in una sessione nella quale si è verificato un errore o in una sessione la cui chiusura ha avuto esito negativo.|
|Unidirezionale|✔️|✔️||No|Viene generata un'eccezione e viene eseguito il rollback della transazione.|
|Unidirezionale|✔️||✔️|Sì|Tenta di inviare di nuovo il messaggio a un endpoint di backup. Dopo che tutte le operazioni di invio dei messaggi vengono completate senza errori, la sessione indica che non sono presenti altri messaggi e il servizio di routing chiude correttamente tutti i canali di sessione in uscita, tutti i contesti di ricezione vengono completati e il canale di sessione in ingresso viene chiuso.|
|Unidirezionale|✔️|✔️|✔️|Sì|Interrompere la transazione corrente e crearne una nuova. Inviare di nuovo tutti i messaggi precedenti nella sessione. Dopo che è stata creata una transazione in cui tutti i messaggi vengono inviati correttamente e la sessione indica che non sono presenti altri messaggi, tutti i canali di sessione in uscita vengono chiusi, i contesti di ricezione vengono tutti completati con la transazione, il canale di sessione in ingresso viene chiuso e viene eseguito il commit della transazione.<br /><br /> Quando per le sessioni viene usata la trasmissione multicast, i messaggi senza errori vengono inviati di nuovo alla stessa destinazione, mentre quelli per i quali si è verificato un errore vengono inviati a destinazioni di backup.|
|Bidirezionale||||Sì|Inviare a una destinazione di backup.  Dopo che un canale restituisce un messaggio di risposta, viene restituita la risposta al client originale.|
|Bidirezionale|✔️|||Sì|Inviare tutti i messaggi nel canale a una destinazione di backup.  Dopo che un canale restituisce un messaggio di risposta, viene restituita la risposta al client originale.|
|Bidirezionale||✔️||No|Viene generata un'eccezione e viene eseguito il rollback della transazione.|
|Bidirezionale|✔️|✔️||No|Viene generata un'eccezione e viene eseguito il rollback della transazione.|
|Duplex||||No|La comunicazione duplex non di sessione non è attualmente supportata.|
|Duplex|✔️|||Sì|Inviare a una destinazione di backup.|

## <a name="hosting"></a>Hosting

Poiché il servizio di routing viene implementato come servizio WCF, deve essere indipendente all'interno di un'applicazione o ospitato da IIS o WAS. È consigliabile che il servizio di routing sia ospitato in IIS, WAS o un'applicazione di servizio Windows per sfruttare le funzionalità di avvio automatico e di gestione del ciclo di vita disponibili in tali ambienti di hosting.

Nell'esempio seguente viene illustrato l'hosting del servizio di routing in un'applicazione.

```csharp
using (ServiceHost serviceHost =
                new ServiceHost(typeof(RoutingService)))
```

Per ospitare il servizio di routing in IIS o WAS, è necessario creare un file del servizio (con estensione svc) oppure usare l'attivazione basata sulla configurazione del servizio. Se si usa un file del servizio, è necessario specificare <xref:System.ServiceModel.Routing.RoutingService> mediante il parametro Service. L'esempio seguente contiene un servizio di esempio che può essere usato per ospitare il servizio di routing con IIS o WAS.

```aspx-csharp
<%@ ServiceHost Language="C#" Debug="true" Service="System.ServiceModel.Routing.RoutingService,
     System.ServiceModel.Routing, version=4.0.0.0, Culture=neutral,
     PublicKeyToken=31bf3856ad364e35" %>
```

## <a name="routing-service-and-impersonation"></a>Servizio di routing e rappresentazione

Il servizio di routing di WCF può essere usato con la rappresentazione sia per l'invio sia per la ricezione di messaggi. Si applicano tutti i consueti vincoli di rappresentazione di Windows. Come per la configurazione delle autorizzazioni dell'account o del servizio per usare la rappresentazione durante la scrittura del servizio, questi stessi passaggi sono necessari per usare la rappresentazione con il servizio di routing. Per ulteriori informazioni, vedere [delega e rappresentazione](delegation-and-impersonation-with-wcf.md).

La rappresentazione con il servizio di routing richiede l'uso della rappresentazione ASP.NET in modalità di compatibilità ASP.NET o l'uso delle credenziali di Windows che sono state configurate per consentire la rappresentazione. Per ulteriori informazioni sulla modalità di compatibilità ASP.NET, vedere [servizi WCF e ASP.NET](wcf-services-and-aspnet.md).

> [!WARNING]
> Il servizio di routing di WCF non supporta la rappresentazione con l'autenticazione di base.

Per usare la rappresentazione ASP.NET con il servizio di routing, abilitare la modalità di compatibilità ASP.NET nell'ambiente host del servizio. Il servizio di routing è già stato contrassegnato come servizio che consente la modalità di compatibilità ASP.NET e la rappresentazione verrà abilitata automaticamente. La rappresentazione è l'unico utilizzo supportato dell'integrazione ASP.NET con il servizio di routing.

Per usare la rappresentazione di credenziali di Windows con il servizio di routing è necessario configurare sia le credenziali sia il servizio. L'oggetto delle credenziali client (<xref:System.ServiceModel.Security.WindowsClientCredential>, accessibile da <xref:System.ServiceModel.ChannelFactory>) definisce una proprietà <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> che deve essere impostata per consentire la rappresentazione. Infine, nel servizio è necessario configurare il comportamento di <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> per impostare `ImpersonateCallerForAllOperations` su `true`. Il servizio di routing usa questo flag per decidere se creare i client per inoltrare i messaggi con la rappresentazione abilitata.

## <a name="see-also"></a>Vedere anche

- [Filtri per messaggi](message-filters.md)
- [Contratti di routing](routing-contracts.md)
- [Scelta di un filtro](choosing-a-filter.md)

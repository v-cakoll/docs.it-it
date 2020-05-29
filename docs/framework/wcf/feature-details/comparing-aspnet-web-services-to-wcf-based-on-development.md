---
title: Confronto tra servizi Web ASP.NET e WCF basato sullo sviluppo
ms.date: 03/30/2017
ms.assetid: f362d00e-ce82-484f-9d4f-27e579d5c320
ms.openlocfilehash: c5a2145a6d7b631a666df94eb0c1fc53cbc3c55f
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202270"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-development"></a>Confronto tra servizi Web ASP.NET e WCF basato sullo sviluppo

Windows Communication Foundation (WCF) dispone di un'opzione della modalità di compatibilità ASP.NET per consentire la programmazione e la configurazione delle applicazioni WCF come servizi Web ASP.NET e simulare il comportamento. Nelle sezioni seguenti vengono confrontati i servizi Web di ASP.NET e WCF in base a ciò che è necessario per sviluppare applicazioni con entrambe le tecnologie.

## <a name="data-representation"></a>Rappresentazione dei dati

Lo sviluppo di un servizio Web con ASP.NET inizia in genere con la definizione di qualsiasi tipo di dati complesso che il servizio deve usare. ASP.NET si basa sulla classe <xref:System.Xml.Serialization.XmlSerializer> per tradurre dati rappresentati da tipi .NET Framework in dati XML per la trasmissione a o da un servizio, nonché per tradurre dati ricevuti come XML in oggetti .NET Framework. La definizione dei tipi di dati complessi che un servizio ASP.NET deve usare richiede la definizione di classi .NET Framework che la classe <xref:System.Xml.Serialization.XmlSerializer> può serializzare in e da XML. Tali classi possono essere scritte manualmente o generate da definizioni dei tipi in XML Schema usando l'utilità della riga di comando XML Schemas/Data Types Support Utility, xsd.exe.

Di seguito sono elencati i principali aspetti da considerare nella definizione di classi .NET Framework che la classe <xref:System.Xml.Serialization.XmlSerializer> può serializzare in XML e da XML:

- Soltanto i campi e le proprietà pubbliche di oggetti .NET Framework vengono tradotti in XML.

- Le istanze di classi di raccolte possono essere serializzate in XML soltanto se le classi implementano l'interfaccia <xref:System.Collections.IEnumerable> o <xref:System.Collections.ICollection>.

- Le classi che implementano l'interfaccia <xref:System.Collections.IDictionary>, ad esempio <xref:System.Collections.Hashtable>, non possono essere serializzate in XML.

- I numerosi tipi di attributo nello spazio dei nomi <xref:System.Xml.Serialization> possono essere aggiunti a una classe .NET Framework e ai relativi membri per controllare in che modo le istanze della classe vengono rappresentate in XML.

Lo sviluppo di applicazioni WCF inizia in genere anche con la definizione di tipi complessi. È possibile eseguire WCF per utilizzare gli stessi tipi di .NET Framework dei servizi Web ASP.NET.

WCF <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> possono essere aggiunti ai tipi di .NET Framework per indicare che le istanze del tipo devono essere serializzate in XML e quali particolari campi o proprietà del tipo devono essere serializzati, come illustrato nel codice di esempio seguente.

```csharp
//Example One:
[DataContract]
public class LineItem
{
    [DataMember]
    public string ItemNumber;
    [DataMember]
    public decimal Quantity;
    [DataMember]
    public decimal UnitPrice;
}

//Example Two:
public class LineItem
{
    [DataMember]
    private string itemNumber;
    [DataMember]
    private decimal quantity;
    [DataMember]
    private decimal unitPrice;

    public string ItemNumber
    {
      get
      {
          return this.itemNumber;
      }

      set
      {
          this.itemNumber = value;
      }
    }

    public decimal Quantity
    {
        get
        {
            return this.quantity;
        }

        set
        {
            this.quantity = value;
        }
    }

    public decimal UnitPrice
    {
      get
      {
          return this.unitPrice;
      }

      set
      {
          this.unitPrice = value;
      }
    }
}

//Example Three:
public class LineItem
{
     private string itemNumber;
     private decimal quantity;
     private decimal unitPrice;

     [DataMember]
     public string ItemNumber
     {
       get
       {
          return this.itemNumber;
       }

       set
       {
           this.itemNumber = value;
       }
     }

     [DataMember]
     public decimal Quantity
     {
          get
          {
              return this.quantity;
          }

          set
          {
             this.quantity = value;
          }
     }

     [DataMember]
     public decimal UnitPrice
     {
          get
          {
              return this.unitPrice;
          }

          set
          {
              this.unitPrice = value;
          }
     }
}
```

<xref:System.Runtime.Serialization.DataContractAttribute> significa che nessuno dei campi o proprietà di un tipo o altri campi o proprietà di un tipo devono essere serializzati, mentre <xref:System.Runtime.Serialization.DataMemberAttribute> indica che un deve essere serializzato un particolare campo o proprietà. L'attributo <xref:System.Runtime.Serialization.DataContractAttribute> può essere applicato a una classe o a una struttura. L'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> può essere applicato a un campo o a una proprietà e i campi e le proprietà alle quali viene applicato l'attributo possono essere pubbliche o private. Le istanze di tipi a cui è <xref:System.Runtime.Serialization.DataContractAttribute> applicato il sono definite contratti dati in WCF. Vengono serializzate in XML usando <xref:System.Runtime.Serialization.DataContractSerializer>.

Nell'elenco seguente sono descritte le principali differenze tra l'uso di <xref:System.Runtime.Serialization.DataContractSerializer> e l'uso di <xref:System.Xml.Serialization.XmlSerializer> e dei vari attributi dello spazio dei nomi <xref:System.Xml.Serialization>.

- La classe <xref:System.Xml.Serialization.XmlSerializer> e gli attributi dello spazio dei nomi <xref:System.Xml.Serialization> consentono di eseguire il mapping di tipi .NET Framework a qualsiasi tipo valido definito nell'XML Schema e forniscono pertanto un controllo preciso della modalità di rappresentazione di un tipo in XML. Gli attributi <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> forniscono invece un controllo limitato sulla modalità di rappresentazione di un tipo in XML. È possibile specificare soltanto gli spazi dei nomi e i nomi usati per rappresentare il tipo e i relativi campi o proprietà in XML e la sequenza nella quale i campi e le proprietà vengono visualizzate in XML:

  ```csharp
  [DataContract(
  Namespace="urn:Contoso:2006:January:29",
  Name="LineItem")]
  public class LineItem
  {
        [DataMember(Name="ItemNumber",IsRequired=true,Order=0)]
        public string itemNumber;
        [DataMember(Name="Quantity",IsRequired=false,Order = 1)]
        public decimal quantity;
        [DataMember(Name="Price",IsRequired=false,Order = 2)]
        public decimal unitPrice;
  }
  ```

  Qualsiasi altro elemento relativo alla struttura dell'XML Schema usato per rappresentare il tipo .NET è determinata da <xref:System.Runtime.Serialization.DataContractSerializer>.

- Non consentendo un controllo esteso sulla modalità di rappresentazione di un tipo in XML, il processo di serializzazione diventa estremamente prevedibile per <xref:System.Runtime.Serialization.DataContractSerializer>e quindi più facile da ottimizzare. Un vantaggio pratico della struttura della classe <xref:System.Runtime.Serialization.DataContractSerializer> sono prestazioni più avanzate, approssimativamente del dieci percento.

- Gli attributi da usare con la classe <xref:System.Xml.Serialization.XmlSerializer> non indicano quali campi o proprietà del tipo vengono serializzati in XML, mentre l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> da usare con la classe <xref:System.Runtime.Serialization.DataContractSerializer> mostra esplicitamente quali campi o proprietà vengono serializzati. I contratti dati sono quindi contratti espliciti sulla struttura dei dati che un'applicazione deve inviare e ricevere.

- La classe <xref:System.Xml.Serialization.XmlSerializer> può tradurre soltanto i membri pubblici di un oggetto .NET in XML, mentre la classe <xref:System.Runtime.Serialization.DataContractSerializer> può tradurre i membri di oggetti in XML indipendentemente dai modificatori di accesso di tali membri.

- Poiché è in grado di serializzare membri non pubblici di tipi in XML, la classe <xref:System.Runtime.Serialization.DataContractSerializer> ha meno restrizioni sulla varietà dei tipi .NET che può serializzare in XML. In particolare, questa classe può tradurre in XML tipi quali <xref:System.Collections.Hashtable> che implementano l'interfaccia <xref:System.Collections.IDictionary>. Con maggiore probabilità la classe <xref:System.Runtime.Serialization.DataContractSerializer> è in grado di serializzare in XML le istanze di qualsiasi tipo .NET preesistente senza dover modificare la definizione del tipo o sviluppare un wrapper specifico.

- Un'altra conseguenza della capacità della classe <xref:System.Runtime.Serialization.DataContractSerializer> di accedere ai membri non pubblici di un tipo è che richiede attendibilità totale, diversamente dalla classe <xref:System.Xml.Serialization.XmlSerializer>. L'autorizzazione di accesso al codice con attendibilità totale fornisce l'accesso completo a tutte le risorse in un computer a cui è possibile accedere utilizzando le credenziali utilizzate per l'esecuzione del codice. Questa opzione deve essere usata con cautela perché il codice completamente attendibile accede a tutte le risorse nel computer.

- La classe <xref:System.Runtime.Serialization.DataContractSerializer> include alcune funzionalità di supporto per il controllo delle versioni:

  - <xref:System.Runtime.Serialization.DataMemberAttribute> ha una proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> alla quale può essere assegnato un valore false per i membri che vengono aggiunti a nuove versioni di un contratto dati che non erano presenti nelle versioni precedenti, consentendo così alle applicazioni con le nuove versioni del contratto di essere in grado di elaborare versioni precedenti.

  - Se per un contratto dati viene implementata l'interfaccia <xref:System.Runtime.Serialization.IExtensibleDataObject>, è possibile consentire alla classe <xref:System.Runtime.Serialization.DataContractSerializer> di passare membri definiti in versioni più recenti di un contratto dati mediante applicazioni con versioni precedenti del contratto.

Nonostante tutte le differenze, il codice XML in cui la classe <xref:System.Xml.Serialization.XmlSerializer> serializza un tipo per impostazione predefinita è semanticamente identico al codice XML in cui la classe <xref:System.Runtime.Serialization.DataContractSerializer> serializza un tipo, a condizione che lo spazio dei nomi per il codice XML sia definito esplicitamente. La classe seguente, che include attributi da utilizzare con entrambi i serializzatori, viene convertita in XML semanticamente identico da <xref:System.Xml.Serialization.XmlSerializer> e da <xref:System.Runtime.Serialization.DataContractAttribute> :

```csharp
[Serializable]
[XmlRoot(Namespace="urn:Contoso:2006:January:29")]
[DataContract(Namespace="urn:Contoso:2006:January:29")]
public class LineItem
{
     [DataMember]
     public string ItemNumber;
     [DataMember]
     public decimal Quantity;
     [DataMember]
     public decimal UnitPrice;
}
```

Windows Software Development Kit (SDK) include uno strumento da riga di comando denominato [ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Analogamente allo strumento XSD. exe utilizzato con i servizi Web di ASP.NET, Svcutil. exe può generare definizioni di tipi di dati .NET da XML Schema. I tipi sono contratti dati se la classe <xref:System.Runtime.Serialization.DataContractSerializer> può generare codice XML nel formato definito dall'XML Schema. In caso contrario, sono destinati alla serializzazione mediante l'uso della classe <xref:System.Xml.Serialization.XmlSerializer>. Svcutil. exe può inoltre generare un XML Schema dai contratti dati utilizzando il relativo `dataContractOnly` comcambio.

> [!NOTE]
> Sebbene i servizi Web di ASP.NET usino il <xref:System.Xml.Serialization.XmlSerializer> e la modalità di compatibilità wcf ASP.NET fa in modo che i servizi WCF rispecchino il comportamento dei servizi web ASP.NET, l'opzione di compatibilità ASP.NET non ne limita l'utilizzo <xref:System.Xml.Serialization.XmlSerializer> . È comunque possibile usare la classe <xref:System.Runtime.Serialization.DataContractSerializer> con servizi che sono in esecuzione nella modalità di compatibilità ASP.NET.

## <a name="service-development"></a>Sviluppo del servizio

Per sviluppare un servizio usando ASP.NET veniva in genere aggiunto l'attributo <xref:System.Web.Services.WebService> a una classe e l'attributo <xref:System.Web.Services.WebMethodAttribute> a uno dei metodi di tale classe che devono essere operazioni del servizio:

```csharp
[WebService]
public class Service : T:System.Web.Services.WebService
{
    [WebMethod]
    public string Echo(string input)
    {
       return input;
    }
}
```

ASP.NET 2.0 ha introdotto l'opzione di aggiunta dell'attributo <xref:System.Web.Services.WebService> e di <xref:System.Web.Services.WebMethodAttribute> a un'interfaccia piuttosto che a una classe e di scrittura di una classe per implementare l'interfaccia:

```csharp
[WebService]
public interface IEcho
{
    [WebMethod]
    string Echo(string input);
}

public class Service : IEcho
{

   public string Echo(string input)
   {
        return input;
    }
}
```

È preferibile usare questa opzione in quanto l'interfaccia avente l'attributo <xref:System.Web.Services.WebService> costituisce un contratto per le operazioni eseguite dal servizio che può essere riutilizzato con varie classi in grado di implementare lo stesso contratto in modi diversi.

Un servizio WCF viene fornito definendo uno o più endpoint WCF. Un endpoint è definito da un indirizzo, un'associazione e un contratto di servizio. L'indirizzo definisce l'ubicazione del servizio. L'associazione specifica come comunicare con il servizio. Il contratto di servizio definisce le operazioni che il servizio può eseguire.

Il contratto di servizio viene in genere definito per primo, aggiungendo <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.OperationContractAttribute> a un'interfaccia:

```csharp
[ServiceContract]
public interface IEcho
{
     [OperationContract]
     string Echo(string input);
}
```

<xref:System.ServiceModel.ServiceContractAttribute>Specifica che l'interfaccia definisce un contratto di servizio WCF e <xref:System.ServiceModel.OperationContractAttribute> indica quale, se presente, i metodi dell'interfaccia definiscono le operazioni del contratto di servizio.

Una volta che è stato definito, il contratto di servizio viene implementato in una classe, facendo in modo che la classe implementi l'interfaccia mediante la quale viene definito il contratto di servizio:

```csharp
public class Service : IEcho
{
    public string Echo(string input)
    {
       return input;
    }
}
```

Una classe che implementa un contratto di servizio viene definita tipo di servizio in WCF.

Il passaggio successivo consiste nell'associare un indirizzo e un'associazione a un tipo di servizio. Questa operazione viene in genere eseguita in un file di configurazione, modificando direttamente il file o usando un editor di configurazione fornito con WCF. Di seguito è riportato un esempio di file di configurazione.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
     <system.serviceModel>
      <services>
      <service name="Service ">
       <endpoint
        address="EchoService"
        binding="basicHttpBinding"
        contract="IEchoService "/>
      </service>
      </services>
     </system.serviceModel>
</configuration>
```

L'associazione specifica il set di protocolli per la comunicazione con l'applicazione. Nella tabella seguente sono elencate le associazioni fornite dal sistema che rappresentano opzioni comuni.

|Nome|Scopo|
|----------|-------------|
|BasicHttpBinding|Interoperabilità con servizi Web e client che supportano WS-BasicProfile 1.1 e Basic Security Profile 1.0.|
|WSHttpBinding|Interoperabilità con servizi Web e client che supportano protocolli WS-* su HTTP.|
|WSDualHttpBinding|Comunicazione HTTP duplex in base alla quale il ricevitore di un messaggio iniziale non risponde direttamente al mittente iniziale, ma può trasmettere un numero qualsiasi di risposte in un determinato periodo di tempo usando HTTP in conformità ai protocolli WS-*.|
|WSFederationBinding|Comunicazione HTTP nella quale l'accesso alle risorse di un servizio può essere controllato in base a credenziali rilasciate da un provider di credenziali identificato in modo esplicito.|
|NetTcpBinding|Comunicazione sicura, affidabile e a elevate prestazioni tra entità software WCF in una rete.|
|NetNamedPipeBinding|Comunicazione sicura, affidabile e a elevate prestazioni tra entità software WCF nello stesso computer.|
|NetMsmqBinding|Comunicazione tra entità software WCF tramite MSMQ.|
|MsmqIntegrationBinding|Comunicazione tra un'entità software WCF e un'altra entità software tramite MSMQ.|
|NetPeerTcpBinding|Comunicazione tra entità software WCF mediante la rete peer-to-peer di Windows.|

L'associazione fornita dal sistema, <xref:System.ServiceModel.BasicHttpBinding>, incorpora il set di protocolli supportato dai servizi Web ASP.NET.

Le associazioni personalizzate per le applicazioni WCF sono facilmente definite come raccolte delle classi di elementi di associazione utilizzate da WCF per implementare i singoli protocolli. Nuovi elementi di associazione possono essere scritti per rappresentare protocolli aggiuntivi.

Il comportamento interno dei tipi di servizio può essere regolato usando le proprietà di una famiglia di classi denominate comportamenti. In questo caso la classe <xref:System.ServiceModel.ServiceBehaviorAttribute> viene usata per specificare che il tipo di servizio deve essere multithreading.

```csharp
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple)]
public class DerivativesCalculatorServiceType: IDerivativesCalculator
```

Alcuni comportamenti, come <xref:System.ServiceModel.ServiceBehaviorAttribute>, sono attributi. I comportamenti con proprietà che gli amministratori vorrebbero impostare possono essere modificati nella configurazione di un'applicazione.

Nella programmazione di tipi di servizio viene spesso usata la classe <xref:System.ServiceModel.OperationContext>. La proprietà <xref:System.ServiceModel.OperationContext.Current%2A> statica di questa classe fornisce l'accesso a informazioni sul contesto nel quale viene eseguita un'operazione. L'oggetto <xref:System.ServiceModel.OperationContext> è simile a entrambe le classi <xref:System.Web.HttpContext> e <xref:System.EnterpriseServices.ContextUtil>.

## <a name="hosting"></a>Hosting

I servizi Web ASP.NET vengono compilati in un assembly della libreria di classi. Viene fornito un file denominato file del servizio che ha l'estensione asmx e contiene una direttiva `@ WebService` che identifica la classe che contiene il codice per il servizio e l'assembly in cui si trova.

`<%@ WebService Language="C#" Class="Service,ServiceAssembly" %>`

Il file del servizio viene copiato in una radice dell'applicazione ASP.NET in Internet Information Services (IIS) e l'assembly viene copiato nella sottodirectory \bin di tale radice. Per accedere all'applicazione sarà quindi possibile usare l'URL (Uniform Resource Locator) del file del servizio nella radice dell'applicazione.

I servizi WCF possono essere ospitati immediatamente in IIS 5,1 o 6,0, il servizio di attivazione dei processi di Windows (WAS) fornito come parte di IIS 7,0 e in qualsiasi applicazione .NET. Per ospitare un servizio in IIS 5.1 o 6.0 il servizio deve usare HTTP come protocollo di trasporto delle comunicazioni.

Per ospitare un servizio in IIS 5.1, 6.0 o in WAS, eseguire i passaggi seguenti:

1. Compilare il tipo di servizio in un assembly della libreria di classi.

2. Creare un file del servizio con un'estensione svc con una direttiva `@ ServiceHost` per identificare il tipo di servizio:

    `<%@ServiceHost language="c#" Service="MyService" %>`

3. Copiare il file del servizio in una directory virtuale e l'assembly nella sottodirectory \bin di tale directory.

4. Copiare il file di configurazione nella directory virtuale e denominarlo Web.config.

Per accedere all'applicazione sarà quindi possibile usare l'URL del file del servizio nella radice dell'applicazione.

Per ospitare un servizio WCF all'interno di un'applicazione .NET, compilare il tipo di servizio in un assembly della libreria di classi a cui fa riferimento l'applicazione e programmare l'applicazione in modo che ospiti il servizio usando la <xref:System.ServiceModel.ServiceHost> classe. Di seguito è riportato un esempio della programmazione di base necessaria.

```csharp
string httpBaseAddress = "http://www.contoso.com:8000/";
string tcpBaseAddress = "net.tcp://www.contoso.com:8080/";

Uri httpBaseAddressUri = new Uri(httpBaseAddress);
Uri tcpBaseAddressUri = new Uri(tcpBaseAddress);

Uri[] baseAddresses = new Uri[] {
 httpBaseAddressUri,
 tcpBaseAddressUri};

using(ServiceHost host = new ServiceHost(
typeof(Service), //"Service" is the name of the service type baseAddresses))
{
     host.Open();

     […] //Wait to receive messages
     host.Close();
}
```

Questo esempio mostra in che modo vengono specificati gli indirizzi per uno o più protocolli di trasporto nella costruzione di una classe <xref:System.ServiceModel.ServiceHost>. Questi indirizzi sono detti indirizzi di base.

L'indirizzo fornito per qualsiasi endpoint di un servizio WCF è un indirizzo relativo a un indirizzo di base dell'host dell'endpoint. L'host può avere un indirizzo di base per ogni protocollo di trasporto della comunicazione. Nella configurazione di esempio nel file di configurazione precedente, il costruttore <xref:System.ServiceModel.BasicHttpBinding> selezionato per l'endpoint usa HTTP come protocollo di trasporto. L'indirizzo dell'endpoint, `EchoService` è quindi relativo all'indirizzo di base HTTP dell'host. Nel caso dell'host nell'esempio precedente, l'indirizzo di base HTTP è `http://www.contoso.com:8000/` . Nel caso di un servizio ospitato in IIS o WAS, l'indirizzo di base è l'URL del file del servizio.

Solo i servizi ospitati in IIS o WAS e che sono configurati solo con HTTP come protocollo di trasporto, possono essere eseguiti per utilizzare l'opzione modalità di compatibilità ASP.NET di WCF. Per attivare questa opzione è necessario eseguire i passaggi seguenti.

1. Il programmatore deve aggiungere l'attributo <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> al tipo di servizio e deve specificare che la modalità di compatibilità ASP.NET è consentita o necessaria.

    ```csharp
    [System.ServiceModel.Activation.AspNetCompatibilityRequirements(
          RequirementsMode=AspNetCompatibilityRequirementsMode.Require)]
    public class DerivativesCalculatorServiceType: IDerivativesCalculator
    ```

2. L'amministratore deve configurare l'applicazione per l'uso della modalità di compatibilità ASP.NET.

    ```xml
    <configuration>
         <system.serviceModel>
          <services>
          […]
          </services>
          <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
        </system.serviceModel>
    </configuration>
    ```

    Le applicazioni WCF possono inoltre essere configurate per l'utilizzo di. asmx come estensione per i file del servizio anziché con estensione svc.

    ```xml
    <system.web>
         <compilation>
          <compilation debug="true">
          <buildProviders>
           <remove extension=".asmx"/>
           <add extension=".asmx"
            type="System.ServiceModel.ServiceBuildProvider,
            System.ServiceModel,
            Version=3.0.0.0,
            Culture=neutral,
            PublicKeyToken=b77a5c561934e089" />
          </buildProviders>
          </compilation>
         </compilation>
    </system.web>
    ```

    Questa opzione consente di evitare di dover modificare i client configurati per l'utilizzo degli URL dei file del servizio ASMX quando si modifica un servizio per l'utilizzo di WCF.

## <a name="client-development"></a>Sviluppo client

I client per i servizi Web ASP.NET vengono generati usando lo strumento da riga di comando WSDL.exe che fornisce come input l'URL del file con estensione asmx. Lo strumento corrispondente fornito da WCF è [ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Genera un modulo di codice con la definizione del contratto di servizio e la definizione di una classe client WCF. Genera anche un file di configurazione con l'indirizzo e l'associazione del servizio.

Per programmare un client per un servizio remoto è in genere consigliabile eseguire la programmazione in base a un modello asincrono. Il codice generato dallo strumento WSDL.exe fornisce sempre per entrambi un modello sincrono e un modello asincrono per impostazione predefinita. Il codice generato dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) può fornire per uno dei due modelli. Per impostazione predefinita viene usato per il modello sincrono. Se lo strumento viene eseguito con l'opzione `/async`, il codice generato viene usato per il modello asincrono.

Non vi è alcuna garanzia che i nomi nelle classi client WCF generate da ASP. Per impostazione predefinita, lo strumento WSDL. exe di NET corrisponde ai nomi nelle classi client WCF generate dallo strumento Svcutil. exe. In particolare, nel codice generato dallo strumento Svcutil.exe ai nomi delle proprietà di classi che devono essere serializzate usando la classe <xref:System.Xml.Serialization.XmlSerializer> viene assegnato, per impostazione predefinita, il suffisso Property. Questo non accade invece nel codice generato dallo strumento WSDL.exe.

## <a name="message-representation"></a>Rappresentazione dei messaggi

Le intestazioni dei messaggi SOAP inviati e ricevuti dai servizi Web ASP.NET possono essere personalizzate. Una classe viene derivata dalla classe <xref:System.Web.Services.Protocols.SoapHeader> per definire la struttura dell'intestazione. La classe <xref:System.Web.Services.Protocols.SoapHeaderAttribute> viene quindi usata per indicare la presenza dell'intestazione.

```csharp
public class SomeProtocol : SoapHeader
{
     public long CurrentValue;
     public long Total;
}

[WebService]
public interface IEcho
{
     SomeProtocol ProtocolHeader
     {
      get;
     set;
     }

     [WebMethod]
     [SoapHeader("ProtocolHeader")]
     string PlaceOrders(PurchaseOrderType order);
}

public class Service: WebService, IEcho
{
     private SomeProtocol protocolHeader;

     public SomeProtocol ProtocolHeader
     {
         get
         {
              return this.protocolHeader;
         }

         set
         {
              this.protocolHeader = value;
         }
     }

     string PlaceOrders(PurchaseOrderType order)
     {
         long currentValue = this.protocolHeader.CurrentValue;
     }
}
```

WCF fornisce gli attributi,, <xref:System.ServiceModel.MessageContractAttribute> <xref:System.ServiceModel.MessageHeaderAttribute> e <xref:System.ServiceModel.MessageBodyMemberAttribute> per descrivere la struttura dei messaggi SOAP inviati e ricevuti da un servizio.

```csharp
[DataContract]
public class SomeProtocol
{
     [DataMember]
     public long CurrentValue;
     [DataMember]
     public long Total;
}

[DataContract]
public class Item
{
     [DataMember]
     public string ItemNumber;
     [DataMember]
     public decimal Quantity;
     [DataMember]
     public decimal UnitPrice;
}

[MessageContract]
public class ItemMessage
{
     [MessageHeader]
     public SomeProtocol ProtocolHeader;
     [MessageBody]
     public Item Content;
}

[ServiceContract]
public interface IItemService
{
     [OperationContract]
     public void DeliverItem(ItemMessage itemMessage);
}
```

Questa sintassi genera una rappresentazione esplicita della struttura dei messaggi, mentre la struttura dei messaggi è implicita nel codice di un servizio Web ASP.NET. Inoltre, nella sintassi ASP.NET le intestazioni dei messaggi sono rappresentate come proprietà del servizio, ad esempio la `ProtocolHeader` proprietà nell'esempio precedente, mentre nella sintassi WCF sono rappresentate più accuratamente come proprietà dei messaggi. Inoltre, WCF consente di aggiungere intestazioni di messaggio alla configurazione degli endpoint.

```xml
<service name="Service ">
     <endpoint
      address="EchoService"
      binding="basicHttpBinding"
      contract="IEchoService ">
      <headers>
      <dsig:X509Certificate
       xmlns:dsig="http://www.w3.org/2000/09/xmldsig#">
       ...
      </dsig:X509Certificate>
      </headers>
     </endpoint>
</service>
```

Questa opzione consente di evitare qualsiasi riferimento a intestazioni di protocollo infrastrutturali nel codice per un client o un servizio: le intestazioni vengono aggiunte ai messaggi a seconda della modalità di configurazione dell'endpoint.

## <a name="service-description"></a>Descrizione del servizio

La pubblicazione di una richiesta HTTP GET per il file asmx di un servizio Web ASP.NET con la query WSDL determina in ASP.NET la generazione del file WSDL per descrivere il servizio. Il file WSDL viene restituito da ASP.NET come risposta alla richiesta.

ASP.NET 2.0 consente di verificare che un servizio sia conforme alla specifica Basic Profile 1.1 di WS-I (Web Services-Interoperability Organization ) e di inserire un'attestazione di conformità del servizio nel relativo file WSDL. Questa verifica viene effettuata usando i parametri `ConformsTo` e `EmitConformanceClaims` dell'attributo <xref:System.Web.Services.WebServiceBindingAttribute>.

```csharp
[WebService(Namespace = "http://tempuri.org/")]
[WebServiceBinding(
     ConformsTo = WsiProfiles.BasicProfile1_1,
     EmitConformanceClaims=true)]
public interface IEcho
```

Il WSDL generato da ASP.NET per un servizio può essere personalizzato. Le personalizzazioni vengono effettuate creando una classe derivata di <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension> per aggiungere elementi al WSDL.

L'invio di una richiesta HTTP GET con la query WSDL per il file con estensione svc di un servizio WCF con un endpoint HTTP ospitato in IIS 51, 6,0 o WAS fa sì che WCF risponda con WSDL per descrivere il servizio. L'invio di una richiesta GET HTTP con la query WSDL all'indirizzo di base HTTP di un servizio ospitato in un'applicazione .NET produce lo stesso effetto di quando httpGetEnabled è impostato su True.

Tuttavia, WCF risponde anche alle richieste WS-MetadataExchange con WSDL generato per descrivere un servizio. I servizi Web ASP.NET non dispongono di supporto incorporato per le richieste WS-MetadataExchange.

Il WSDL generato da WCF può essere ampiamente personalizzato. La classe <xref:System.ServiceModel.Description.ServiceMetadataBehavior> fornisce alcune funzioni per la personalizzazione di WSDL. WCF può anche essere configurato in modo da non generare WSDL, bensì usare un file WSDL statico in un URL specificato.

```xml
<behaviors>
     <behavior name="DescriptionBehavior">
     <metadataPublishing
      enableMetadataExchange="true"
      enableGetWsdl="true"
      enableHelpPage="true"
      metadataLocation=
      "http://localhost/DerivativesCalculatorService/Service.WSDL"/>
     </behavior>
</behaviors>
```

## <a name="exception-handling"></a>Gestione delle eccezioni

Nei servizi Web ASP.NET le eccezioni non gestite vengono restituite ai client come errori SOAP. È anche possibile generare esplicitamente istanze della classe <xref:System.Web.Services.Protocols.SoapException> e disporre di maggiore controllo sul contenuto dell'errore SOAP che viene trasmesso al client.

Nei servizi WCF, le eccezioni non gestite non vengono restituite ai client come errori SOAP per impedire che le informazioni riservate vengano inavvertitamente esposte tramite le eccezioni. Viene fornita un'impostazione di configurazione per fare in modo che le eccezioni non gestite vengano restituite ai client a scopo di debug.

Per restituire gli errori SOAP ai client è possibile generare istanze del tipo generico, <xref:System.ServiceModel.FaultException%601>, usando il tipo di contratto dati come tipo generico. È anche possibile aggiungere attributi <xref:System.ServiceModel.FaultContractAttribute> alle operazioni per specificare gli errori che un'operazione potrebbe generare.

```csharp
[DataContract]
public class MathFault
{
     [DataMember]
     public string operation;
     [DataMember]
     public string problemType;
}

[ServiceContract]
public interface ICalculator
{
     [OperationContract]
     [FaultContract(typeof(MathFault))]
     int Divide(int n1, int n2);
}
```

In questo modo i potenziali errori vengono annunciati nel WSDL per il servizio, consentendo ai programmatori dei client di prevedere quali errori potrebbero risultare da un'operazione e di scrivere le istruzioni Catch appropriate.

```csharp
try
{
     result = client.Divide(value1, value2);
}
catch (FaultException<MathFault> e)
{
 Console.WriteLine("FaultException<MathFault>: Math fault while doing "
  + e.Detail.operation
  + ". Problem: "
  + e.Detail.problemType);
}
```

## <a name="state-management"></a>Gestione dello stato

La classe usata per implementare un servizio Web ASP.NET può essere derivata da <xref:System.Web.Services.WebService>.

```csharp
public class Service : WebService, IEcho
{

 public string Echo(string input)
 {
  return input;
 }
}
```

In tal caso, la classe può essere programmata per usare la proprietà Context della classe di base <xref:System.Web.Services.WebService> per accedere a un oggetto <xref:System.Web.HttpContext>. L'oggetto <xref:System.Web.HttpContext> può essere usato per aggiornare e recuperare informazioni sullo stato dell'applicazione usando la relativa proprietà Application, nonché per aggiornare e recuperare informazioni sullo stato della sessione usando la relativa proprietà Session.

ASP.NET fornisce un livello di controllo elevato sulla posizione in cui vengono effettivamente memorizzate le informazioni sullo stato della sessione alla quali è possibile accedere usando la proprietà Session dell'oggetto <xref:System.Web.HttpContext>. Possono essere memorizzate in cookie, in un database, nella memoria del server corrente o nella memoria di un server specificato. La scelta viene effettuata nel file di configurazione del servizio.

WCF fornisce oggetti estendibili per la gestione dello stato. Gli oggetti estensibili sono oggetti che implementano l'interfaccia <xref:System.ServiceModel.IExtensibleObject%601>. Gli oggetti estendibili più importanti sono <xref:System.ServiceModel.ServiceHostBase> e <xref:System.ServiceModel.InstanceContext>. `ServiceHostBase` consente di mantenere lo stato al quale possono accedere tutte le istanze di tutti i tipi di servizio sullo stesso host, mentre `InstanceContext` consente di mantenere lo stato al quale può accedere qualsiasi codice in esecuzione nella stessa istanza di un tipo di servizio.

Qui, il tipo di servizio, `TradingSystem` , dispone di un oggetto <xref:System.ServiceModel.ServiceBehaviorAttribute> che specifica che tutte le chiamate dalla stessa istanza del client WCF vengono instradate alla stessa istanza del tipo di servizio.

```csharp
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]
public class TradingSystem: ITradingService
```

La classe `DealData` definisce lo stato al quale può accedere qualsiasi codice in esecuzione nella stessa istanza di un tipo di servizio.

```csharp
internal class DealData: IExtension<InstanceContext>
{
 public string DealIdentifier = null;
 public Trade[] Trades = null;
}
```

Nel codice del tipo di servizio che implementa una delle operazioni del contratto di servizio viene aggiunto un oggetto stato `DealData` allo stato dell'istanza corrente del tipo di servizio.

```csharp
string ITradingService.BeginDeal()
{
 string dealIdentifier = Guid.NewGuid().ToString();
 DealData state = new DealData(dealIdentifier);
 OperationContext.Current.InstanceContext.Extensions.Add(state);
 return dealIdentifier;
}
```

Questo oggetto stato può essere successivamente recuperato e modificato dal codice che implementa un'altra delle operazioni del contratto di servizio.

```csharp
void ITradingService.AddTrade(Trade trade)
{
 DealData dealData =  OperationContext.Current.InstanceContext.Extensions.Find<DealData>();
 dealData.AddTrade(trade);
}
```

Mentre ASP.NET fornisce il controllo sulla posizione in cui vengono archiviate le informazioni sullo stato nella <xref:System.Web.HttpContext> classe, WCF, almeno nella versione iniziale, non fornisce alcun controllo sulla posizione in cui vengono archiviati gli oggetti estensibili. Questo costituisce il motivo migliore per la selezione della modalità di compatibilità ASP.NET per un servizio WCF. Se la gestione dello stato configurabile è imperativa, la scelta della modalità di compatibilità ASP.NET consente di usare le funzioni della classe <xref:System.Web.HttpContext> esattamente nel modo in cui vengono usate in ASP.NET, nonché di configurare la posizione in cui vengono memorizzate le informazioni sullo stato gestite mediante la classe <xref:System.Web.HttpContext>.

## <a name="security"></a>Sicurezza

Le opzioni per la protezione dei servizi Web ASP.NET sono le stesse usate per la protezione di qualsiasi applicazione IIS. Poiché le applicazioni WCF possono essere ospitate non solo in IIS ma anche in qualsiasi eseguibile .NET, le opzioni per la protezione delle applicazioni WCF devono essere rese indipendenti dalle funzionalità di IIS. Tuttavia, le funzionalità fornite per i servizi Web ASP.NET sono disponibili anche per i servizi WCF in esecuzione in modalità di compatibilità ASP.NET.

### <a name="security-authentication"></a>Protezione: autenticazione

IIS fornisce funzionalità per il controllo di accesso alle applicazioni tra le quali è possibile selezionare l'accesso anonimo o varie modalità di autenticazione: autenticazione di Windows, autenticazione digest, autenticazione di base e autenticazione .NET Passport. L'opzione Autenticazione di Windows può essere usata per controllare l'accesso ai servizi Web ASP.NET. Tuttavia, quando le applicazioni WCF sono ospitate in IIS, è necessario configurare IIS per consentire l'accesso anonimo all'applicazione, in modo che l'autenticazione possa essere gestita da WCF, che supporta l'autenticazione di Windows tra le varie opzioni. Le altre opzioni incorporate includono token del nome utente, certificati X.509, token SAML e schede CardSpace, ma è comunque possibile definire meccanismi di autenticazione personalizzati.

### <a name="security-impersonation"></a>Protezione: rappresentazione

ASP.NET fornisce un elemento di identità mediante il quale un servizio Web ASP.NET può essere impostato per rappresentare un determinato utente o le credenziali utente che vengono fornite con la richiesta corrente. Tale elemento può essere utilizzato per configurare la rappresentazione nelle applicazioni WCF in esecuzione in modalità di compatibilità ASP.NET.

Il sistema di configurazione WCF fornisce il proprio elemento Identity per la designazione di un utente specifico per la rappresentazione. Inoltre, i client e i servizi WCF possono essere configurati in modo indipendente per la rappresentazione. I client possono essere configurati per rappresentare l'utente corrente quando trasmettono richieste.

```xml
<behaviors>
     <behavior name="DerivativesCalculatorClientBehavior">
      <clientCredentials>
      <windows allowedImpersonationLevel="Impersonation"/>
      </clientCredentials>
     </behavior>
</behaviors>
```

Le operazioni dei servizi possono essere configurate per rappresentare le credenziali utente fornite con la richiesta corrente.

```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]
public void Receive(Message input)
```

### <a name="security-authorization-using-access-control-lists"></a>Protezione: autorizzazione mediante elenchi di controllo di accesso (ACL)

Gli elenchi di controllo di accesso (ACL) possono essere usati per limitare l'accesso ai file con estensione asmx. Tuttavia, gli ACL nei file WCF. svc vengono ignorati tranne che in modalità di compatibilità ASP.NET.

### <a name="security-role-based-authorization"></a>Protezione: autorizzazione basata sui ruoli

L'opzione Autenticazione di Windows di IIS può essere usata insieme all'elemento di autorizzazione fornito dal linguaggio di configurazione di ASP.NET per facilitare l'autorizzazione basata sui ruoli per i servizi Web ASP.NET basati sui gruppi di Windows ai quali sono assegnati gli utenti. ASP.NET 2.0 ha introdotto un meccanismo più generale di autorizzazione basata sui ruoli: i provider di ruoli.

I provider di ruoli sono classi che implementano tutte un'interfaccia di base per ottenere informazioni sui ruoli ai quali è assegnato un utente, ma ogni provider di ruoli sa come recuperare tali informazioni da un'origine diversa. ASP.NET 2.0 fornisce un provider di ruoli in grado di recuperare assegnazioni di ruolo da un database Microsoft SQL Server e un altro provider in grado di recuperare assegnazioni di ruolo da Gestione autorizzazioni di Windows Server 2003.

Il meccanismo del provider di ruoli può essere effettivamente utilizzato indipendentemente da ASP.NET in qualsiasi applicazione .NET, inclusa un'applicazione WCF. La configurazione di esempio seguente per un'applicazione WCF Mostra come l'uso di un provider di ruoli ASP.NET è un'opzione selezionata per mezzo del <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> .

```xml
<system.serviceModel>
     <services>
         <service name="Service.ResourceAccessServiceType"
             behaviorConfiguration="ServiceBehavior">
             <endpoint
              address="ResourceAccessService"
              binding="wsHttpBinding"
              contract="Service.IResourceAccessContract"/>
         </service>
     </services>
     <behaviors>
       <behavior name="ServiceBehavior">
       <serviceAuthorization principalPermissionMode="UseAspNetRoles"/>
      </behavior>
     </behaviors>
</system.serviceModel>
```

### <a name="security-claims-based-authorization"></a>Protezione: autorizzazione basata sulle attestazioni

Una delle innovazioni più importanti di WCF è il supporto completo per l'autorizzazione dell'accesso alle risorse protette in base alle attestazioni. Le attestazioni sono costituite da un tipo, da un diritto e da un valore, ad esempio la licenza di un driver. In questo caso WCF crea un set di attestazioni relative al titolare della licenza, una delle quali è la data di nascita del titolare. Il tipo di questa attestazione è data di nascita, mentre il valore dell'attestazione è la data di nascita del titolare della licenza. Il diritto che un'attestazione conferisce al titolare specifica le operazioni che possono essere eseguite dal titolare con il valore dell'attestazione. Nel caso dell'attestazione della data di nascita del titolare della licenza, il diritto è possesso: il titolare possiede quella data di nascita ma non può, ad esempio, modificarla. L'autorizzazione basata sulle attestazioni include l'autorizzazione basata sui ruoli in quanto i ruoli sono un tipo di attestazione.

L'autorizzazione basata sulle attestazioni viene eseguita confrontando un set di attestazioni ai requisiti di accesso dell'operazione e, a seconda del risultato di tale confronto, concedendo o negando l'accesso all'operazione. In WCF è possibile specificare una classe da utilizzare per eseguire l'autorizzazione basata sulle attestazioni, ancora una volta assegnando un valore alla `ServiceAuthorizationManager` proprietà di <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> .

```xml
<behaviors>
     <behavior name='ServiceBehavior'>
     <serviceAuthorization
     serviceAuthorizationManagerType=
                   'Service.AccessChecker, Service' />
     </behavior>
</behaviors>
```

Le classi usate per eseguire l'autorizzazione basata sulle attestazioni devono derivare da <xref:System.ServiceModel.ServiceAuthorizationManager>, che deve eseguire l'override di un solo metodo, `AccessCheck()`. WCF chiama tale metodo ogni volta che viene richiamata un'operazione del servizio e fornisce un <xref:System.ServiceModel.OperationContext> oggetto che dispone delle attestazioni per l'utente nella relativa `ServiceSecurityContext.AuthorizationContext` Proprietà. WCF esegue le operazioni di assemblaggio delle attestazioni relative all'utente da qualsiasi token di sicurezza fornito dall'utente per l'autenticazione, che lascia l'attività di valutazione del fatto che le attestazioni siano sufficienti per l'operazione in questione.

Che WCF assembla automaticamente le attestazioni da qualsiasi tipo di token di sicurezza rappresenta un'innovazione estremamente significativa, perché rende il codice per l'autorizzazione basata sulle attestazioni completamente indipendenti dal meccanismo di autenticazione. L'autorizzazione mediante ACL e l'autorizzazione basata sui ruoli in ASP.NET sono invece strettamente collegate all'autenticazione di Windows.

### <a name="security-confidentiality"></a>Protezione: riservatezza

La riservatezza dei messaggi scambiati con servizi Web ASP.NET può essere garantita al livello del trasporto configurando l'applicazione in IIS per l'uso del protocollo HTTPS. È possibile eseguire la stessa operazione per le applicazioni WCF ospitate in IIS. Tuttavia, le applicazioni WCF ospitate al di fuori di IIS possono anche essere configurate per l'utilizzo di un protocollo di trasporto sicuro. Più importante, le applicazioni WCF possono anche essere configurate per proteggere i messaggi prima che vengano trasportati, utilizzando il protocollo WS-Security. La protezione del solo corpo del messaggio mediante il protocollo WS-Security consente la trasmissione riservata del messaggio su intermediari prima di raggiungere la destinazione finale.

## <a name="globalization"></a>Globalizzazione

Il linguaggio di configurazione di ASP.NET consente di specificare le impostazioni cultura per i singoli servizi. WCF non supporta questa impostazione di configurazione tranne che in modalità di compatibilità ASP.NET. Per localizzare un servizio WCF che non usa la modalità di compatibilità ASP.NET, compilare il tipo di servizio in assembly specifici delle impostazioni cultura e avere endpoint specifici delle impostazioni cultura per ogni assembly specifico delle impostazioni cultura.

## <a name="see-also"></a>Vedere anche

- [Confronto tra i servizi Web ASP.NET e WCF basato sullo scopo e gli standard usati](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)

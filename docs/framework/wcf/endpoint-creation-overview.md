---
title: Cenni preliminari sulla creazione di endpoint
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], overview
ms.assetid: f4dce0fb-6f54-47e6-8054-86d7f574b91c
ms.openlocfilehash: 0d7baacb9525e0c268ae53b0c3617324ecd0772f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548989"
---
# <a name="endpoint-creation-overview"></a>Cenni preliminari sulla creazione di endpoint
Tutte le comunicazioni con un servizio Windows Communication Foundation (WCF) viene eseguita tramite il *endpoint* del servizio. Gli endpoint forniscono ai client l'accesso alla funzionalità offerta da un servizio WCF. Questa sezione descrive la struttura di un endpoint e viene illustrato come definire un endpoint nella configurazione e nel codice.  
  
## <a name="the-structure-of-an-endpoint"></a>Struttura di un endpoint  
 Ogni endpoint contiene un indirizzo che indica dove individuare l'endpoint, un'associazione che specifica in che modo un client può comunicare con l'endpoint e un contratto che identifica i metodi disponibili.  
  
-   **Indirizzo**. L'indirizzo identifica in modo univoco l'endpoint e comunica ai potenziali utenti l'ubicazione del servizio. È rappresentato nel modello a oggetti WCF dal <xref:System.ServiceModel.EndpointAddress> indirizzo, che contiene un identificatore URI (Uniform Resource) e le proprietà di indirizzo che includono un'identità, alcuni elementi di servizi Web (WSDL, Web Services Description Language) e una raccolta di facoltativo intestazioni. Le intestazioni facoltative forniscono dettagli aggiuntivi sull'indirizzo per identificare o interagire con l'endpoint. Per altre informazioni, vedere [che specifica un indirizzo Endpoint](../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
-   **Associazione**. L'associazione specifica la modalità di comunicazione con l'endpoint. L'associazione specifica in che modo l'endpoint comunica con il mondo, incluso il protocollo di trasporto da usare (ad esempio, TCP o HTTP), il tipo di codifica da usare per i messaggi (ad esempio, testo o binaria) e i requisiti di sicurezza necessari (ad esempio, Secure Sockets Layer [SSL] o sicurezza dei messaggi SOAP). Per altre informazioni, vedere [utilizzando le associazioni per configurare servizi e client](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).  
  
-   **Contratto di servizio**. Il contratto di servizio delinea la funzionalità che l'endpoint espone al client. Un contratto specifica le operazioni che un client può richiamare, il modulo del messaggio e il tipo di parametri o dati di input necessari per chiamare l'operazione e il tipo di elaborazione o messaggio di risposta che il client può aspettarsi. Tre tipi di contratti di base corrispondono a modelli di scambio dei messaggi (MEP, Message Exchange Pattern) di base: datagramma (unidirezionale), request/reply e duplex (bidirezionale). Il contratto di servizio può inoltre usare contratti dati e contratti di messaggio per richiedere tipi di dati e formati di messaggio specifici al momento dell'accesso. Per altre informazioni su come definire un contratto di servizio, vedere [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md). Per ricevere messaggi dal servizio in un modello di scambio dei messaggi (MEP) duplex, è possibile che un client debba implementare un contratto definito dal servizio, detto contratto di callback. Per altre informazioni, vedere [servizi Duplex](../../../docs/framework/wcf/feature-details/duplex-services.md).  
  
 L'endpoint per un servizio può essere specificato in modo imperativo mediante l'uso di codice oppure in modo dichiarativo mediante la configurazione. Se non è specificato alcun endpoint, il runtime ne fornisce di predefiniti aggiungendone uno per ogni indirizzo di base per ciascun contratto di servizio implementato dal servizio. In genere definire endpoint nel codice non è pratico in quanto le associazioni e gli indirizzi di un servizio distribuito sono solitamente diversi da quelli usati durante lo sviluppo del servizio. In genere è più pratico definire endpoint di servizio mediante la configurazione piuttosto che mediante codice. Se le informazioni sull'associazione e sull'indirizzo non vengono incluse nel codice, tali dati possono essere modificati senza dover compilare e distribuire nuovamente l'applicazione.  
  
> [!NOTE]
>  Quando si aggiunge un endpoint di servizio che esegue la rappresentazione, è necessario usare uno dei metodi <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> o il metodo <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> per caricare correttamente il contratto in un nuovo oggetto <xref:System.ServiceModel.Description.ServiceDescription>.  
  
## <a name="defining-endpoints-in-code"></a>Definizione di endpoint nel codice  
 Nell'esempio riportato di seguito viene illustrato come specificare un endpoint nel codice.  
  
-   Definire un contratto per un `IEcho` tipo di servizio che accetta di un utente nome e l'istruzione echo con la risposta "Hello \<nome >!".  
  
-   Implementare un servizio `Echo` del tipo definito dal contratto `IEcho`.  
  
-   Specificare un indirizzo dell'endpoint di `http://localhost:8000/Echo` per il servizio.  
  
-   Configurare il servizio `Echo` usando un'associazione <xref:System.ServiceModel.WSHttpBinding>.  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   public interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   class Echo : IEcho  
   {  
      public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      public static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Use a predefined WSHttpBinding to configure the service.  
          WSHttpBinding binding = new WSHttpBinding();  
  
          // Add the endpoint for this service to the service host.  
          serviceHost.AddServiceEndpoint(  
             typeof(IEcho),   
             binding,   
             echoUri  
           );  
  
          // Open the service host to run it.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Create a ServiceHost for the Echo service.  
Dim svcHost As ServiceHost = New ServiceHost(GetType(HelloWorld), echoUri)  
  
' Use a predefined WSHttpBinding to configure the service.  
Dim binding As New WSHttpBinding()  
  
' Add the endpoint for this service to the service host.  
serviceHost.AddServiceEndpoint(GetType(IEcho), binding, echoUri)  
  
' Open the service host to run it.  
serviceHost.Open()  
```  
  
> [!NOTE]
>  L'host del servizio viene creato con un indirizzo di base. Il resto dell'indirizzo, relativo all'indirizzo di base, viene quindi specificato come parte di un endpoint. Questo partizionamento dell'indirizzo consente a più endpoint di essere definiti in modo più appropriato per i servizi presenti in un host.  
  
> [!NOTE]
>  Le proprietà di <xref:System.ServiceModel.Description.ServiceDescription> nell'applicazione del servizio non devono essere modificate dopo la chiamata al metodo <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> su <xref:System.ServiceModel.ServiceHostBase>. Se vengono modificati dopo questo punto, alcuni membri, ad esempio la proprietà <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> e i metodi `AddServiceEndpoint` su <xref:System.ServiceModel.ServiceHostBase> e <xref:System.ServiceModel.ServiceHost>, generano un'eccezione. Altri consentono la modifica, ma il risultato è indefinito.  
>   
>  Analogamente, sul client i valori <xref:System.ServiceModel.Description.ServiceEndpoint> non devono essere modificati dopo la chiamata a <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> su <xref:System.ServiceModel.ChannelFactory>. Se viene modificata dopo questo punto, la proprietà <xref:System.ServiceModel.ChannelFactory.Credentials%2A> genera un'eccezione. Gli altri valori della descrizione client possono essere modificati senza errore, ma il risultato è indefinito.  
>   
>  Per il servizio o per il client, è consigliabile modificare la descrizione prima di chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.  
  
## <a name="defining-endpoints-in-configuration"></a>Definizione di endpoint nella configurazione  
 Durante la creazione di un'applicazione è spesso necessario rimettere le decisioni all'amministratore che distribuisce l'applicazione. Spesso non è possibile prevedere, ad esempio, quale sarà l'indirizzo (URI) di un servizio. Anziché inserire un indirizzo nel codice, è preferibile consentire che questa operazione venga eseguita da un amministratore dopo la creazione del servizio. Questa flessibilità viene realizzata attraverso la configurazione. Per informazioni dettagliate, vedere [configurazione dei servizi](../../../docs/framework/wcf/configuring-services.md).  
  
> [!NOTE]
>  Usare il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con il `/config:` *nomefile*`[,`*filename* `]` passare a creare rapidamente file di configurazione.  
  
## <a name="using-default-endpoints"></a>Uso di endpoint predefiniti  
 Se non è specificato alcun endpoint nel codice o nella configurazione, il runtime ne fornisce di predefiniti aggiungendone uno per ogni indirizzo di base per ciascun contratto di servizio implementato dal servizio. L'indirizzo di base può essere specificato nel codice o nella configurazione e gli endpoint predefiniti vengono aggiunti quando viene chiamato <xref:System.ServiceModel.ICommunicationObject.Open> in <xref:System.ServiceModel.ServiceHost>. Questo esempio è identico a quello della sezione precedente, ma poiché non è stato specificato alcun endpoint, vengono aggiunti gli endpoint predefiniti.  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   Interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   Class Echo : IEcho  
   {  
      Public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Open the service host to run it. Default endpoints  
          // are added when the service is opened.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Open the service host to run it. Default endpoints  
' are added when the service is opened.  
serviceHost.Open()  
```  
  
 Se vengono forniti endpoint in modo esplicito, è comunque possibile aggiungere gli endpoint predefiniti chiamando <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> su <xref:System.ServiceModel.ServiceHost> prima di chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>. Per altre informazioni sugli endpoint predefiniti, vedere [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="see-also"></a>Vedere anche
- [Implementazione dei contratti di servizio](../../../docs/framework/wcf/implementing-service-contracts.md)

---
title: 'Procedura: ospitare un flusso di lavoro non di servizio in IIS'
ms.date: 03/30/2017
ms.assetid: f362562c-767d-401b-8257-916616568fd4
ms.openlocfilehash: 70fd6aca94f2addd7ee568e897171ae1da86db67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496756"
---
# <a name="how-to-host-a-non-service-workflow-in-iis"></a>Procedura: ospitare un flusso di lavoro non di servizio in IIS
I flussi di lavoro che non sono servizi flusso di lavoro possono essere ospitati in IIS/WAS. Tale possibilità si rivela utile quando è necessario ospitare un flusso di lavoro scritto da un altro utente, ad esempio se si ospita di nuovo Progettazione flussi di lavoro e si consente agli utenti di creare flussi di lavoro.  L'host di flussi di lavoro non di servizio in IIS fornisce supporto per caratteristiche quali il riciclo dei processi, la chiusura per inattività, il monitoraggio dell'integrità dei processi e l'attivazione basata su messaggi. I servizi flusso di lavoro ospitati in IIS includono le attività <xref:System.ServiceModel.Activities.Receive> e vengono attivati quando un messaggio viene ricevuto da IIS. Nei flussi di lavoro non di servizio non sono contenute attività di messaggistica e, per impostazione predefinita, non possono essere attivati inviando un messaggio.  È necessario derivare una classe dall'oggetto <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> e definire un contratto di servizio contenente le operazioni per creare un'istanza del flusso di lavoro. Questo argomento viene descritta la creazione di un flusso di lavoro semplice, definendo un contratto di servizio, un client può utilizzare per attivare il flusso di lavoro e derivando una classe dal <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> che utilizza il contratto di servizio in ascolto di richieste di creazione del flusso di lavoro.  
  
### <a name="create-a-simple-workflow"></a>Creare un flusso di lavoro semplice  
  
1.  Creare una nuova soluzione [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] vuota chiamata `CreationEndpointTest`.  
  
2.  Aggiungere un nuovo progetto Applicazione di servizi flusso di lavoro WCF denominato `SimpleWorkflow` alla soluzione. Verrà aperta Progettazione flussi di lavoro.  
  
3.  Eliminare le attività ReceiveRequest e SendResponse. Un flusso di lavoro diventa un servizio flusso di lavoro grazie a queste attività. Poiché in questo momento non si intende usare un servizio flusso di lavoro, tali attività non sono più necessarie.  
  
4.  Impostare DisplayName per l'attività sequence su "Flusso di lavoro sequenziale".  
  
5.  Rinominare Service1.xamlx con Workflow1.xamlx.  
  
6.  Fare clic sulla finestra di progettazione all'esterno di attività sequence e impostare le proprietà Name e ConfigurationName su "Workflow1"  
  
7.  Trascinare un'attività <xref:System.Activities.Statements.WriteLine> nell'oggetto <xref:System.Activities.Statements.Sequence>. Il <xref:System.Activities.Statements.WriteLine> attività, vedere il **primitive** sezione della casella degli strumenti. Impostare il <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà del <xref:System.Activities.Statements.WriteLine> attività "Hello, world".  
  
     A questo punto, l'aspetto del flusso di lavoro deve essere simile al diagramma seguente.  
  
     ![Un semplice flusso di lavoro](../../../../docs/framework/wcf/feature-details/media/simpleworkflow.png "SimpleWorkflow")  
  
### <a name="create-the-workflow-creation-service-contract"></a>Creare un contratto di servizio di creazione del flusso di lavoro  
  
1.  Aggiungere un nuovo progetto Libreria di classi denominato `Shared` alla soluzione `CreationEndpointTest`.  
  
2.  Aggiungere un riferimento a System.ServiceModel.dll, System.Configuration e System.ServiceModel.Activities al progetto `Shared`.  
  
3.  Rinominare il file Class1.cs con IWorkflowCreation.cs e il codice seguente in base al file.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
  
    namespace Shared  
    {  
        //service contract exposed from the endpoint  
        [ServiceContract(Name = "IWorkflowCreation")]  
        public interface IWorkflowCreation  
        {  
            [OperationContract(Name = "Create")]  
            Guid Create(IDictionary<string, object> inputs);  
  
            [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
            void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
        }  
    }  
    ```  
  
     Questo contratto consente di definire due operazioni che permettono entrambe di creare una nuova istanza del flusso di lavoro non di servizio appena creato. Una consente di creare una nuova istanza con un ID istanza generato e l'altra di specificare l'ID istanza per la nuova istanza del flusso di lavoro.  Entrambi i metodi consentono di passare parametri alla nuova istanza del flusso di lavoro. Questo contratto verrà esposto dal <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> per consentire ai client di creare nuove istanze del flusso di lavoro non di servizio.  
  
### <a name="derive-a-class-from-workflowhostingendpoint"></a>Derivare una classe da WorkflowHostingEndpoint  
  
1.  Aggiungere una nuova classe denominata `CreationEndpoint` derivato da <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> per il `Shared` progetto.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Globalization;  
    using System.ServiceModel;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Channels;  
  
    namespace Shared  
    {  
        public class CreationEndpoint : WorkflowHostingEndpoint  
        {  
        }  
    }  
    ```  
  
2.  Aggiungere una variabile locale statica <xref:System.Uri> denominata `defaultBaseUri` alla classe `CreationEndpoint`.  
  
    ```  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
    }  
    ```  
  
3.  Aggiungere il costruttore seguente alla classe `CreationEndpoint`. Si noti che il contratto di servizio `IWorkflowCreation` viene specificato nella chiamata al costruttore base.  
  
    ```  
    public CreationEndpoint(Binding binding, EndpointAddress address)  
       : base(typeof(IWorkflowCreation), binding, address)  
       {  
       }  
    ```  
  
4.  Aggiungere il seguente costruttore predefinito alla classe `CreationEndpoint`.  
  
    ```  
    public CreationEndpoint()  
       : this(GetDefaultBinding(),  
       new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative))))  
       {  
       }  
    ```  
  
5.  Aggiungere una proprietà statica `DefaultBaseUri` alla classe `CreationEndpoint`. Questa proprietà sarà usata per includere un URI di base predefinito, se non ne viene fornito uno.  
  
    ```  
    static Uri DefaultBaseUri  
    {  
       get  
       {  
          if (defaultBaseUri == null)  
          {  
             defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                Process.GetCurrentProcess().Id,  
                AppDomain.CurrentDomain.Id));  
          }  
          return defaultBaseUri;  
       }  
     }  
    ```  
  
6.  Creare il metodo seguente per ottenere il binding predefinito da usare per l'endpoint di creazione.  
  
    ```  
    //defaults to NetNamedPipeBinding  
    public static Binding GetDefaultBinding()  
    {  
       return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
    }  
    ```  
  
7.  Eseguire l'override del metodo <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A> per restituire l'ID istanza del flusso di lavoro. Se il `Action` intestazione termina con "Create" restituisce un GUID vuoto, se il `Action` intestazione termina con "createwithinstanceid, viene" restituito il GUID passato al metodo. In caso contrario, viene generata un'eccezione <xref:System.InvalidOperationException>. Queste intestazioni `Action` corrispondono alle due operazioni definite nel contratto di servizio `IWorkflowCreation`.  
  
    ```  
    protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
    {  
       //Create was called by client  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
       {  
          return Guid.Empty;  
       }  
       //CreateWithInstanceId was called by client  
       else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
       {  
          return (Guid)inputs[1];  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
    }  
    ```  
  
8.  Eseguire l'override del metodo <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A> per creare un oggetto <xref:System.ServiceModel.Activities.WorkflowCreationContext>, aggiungere qualsiasi argomento per il flusso di lavoro, inviare l'ID istanza al client e restituire l'oggetto <xref:System.ServiceModel.Activities.WorkflowCreationContext>.  
  
    ```  
    protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
    {  
       WorkflowCreationContext creationContext = new WorkflowCreationContext();  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create") || (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId")))  
       {  
          Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
          if (arguments != null && arguments.Count > 0)  
          {  
             foreach (KeyValuePair<string, object> pair in arguments)  
             {  
                //arguments to pass to the workflow  
                creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
             }  
          }  
          //reply to client with instanceId  
          responseContext.SendResponse(instanceId, null);  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
       return creationContext;  
    }  
    ```  
  
### <a name="create-a-standard-endpoint-element-to-allow-you-to-configure-the-workflowcreationendpoint"></a>Creare un elemento endpoint standard per consentire la configurazione di WorkflowCreationEndpoint  
  
1.  Aggiungere un riferimento a Shared nel progetto `CreationEndpoint`  
  
2.  Aggiungere una nuova classe denominata `CreationEndpointElement`, derivata dall'oggetto <xref:System.ServiceModel.Configuration.StandardEndpointElement> al progetto `CreationEndpoint`. Questa classe rappresenterà un oggetto `CreationEndpoint` in un file web.config.  
  
    ```  
    using System;  
    using System.Configuration;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Configuration;  
    using System.ServiceModel.Description;  
    using Shared;  
  
    namespace CreationEndpointTest  
    {  
        //config element for CreationEndpoint  
        public class CreationEndpointElement : StandardEndpointElement  
        {  
       }  
    ```  
  
3.  Aggiungere una proprietà denominata `EndpointType` per restituire il tipo di endpoint.  
  
    ```  
    protected override Type EndpointType  
    {  
       get { return typeof(CreationEndpoint); }  
    }  
    ```  
  
4.  Eseguire l'override del metodo <xref:System.ServiceModel.Configuration.StandardEndpointElement.CreateServiceEndpoint%2A> e restituire un nuovo oggetto `CreationEndpoint`.  
  
    ```  
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
    {  
       return new CreationEndpoint();  
    }  
    ```  
  
5.  Eseguire l'overload dei metodi <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A> e <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A>. Questi metodi devono solo essere definiti; non è necessario aggiungervi alcun codice.  
  
    ```  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
    ```  
  
6.  Aggiungere la classe di raccolta per `CreationEndpoint` al file CreationEndpointElement.cs nel progetto `CreationEndpoint`. Questa classe viene usata dalla configurazione per mantenere un numero di istanze `CreationEndpoint` in un file web.config.  
  
    ```  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
    ```  
  
7.  Compilare la soluzione.  
  
### <a name="host-the-workflow-in-iis"></a>Ospitare il flusso di lavoro in IIS  
  
1.  Creare una nuova applicazione denominata `MyCreationEndpoint` in IIS.  
  
2.  Copiare il file workflow1.xaml generato da Progettazione flussi di lavoro nella directory dell'applicazione e rinominarlo workflow1.xamlx.  
  
3.  Copiare i file shared.dll e CreationEndpoint.dll nella directory bin dell'applicazione; se non è presente è necessario crearla.  
  
4.  Sostituire il contenuto del file Web.config nel progetto `CreationEndpoint` con il codice seguente.  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.web>  
        <compilation debug="true" targetFramework="4.0" />  
      </system.web>   
    </configuration>  
    ```  
  
5.  Dopo l'elemento `<system.web>`, registrare `CreationEndpoint` aggiungendo il codice di configurazione seguente.  
  
    ```xml  
    <system.serviceModel>  
        <!--register CreationEndpoint-->  
        <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
        <extensions>  
          <endpointExtensions>  
            <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, CreationEndpoint, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </endpointExtensions>  
        </extensions>  
    </system.serviceModel>  
    ```  
  
     Questa operazione consente di registrare la classe `CreationEndpointCollection` affinché sia possibile configurare un oggetto `CreationEndpoint` in un file web.config.  
  
6.  Aggiungere un `<service>` elemento (dopo il \</extensions > tag) con un `CreationEndpoint` che sarà in ascolto dei messaggi in arrivo.  
  
    ```xml  
    <services>  
          <!-- add endpoint to service-->  
          <service name="Workflow1" behaviorConfiguration="basicConfig" >  
            <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
          </service>  
        </services>  
    ```  
  
7.  Aggiungere un \<comportamenti > elemento (dopo il  \< /services > tag) per abilitare i metadati del servizio.  
  
    ```xml  
    <behaviors>  
          <serviceBehaviors>  
            <behavior name="basicConfig">  
              <serviceMetadata httpGetEnabled="true" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
    ```  
  
8.  Copiare il file web.config nella directory dell'applicazione IIS.  
  
9. Test per vedere se l'endpoint di creazione sta funzionando aprendo Internet Explorer e la selezione di http://localhost/MyCreationEndpoint/Workflow1.xamlx. In Internet Explorer deve essere visualizzata la schermata seguente:  
  
     ![Test del servizio](../../../../docs/framework/wcf/feature-details/media/testservice.gif "TestService")  
  
### <a name="create-a-client-that-will-call-the-creationendpoint"></a>Creare un client che consentirà di chiamare CreationEndpoint.  
  
1.  Aggiungere una nuova applicazione console alla soluzione `CreationEndpointTest`.  
  
2.  Aggiungere riferimenti a System.ServiceModel.dll e System.ServiceModel.Activities e il progetto `Shared`.  
  
3.  Nel `Main` metodo crea un <xref:System.ServiceModel.ChannelFactory%601> di tipo `IWorkflowCreation` e chiamare <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>. Questa operazione consentirà la restituzione di un proxy. Successivamente è possibile chiamare `Create` su tale proxy per creare l'istanza del flusso di lavoro ospitata in IIS:  
  
    ```  
    using System.Text;  
    using Shared;  
    using System.ServiceModel;  
  
    namespace CreationEndpointClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                try  
                {  
                    //client using BasicHttpBinding  
                    IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/CreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                    Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                    Console.WriteLine("Press return to exit ...");  
                    Console.ReadLine();  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine(ex);  
                    Console.ReadLine();  
                }  
            }  
        }  
    }  
    ```  
  
4.  Eseguire CreationEndpointClient. L'output dovrebbe essere simile al seguente:  
  
    ```Output  
    Workflow Instance created using CreationEndpoint added in config. Instance Id: 0875dac0-2b8b-473e-b3cc-abcb235e9693Press return to exit ...  
    ```  
  
    > [!NOTE]
    >  L'output del flusso di lavoro non sarà visualizzato poiché è in esecuzione in IIS, il quale non dispone di alcun output di console.  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato il codice completo per questo esempio.  
  
```xaml  
<!-— workflow1.xamlx -->  
<WorkflowService mc:Ignorable="sap"   
                 ConfigurationName="Workflow1"   
                 sap:VirtualizedContainerService.HintSize="263,230"   
                 Name="Workflow1"   
                 mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces"   
                 xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"   
                 xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
                 xmlns:mv="clr-namespace:Microsoft.VisualBasic;assembly=System"   
                 xmlns:mva="clr-namespace:Microsoft.VisualBasic.Activities;assembly=System.Activities"   
                 xmlns:p="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
                 xmlns:s="clr-namespace:System;assembly=mscorlib"   
                 xmlns:s1="clr-namespace:System;assembly=System"   
                 xmlns:s2="clr-namespace:System;assembly=System.Xml"   
                 xmlns:s3="clr-namespace:System;assembly=System.Core"   
                 xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities"   
                 xmlns:sap="http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation"   
                 xmlns:scg="clr-namespace:System.Collections.Generic;assembly=System"   
                 xmlns:scg1="clr-namespace:System.Collections.Generic;assembly=System.ServiceModel"   
                 xmlns:scg2="clr-namespace:System.Collections.Generic;assembly=System.Core"   
                 xmlns:scg3="clr-namespace:System.Collections.Generic;assembly=mscorlib"   
                 xmlns:sd="clr-namespace:System.Data;assembly=System.Data"   
                 xmlns:sl="clr-namespace:System.Linq;assembly=System.Core"   
                 xmlns:st="clr-namespace:System.Text;assembly=mscorlib"   
                 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <p:Sequence DisplayName="Sequential Service"   
              sad:XamlDebuggerXmlReader.FileName="c:\projects\CreationEndpointTest\CreationEndpoint\Service1.xamlx"   
              sap:VirtualizedContainerService.HintSize="233,200"   
              mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces">  
    <p:Sequence.Variables>  
      <p:Variable x:TypeArguments="CorrelationHandle" Name="handle" />  
      <p:Variable x:TypeArguments="x:Int32" Name="data" />  
    </p:Sequence.Variables>  
    <sap:WorkflowViewStateService.ViewState>  
      <scg3:Dictionary x:TypeArguments="x:String, x:Object">  
        <x:Boolean x:Key="IsExpanded">True</x:Boolean>  
      </scg3:Dictionary>  
    </sap:WorkflowViewStateService.ViewState>  
    <p:WriteLine sap:VirtualizedContainerService.HintSize="211,61" Text="Hello, world" />  
  </p:Sequence>  
</WorkflowService>  
```  
  
```csharp  
// CreationEndpointElement.cs  
using System;  
using System.Configuration;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Description;  
using Shared;  
  
namespace CreationEndpointTest  
{  
    //config element for CreationEndpoint  
    public class CreationEndpointElement : StandardEndpointElement  
    {  
        protected override Type EndpointType  
        {  
            get { return typeof(CreationEndpoint); }  
        }  
  
        protected override ConfigurationPropertyCollection Properties  
        {  
            get  
            {  
                ConfigurationPropertyCollection properties = base.Properties;  
                properties.Add(new ConfigurationProperty("name", typeof(String), null, ConfigurationPropertyOptions.IsRequired));  
                return properties;  
            }  
        }  
  
        protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
        {  
            return new CreationEndpoint();  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
    }  
  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
}  
```  
  
```xml  
<!-- web.config -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <!--register CreationEndpoint-->  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
    <extensions>  
      <endpointExtensions>  
        <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, Shared, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </endpointExtensions>  
    </extensions>  
    <services>  
      <!-- add endpoint to service-->  
      <service name="Workflow1" behaviorConfiguration="basicConfig" >  
        <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="basicConfig">  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```csharp  
// IWorkflowCreation.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
  
namespace Shared  
{  
    //service contract exposed from the endpoint  
    [ServiceContract(Name = "IWorkflowCreation")]  
    public interface IWorkflowCreation  
    {  
        [OperationContract(Name = "Create")]  
        Guid Create(IDictionary<string, object> inputs);  
  
        [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
        void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
    }  
}  
```  
  
```csharp  
// CreationEndpoint.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Channels;  
using System.ServiceModel;  
using System.Globalization;  
using System.Diagnostics;  
  
namespace Shared  
{  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
  
        public CreationEndpoint(Binding binding, EndpointAddress address)  
            : base(typeof(IWorkflowCreation), binding, address) { }  
  
        public CreationEndpoint()  
            : this(GetDefaultBinding(),  
                new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative)))) { }  
  
        static Uri DefaultBaseUri  
        {  
            get  
            {  
                if (defaultBaseUri == null)  
                {  
                    defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                        Process.GetCurrentProcess().Id,  
                        AppDomain.CurrentDomain.Id));  
                }  
                return defaultBaseUri;  
            }  
        }  
  
        //defaults to NetNamedPipeBinding  
        public static Binding GetDefaultBinding()  
        {  
            return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
        }  
  
        protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
        {  
            //Create was called by client  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                return Guid.Empty;  
            }  
  
            //CreateWithInstanceId was called by client  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                return (Guid)inputs[1];  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
        }  
  
        protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
        {  
            WorkflowCreationContext creationContext = new WorkflowCreationContext();  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to the workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
                //reply to client with instanceId  
                responseContext.SendResponse(instanceId, null);  
            }  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
            return creationContext;  
        }  
    }  
}  
```  
  
```csharp  
// CreationEndpointClient.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Shared;  
using System.ServiceModel;  
  
namespace CreationClient  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                //client using BasicHttpBinding  
                IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/MyCreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                Console.WriteLine("Press return to exit ...");  
                Console.ReadLine();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex);  
                Console.ReadLine();  
            }  
  
        }  
    }  
  
}  
```  
  
 Questo esempio può sembrare un elemento di confusione poiché non si implementa mai un servizio che consente di implementare `IWorkflowCreation`. Il motivo è rappresentato dal fatto che l'implementazione viene effettuata da `CreationEndpoint`.  
  
## <a name="see-also"></a>Vedere anche  
 [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Hosting in Internet Information Services](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [Procedure consigliate per l'hosting in Internet Information Services (IIS)](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Istruzioni per l'hosting su Internet Information Services](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)  
 [Architettura del flusso di lavoro di Windows](../../../../docs/framework/windows-workflow-foundation/architecture.md)  
 [Segnalibro di ripresa WorkflowHostingEndpoint](../../../../docs/framework/windows-workflow-foundation/samples/workflowhostingendpoint-resume-bookmark.md)  
 [Riallocazione di Progettazione flussi di lavoro](../../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [Panoramica del flusso di lavoro di Windows](../../../../docs/framework/windows-workflow-foundation/overview.md)

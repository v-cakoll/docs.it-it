# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a>Uso di dotnet-svcutil.xmlserializer in .NET Core

## <a name="prerequisites"></a>Prerequisiti

Per il funzionamento di dotnet-svcutil.xmlserializer, è necessario quanto segue. 

* [.NET Core 2.1 SDK o versione successiva](https://www.microsoft.com/net/download/dotnet-core/sdk-2.1.300)
* [Runtime di .NET Core 2.1 o versione successiva](https://www.microsoft.com/net/download/dotnet-core/runtime-2.1.0)

È possibile usare il comando `dotnet --info` per controllare quali versioni di .NET Core SDK e del runtime sono già installate.

Per usare dotnet-svcutil.xmlserializer in un'applicazione console .NET Core:

1. Creare un servizio WCF denominato "MyWCFService" usando il modello predefinito "Applicazione del servizio WCF" in .NET Framework.  Aggiungere l'attributo ```[XmlSerializerFormat]``` nel metodo del servizio, come di seguito
    ```c#
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```
2. Creare un'applicazione console .NET Core come applicazione client WCF che specifica come destinazione netcoreapp 2.1. Creare, ad esempio, un'app denominata "MyWCFClient" con il comando,
    ```
    dotnet new console --name MyWCFClient
    ```
    Assicurarsi che il file con estensione csproj specifichi come destinazione netcoreapp 2.1. A questo scopo, usare l'elemento XML seguente nel file con estensione csproj
    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```
3. Aggiungere a System.ServiceModel.Http un riferimento al pacchetto eseguendo il comando seguente:
   
   ```dotnet add package System.ServiceModel.Http -v 4.5.0```

4. Aggiungere il codice client WCF:
    ```csharp
    using System.ServiceModel;
    
    class Program
    {
        static void Main(string[] args)
        {
            var myBinding = new BasicHttpBinding();
            var myEndpoint = new EndpointAddress("http://localhost:2561/Service1.svc"); //Fill your service url here
            var myChannelFactory = new ChannelFactory<IService1>(myBinding, myEndpoint);
            IService1 client = myChannelFactory.CreateChannel();
            string s = client.GetData(1);
            ((ICommunicationObject)client).Close();
        }
    }

    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```
5. Modificare il file con estensione csproj e aggiungere un riferimento al pacchetto dotnet-svcutil.xmlserializer. Ad esempio:

    i. Eseguire il comando: `dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`

    ii. Aggiungere le righe seguenti in MyWCFClient.csproj,
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. Compilare l'applicazione eseguendo `dotnet build`. Se è stato eseguito tutto correttamente, un assembly denominato MyWCFClient.XmlSerializers.dll verrà generato nella cartella di output. Se lo strumento non è riuscito a generare l'assembly, verranno visualizzati avvisi nell'output di compilazione.

7. Avviare il servizio WCF, ad esempio eseguendo http://localhost:2561/Service1.svc nel browser, quindi avviare l'applicazione client, che caricherà automaticamente e userà i serializzatori pregenerati in fase di esecuzione.

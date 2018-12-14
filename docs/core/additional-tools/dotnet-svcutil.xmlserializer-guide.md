# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a><span data-ttu-id="147c2-101">Uso di dotnet-svcutil.xmlserializer in .NET Core</span><span class="sxs-lookup"><span data-stu-id="147c2-101">Using dotnet-svcutil.xmlserializer on .NET Core</span></span>

## <a name="prerequisites"></a><span data-ttu-id="147c2-102">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="147c2-102">Prerequisites</span></span>

<span data-ttu-id="147c2-103">Per il funzionamento di dotnet-svcutil.xmlserializer, è necessario quanto segue.</span><span class="sxs-lookup"><span data-stu-id="147c2-103">The following is required for dotnet-svcutil.xmlserializer to work.</span></span> 

* [<span data-ttu-id="147c2-104">.NET Core 2.1 SDK o versione successiva</span><span class="sxs-lookup"><span data-stu-id="147c2-104">.NET Core 2.1 SDK or later</span></span>](https://www.microsoft.com/net/download/dotnet-core/sdk-2.1.300)
* [<span data-ttu-id="147c2-105">Runtime di .NET Core 2.1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="147c2-105">.NET Core Runtime 2.1 or later</span></span>](https://www.microsoft.com/net/download/dotnet-core/runtime-2.1.0)

<span data-ttu-id="147c2-106">È possibile usare il comando `dotnet --info` per controllare quali versioni di .NET Core SDK e del runtime sono già installate.</span><span class="sxs-lookup"><span data-stu-id="147c2-106">You can use the command `dotnet --info` to check which versions of .NET Core SDK and runtime you already have installed.</span></span>

<span data-ttu-id="147c2-107">Per usare dotnet-svcutil.xmlserializer in un'applicazione console .NET Core:</span><span class="sxs-lookup"><span data-stu-id="147c2-107">To use dotnet-svcutil.xmlserializer in a .NET Core console application:</span></span>

1. <span data-ttu-id="147c2-108">Creare un servizio WCF denominato "MyWCFService" usando il modello predefinito "Applicazione del servizio WCF" in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="147c2-108">Create a WCF Service named 'MyWCFService' using the default template 'WCF Service Application' in .NET Framework.</span></span>  <span data-ttu-id="147c2-109">Aggiungere l'attributo ```[XmlSerializerFormat]``` nel metodo del servizio, come di seguito</span><span class="sxs-lookup"><span data-stu-id="147c2-109">Add ```[XmlSerializerFormat]``` attribute on the service method like the following</span></span>
    ```c#
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```
2. <span data-ttu-id="147c2-110">Creare un'applicazione console .NET Core come applicazione client WCF che specifica come destinazione netcoreapp 2.1. Creare, ad esempio, un'app denominata "MyWCFClient" con il comando,</span><span class="sxs-lookup"><span data-stu-id="147c2-110">Create a .NET Core console application as WCF client application that targets at netcoreapp 2.1, e.g. create an app named 'MyWCFClient' with the command,</span></span>
    ```
    dotnet new console --name MyWCFClient
    ```
    <span data-ttu-id="147c2-111">Assicurarsi che il file con estensione csproj specifichi come destinazione netcoreapp 2.1.</span><span class="sxs-lookup"><span data-stu-id="147c2-111">Make sure your csproj targets a netcoreapp 2.1.</span></span> <span data-ttu-id="147c2-112">A questo scopo, usare l'elemento XML seguente nel file con estensione csproj</span><span class="sxs-lookup"><span data-stu-id="147c2-112">This is done using the following XML element in your .csproj file</span></span>
    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```
3. <span data-ttu-id="147c2-113">Aggiungere a System.ServiceModel.Http un riferimento al pacchetto eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="147c2-113">Add a package reference to System.ServiceModel.Http by running the following command:</span></span>
   
   ```dotnet add package System.ServiceModel.Http -v 4.5.0```

4. <span data-ttu-id="147c2-114">Aggiungere il codice client WCF:</span><span class="sxs-lookup"><span data-stu-id="147c2-114">Add the WCF Client code:</span></span>
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
5. <span data-ttu-id="147c2-115">Modificare il file con estensione csproj e aggiungere un riferimento al pacchetto dotnet-svcutil.xmlserializer.</span><span class="sxs-lookup"><span data-stu-id="147c2-115">Edit the .csproj file and add a reference to the dotnet-svcutil.xmlserializer package.</span></span> <span data-ttu-id="147c2-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="147c2-116">For example:</span></span>

    <span data-ttu-id="147c2-117">i.</span><span class="sxs-lookup"><span data-stu-id="147c2-117">i.</span></span> <span data-ttu-id="147c2-118">Eseguire il comando: `dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`</span><span class="sxs-lookup"><span data-stu-id="147c2-118">Run command: `dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`</span></span>

    <span data-ttu-id="147c2-119">ii.</span><span class="sxs-lookup"><span data-stu-id="147c2-119">ii.</span></span> <span data-ttu-id="147c2-120">Aggiungere le righe seguenti in MyWCFClient.csproj,</span><span class="sxs-lookup"><span data-stu-id="147c2-120">Add the following lines in MyWCFClient.csproj,</span></span>
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. <span data-ttu-id="147c2-121">Compilare l'applicazione eseguendo `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="147c2-121">Build the application by running `dotnet build`.</span></span> <span data-ttu-id="147c2-122">Se è stato eseguito tutto correttamente, un assembly denominato MyWCFClient.XmlSerializers.dll verrà generato nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="147c2-122">If everything succeeds, an assembly named MyWCFClient.XmlSerializers.dll will be generated in the output folder.</span></span> <span data-ttu-id="147c2-123">Se lo strumento non è riuscito a generare l'assembly, verranno visualizzati avvisi nell'output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="147c2-123">You will see warnings in the build output if the tool failed to generate the assembly.</span></span>

7. <span data-ttu-id="147c2-124">Avviare il servizio WCF, ad esempio eseguendo http://localhost:2561/Service1.svc nel browser,</span><span class="sxs-lookup"><span data-stu-id="147c2-124">Start the WCF service e.g. by running http://localhost:2561/Service1.svc in the browser.</span></span> <span data-ttu-id="147c2-125">quindi avviare l'applicazione client, che caricherà automaticamente e userà i serializzatori pregenerati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="147c2-125">Then start the client application, and it will automatically load and use the pre-generated serializers at runtime.</span></span>

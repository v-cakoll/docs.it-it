---
title: Uso di DotNet-Svcutil. XmlSerializer
description: Informazioni sull'uso del pacchetto NuGet `dotnet-svcutil.xmlserializer` per pregenerare un assembly di serializzazione per i progetti .NET Core.
author: huanwu
ms.date: 11/27/2018
ms.openlocfilehash: 4811647c294118cb160d25805e7d3ada97f071f9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344892"
---
# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a><span data-ttu-id="49139-103">Uso di dotnet-svcutil.xmlserializer in .NET Core</span><span class="sxs-lookup"><span data-stu-id="49139-103">Using dotnet-svcutil.xmlserializer on .NET Core</span></span>

<span data-ttu-id="49139-104">Il pacchetto NuGet `dotnet-svcutil.xmlserializer` consente di pregenerare un assembly di serializzazione per i progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49139-104">The `dotnet-svcutil.xmlserializer` NuGet package can pre-generate a serialization assembly for .NET Core projects.</span></span> <span data-ttu-id="49139-105">Pregenera il codice di serializzazione C# per i tipi presenti nell'applicazione client usati dal contratto di servizio WCF e serializzabili da XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="49139-105">It pre-generates C# serialization code for the types in the client application that are used by the WCF Service Contract and that can be serialized by the XmlSerializer.</span></span> <span data-ttu-id="49139-106">Ciò migliora le prestazioni di avvio della serializzazione XML durante la serializzazione o la deserializzazione di oggetti di tali tipi.</span><span class="sxs-lookup"><span data-stu-id="49139-106">This improves the startup performance of XML serialization when serializing or deserializing objects of those types.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="49139-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="49139-107">Prerequisites</span></span>

* <span data-ttu-id="49139-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="49139-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later</span></span>
* <span data-ttu-id="49139-109">Editor di codice preferito</span><span class="sxs-lookup"><span data-stu-id="49139-109">Your favorite code editor</span></span>

<span data-ttu-id="49139-110">È possibile usare il comando `dotnet --info` per controllare quali versioni di .NET Core SDK e del runtime sono già installate.</span><span class="sxs-lookup"><span data-stu-id="49139-110">You can use the command `dotnet --info` to check which versions of .NET Core SDK and runtime you already have installed.</span></span>

## <a name="getting-started"></a><span data-ttu-id="49139-111">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="49139-111">Getting started</span></span>

<span data-ttu-id="49139-112">Per usare `dotnet-svcutil.xmlserializer` in un'applicazione console .NET Core:</span><span class="sxs-lookup"><span data-stu-id="49139-112">To use `dotnet-svcutil.xmlserializer` in a .NET Core console application:</span></span>

1. <span data-ttu-id="49139-113">Creare un servizio WCF denominato "MyWCFService" usando il modello predefinito "Applicazione del servizio WCF" in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="49139-113">Create a WCF Service named 'MyWCFService' using the default template 'WCF Service Application' in .NET Framework.</span></span> <span data-ttu-id="49139-114">Aggiungere l'attributo `[XmlSerializerFormat]` nel metodo del servizio, come di seguito:</span><span class="sxs-lookup"><span data-stu-id="49139-114">Add `[XmlSerializerFormat]` attribute on the service method like the following:</span></span>

   ```csharp
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

2. <span data-ttu-id="49139-115">Creare un'applicazione console .NET Core come applicazione client WCF che ha come destinazione .NET Core 2.1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="49139-115">Create a .NET Core console application as WCF client application that targets at .NET Core 2.1 or later versions.</span></span> <span data-ttu-id="49139-116">Creare, ad esempio, un'app denominata "MyWCFClient" con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="49139-116">For example, create an app named 'MyWCFClient' with the following command:</span></span>

    ```dotnetcli
    dotnet new console --name MyWCFClient
    ```

    <span data-ttu-id="49139-117">Per verificare che la piattaforma di destinazione del progetto sia .NET Core 2.1 o versione successiva, ispezionare l'elemento XML `TargetFramework` nel file del progetto:</span><span class="sxs-lookup"><span data-stu-id="49139-117">To ensure your project is targeting .NET Core 2.1 or later, inspect the `TargetFramework` XML element in your project file:</span></span>

    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```

3. <span data-ttu-id="49139-118">Aggiungere un riferimento al pacchetto a `System.ServiceModel.Http` eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="49139-118">Add a package reference to `System.ServiceModel.Http` by running the following command:</span></span>

    ```dotnetcli
    dotnet add package System.ServiceModel.Http
    ```

4. <span data-ttu-id="49139-119">Aggiungere il codice client WCF:</span><span class="sxs-lookup"><span data-stu-id="49139-119">Add the WCF Client code:</span></span>

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

5. <span data-ttu-id="49139-120">Aggiungere un riferimento al pacchetto `dotnet-svcutil.xmlserializer` eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="49139-120">Add a reference to the `dotnet-svcutil.xmlserializer` package by running the following command:</span></span>
  
    ```dotnetcli
    dotnet add package dotnet-svcutil.xmlserializer
    ```

    <span data-ttu-id="49139-121">L'esecuzione del comando determina l'aggiunta al file del progetto di una voce simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="49139-121">Running the command should add an entry to your project file similar to this:</span></span>
  
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. <span data-ttu-id="49139-122">Compilare l'applicazione eseguendo `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="49139-122">Build the application by running `dotnet build`.</span></span> <span data-ttu-id="49139-123">Se è stato eseguito tutto correttamente, verrà generato un assembly denominato *MyWCFClient.XmlSerializers.dll* nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="49139-123">If everything succeeds, an assembly named *MyWCFClient.XmlSerializers.dll* is generated in the output folder.</span></span> <span data-ttu-id="49139-124">Se lo strumento non è riuscito a generare l'assembly, verranno visualizzati avvisi nell'output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="49139-124">If the tool failed to generate the assembly, you'll see warnings in the build output.</span></span>

7. <span data-ttu-id="49139-125">Avviare il servizio WCF, ad esempio eseguendo `http://localhost:2561/Service1.svc` nel browser,</span><span class="sxs-lookup"><span data-stu-id="49139-125">Start the WCF service by, for example, running `http://localhost:2561/Service1.svc` in the browser.</span></span> <span data-ttu-id="49139-126">quindi avviare l'applicazione client, che caricherà automaticamente e userà i serializzatori pregenerati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="49139-126">Then start the client application, and it will automatically load and use the pre-generated serializers at runtime.</span></span>

---
title: Uso di DotNet-Svcutil. XmlSerializer
description: Informazioni sull'uso del pacchetto NuGet `dotnet-svcutil.xmlserializer` per pregenerare un assembly di serializzazione per i progetti .NET Core.
author: huanwu
ms.date: 11/27/2018
ms.openlocfilehash: 14bb2e8a85ec35f08b0a83b9734a64d751074f1b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284325"
---
# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a>Uso di dotnet-svcutil.xmlserializer in .NET Core

Il pacchetto NuGet `dotnet-svcutil.xmlserializer` consente di pregenerare un assembly di serializzazione per i progetti .NET Core. Pregenera il codice di serializzazione C# per i tipi presenti nell'applicazione client usati dal contratto di servizio WCF e serializzabili da XmlSerializer. Ciò migliora le prestazioni di avvio della serializzazione XML durante la serializzazione o la deserializzazione di oggetti di tali tipi.

## <a name="prerequisites"></a>Prerequisiti

* [.NET Core 2,1 SDK](https://dotnet.microsoft.com/download) o versione successiva
* Editor di codice preferito

È possibile usare il comando `dotnet --info` per controllare quali versioni di .NET Core SDK e del runtime sono già installate.

## <a name="getting-started"></a>Introduzione

Per usare `dotnet-svcutil.xmlserializer` in un'applicazione console .NET Core:

1. Creare un servizio WCF denominato "MyWCFService" usando il modello predefinito "Applicazione del servizio WCF" in .NET Framework. Aggiungere l'attributo `[XmlSerializerFormat]` nel metodo del servizio, come di seguito:

   ```csharp
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

2. Creare un'applicazione console .NET Core come applicazione client WCF che ha come destinazione .NET Core 2.1 o versioni successive. Creare, ad esempio, un'app denominata "MyWCFClient" con il comando seguente:

    ```dotnetcli
    dotnet new console --name MyWCFClient
    ```

    Per verificare che la piattaforma di destinazione del progetto sia .NET Core 2.1 o versione successiva, ispezionare l'elemento XML `TargetFramework` nel file del progetto:

    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```

3. Aggiungere un riferimento al pacchetto a `System.ServiceModel.Http` eseguendo il comando riportato di seguito:

    ```dotnetcli
    dotnet add package System.ServiceModel.Http
    ```

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

5. Aggiungere un riferimento al pacchetto `dotnet-svcutil.xmlserializer` eseguendo il comando riportato di seguito:
  
    ```dotnetcli
    dotnet add package dotnet-svcutil.xmlserializer
    ```

    L'esecuzione del comando determina l'aggiunta al file del progetto di una voce simile alla seguente:
  
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. Compilare l'applicazione eseguendo `dotnet build`. Se è stato eseguito tutto correttamente, verrà generato un assembly denominato *MyWCFClient.XmlSerializers.dll* nella cartella di output. Se lo strumento non è riuscito a generare l'assembly, verranno visualizzati avvisi nell'output di compilazione.

7. Avviare il servizio WCF, ad esempio eseguendo `http://localhost:2561/Service1.svc` nel browser, Avviare quindi l'applicazione client e caricherà automaticamente e utilizzerà i serializzatori pre-generati in fase di esecuzione.

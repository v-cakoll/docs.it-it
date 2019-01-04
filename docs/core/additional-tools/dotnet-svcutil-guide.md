---
title: Panoramica dello strumento WCF svcutil
description: Panoramica dello strumento Microsoft WCF dotnet-svcutil che aggiunge funzionalità per i progetti .NET Core e ASP.NET Core, come lo strumento WCF svcutil per i progetti .NET Framework.
author: mlacouture
ms.date: 08/20/2018
ms.custom: seodec18
ms.openlocfilehash: e42ec0d4072c56456c824a814f1b383ea70a9307
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237259"
---
# <a name="wcf-dotnet-svcutil-tool-for-net-core"></a><span data-ttu-id="29782-103">Strumento WCF dotnet-svcutil per .NET Core</span><span class="sxs-lookup"><span data-stu-id="29782-103">WCF dotnet-svcutil tool for .NET Core</span></span>

<span data-ttu-id="29782-104">Lo strumento Windows Communication Foundation (WCF) **dotnet-svcutil** è uno strumento dell'interfaccia della riga di comando di .NET Core che consente di recuperare metadati da un servizio Web, in un percorso di rete o da un file WSDL e di generare una classe WCF contenente metodi del proxy client che accedono alle operazioni del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="29782-104">The Windows Communication Foundation (WCF) **dotnet-svcutil** tool is a .NET Core CLI tool that retrieves metadata from a web service on a network location or from a WSDL file, and generates a WCF class containing client proxy methods that access the web service operations.</span></span>

<span data-ttu-id="29782-105">Analogo allo strumento [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per i progetti .NET Framework, **dotnet-svcutil** è uno strumento da riga di comando per la generazione di un riferimento al servizio Web compatibile con i progetti .NET Core e .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="29782-105">Similar to the [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool for .NET Framework projects, the **dotnet-svcutil** is a command-line tool for generating a web service reference compatible with .NET Core and .NET Standard projects.</span></span>

<span data-ttu-id="29782-106">Lo strumento **dotnet-svcutil** rappresenta un'alternativa al provider di servizi connessi di Visuali Studio [**WCF Web Service Reference Provider**](wcf-web-service-reference-guide.md), disponibile per la prima volta con Visual Studio 2017 versione 15.5.</span><span class="sxs-lookup"><span data-stu-id="29782-106">The **dotnet-svcutil** tool is an alternative option to the [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio connected service provider that first shipped with Visual Studio 2017 v15.5.</span></span> <span data-ttu-id="29782-107">Come strumento dell'interfaccia della riga di comando di .NET Core, **dotnet-svcutil** è disponibile come strumento multipiattaforma in Linux, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="29782-107">The **dotnet-svcutil** tool as a .NET Core CLI tool, is available cross-platform on Linux, macOS, and Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29782-108">Si consiglia di fare riferimento solo a servizi provenienti da un'origine attendibile.</span><span class="sxs-lookup"><span data-stu-id="29782-108">You should only reference services from a trusted source.</span></span> <span data-ttu-id="29782-109">L'aggiunta di riferimenti da un'origine non attendibile può compromettere la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="29782-109">Adding references from an untrusted source may compromise security.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="29782-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="29782-110">Prerequisites</span></span>

* <span data-ttu-id="29782-111">[.NET Core SDK](https://dotnet.microsoft.com/download) v1.0.4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="29782-111">[.NET Core SDK](https://dotnet.microsoft.com/download) v1.0.4 or later versions</span></span>
* <span data-ttu-id="29782-112">Editor di codice preferito</span><span class="sxs-lookup"><span data-stu-id="29782-112">Your favorite code editor</span></span>

## <a name="getting-started"></a><span data-ttu-id="29782-113">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="29782-113">Getting started</span></span>

<span data-ttu-id="29782-114">L'esempio seguente illustra la procedura necessaria per aggiungere un riferimento al servizio Web a un progetto console .NET Core e richiamare il servizio.</span><span class="sxs-lookup"><span data-stu-id="29782-114">The following example walks you through the steps required to add a web service reference to a .NET Core console project and invoke the service.</span></span> <span data-ttu-id="29782-115">Si creerà un'applicazione console .NET Core denominata _HelloSvcutil_ e verrà aggiunto un riferimento a un servizio Web che implementa il contratto seguente:</span><span class="sxs-lookup"><span data-stu-id="29782-115">You will create a .NET Core console application named _HelloSvcutil_ and will add a reference to a web service that implements the following contract:</span></span>

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

<span data-ttu-id="29782-116">In questo esempio si presuppone che il servizio Web sia ospitato all'indirizzo seguente: `http://contoso.com/SayHello.svc`</span><span class="sxs-lookup"><span data-stu-id="29782-116">For this example, the web service will be assumed to be hosted at the following address: `http://contoso.com/SayHello.svc`</span></span>

<span data-ttu-id="29782-117">Da una finestra di comando di Windows, macOS o Linux eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="29782-117">From a Windows, macOS, or Linux command window perform the following steps:</span></span>

1. <span data-ttu-id="29782-118">Creare una directory denominata _HelloSvcutil_ per il progetto e renderla la directory corrente, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="29782-118">Create a directory named _HelloSvcutil_ for your project and make it your current directory, as in the following example:</span></span>

```console
mkdir HelloSvcutil
cd HelloSvcutil
```

2. <span data-ttu-id="29782-119">Creare un nuovo progetto console C# in tale directory usando il comando [`dotnet new`](../tools/dotnet-new.md) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="29782-119">Create a new C# console project in that directory using the [`dotnet new`](../tools/dotnet-new.md) command as follows:</span></span>

```console
dotnet new console
```

3. <span data-ttu-id="29782-120">Aprire il file di progetto `HelloSvcutil.csproj` nell'editor, modificare l'elemento `Project` e aggiungere il [`dotnet-svcutil` pacchetto NuGet](https://nuget.org/packages/dotnet-svcutil) come riferimento allo strumento dell'interfaccia della riga di comando, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="29782-120">Open the `HelloSvcutil.csproj` project file in your editor, edit the `Project` element, and add the [`dotnet-svcutil` NuGet package](https://nuget.org/packages/dotnet-svcutil) as a CLI tool reference, using the following code:</span></span>

```xml
<ItemGroup>
  <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.*" />
</ItemGroup>
```

4. <span data-ttu-id="29782-121">Ripristinare il pacchetto _dotnet-svcutil_ usando il comando [`dotnet restore`](../tools/dotnet-restore.md) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="29782-121">Restore the _dotnet-svcutil_ package using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

```console
dotnet restore
```

5. <span data-ttu-id="29782-122">Eseguire _dotnet_ con il comando _svcutil_ per generare il file di riferimento al servizio Web come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="29782-122">Run _dotnet_ with the _svcutil_ command to generate the web service reference file as follows:</span></span>

```console
dotnet svcutil http://contoso.com/SayHello.svc
```
<span data-ttu-id="29782-123">Il file generato viene salvato come _HelloSvcutil/ServiceReference1/Reference.cs_.</span><span class="sxs-lookup"><span data-stu-id="29782-123">The generated file is saved as _HelloSvcutil/ServiceReference1/Reference.cs_.</span></span> <span data-ttu-id="29782-124">Lo strumento _dotnet_svcutil_ aggiunge inoltre al progetto i pacchetti WCF appropriati richiesti dal codice del proxy come riferimenti ai pacchetti.</span><span class="sxs-lookup"><span data-stu-id="29782-124">The _dotnet_svcutil_ tool also adds to the project the appropriate WCF packages required by the proxy code as package references.</span></span>

6. <span data-ttu-id="29782-125">Ripristinare i pacchetti WCF usando il comando [`dotnet restore`](../tools/dotnet-restore.md) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="29782-125">Restore the WCF packages using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

```console
dotnet restore
```

7. <span data-ttu-id="29782-126">Aprire il file `Program.cs` nell'editor, modificare il metodo `Main()` e sostituire il codice generato automaticamente con il codice seguente per richiamare il servizio Web:</span><span class="sxs-lookup"><span data-stu-id="29782-126">Open the `Program.cs` file in your editor, edit the `Main()` method, and replace the auto-generated code with the following code to invoke the web service:</span></span>

```csharp
static void Main(string[] args)
{
    var client = new SayHelloClient();
    Console.WriteLine(client.HelloAsync("dotnet-svcutil").Result);
}
```

8. <span data-ttu-id="29782-127">Eseguire l'applicazione usando il comando [`dotnet run`](../tools/dotnet-run.md) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="29782-127">Run the application using the [`dotnet run`](../tools/dotnet-run.md) command as follows:</span></span>

```console
dotnet run
```
<span data-ttu-id="29782-128">È necessario visualizzare il seguente output: "Hello dotnet-svcutil!"</span><span class="sxs-lookup"><span data-stu-id="29782-128">You should see the following output: "Hello dotnet-svcutil!"</span></span>

<span data-ttu-id="29782-129">Per una descrizione dettagliata dei parametri dello strumento `dotnet-svcutil`, richiamare lo strumento passando il parametro help come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="29782-129">For a detailed description of the `dotnet-svcutil` tool parameters, invoke the tool passing the help parameter as follows:</span></span>

```console
dotnet svcutil --help
```

## <a name="next-steps"></a><span data-ttu-id="29782-130">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="29782-130">Next steps</span></span>

### <a name="feedback--questions"></a><span data-ttu-id="29782-131">Commenti, suggerimenti e domande</span><span class="sxs-lookup"><span data-stu-id="29782-131">Feedback & questions</span></span>

<span data-ttu-id="29782-132">In caso di domande o commenti e suggerimenti, [segnalare un problema in GitHub](https://github.com/dotnet/wcf/issues/new).</span><span class="sxs-lookup"><span data-stu-id="29782-132">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="29782-133">È anche possibile rivedere domande o problemi esistenti [nel repository WCF in GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span><span class="sxs-lookup"><span data-stu-id="29782-133">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

### <a name="release-notes"></a><span data-ttu-id="29782-134">Note sulla versione</span><span class="sxs-lookup"><span data-stu-id="29782-134">Release notes</span></span>

* <span data-ttu-id="29782-135">Fare riferimento alle [note sulla versione](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) per informazioni aggiornate sulle versioni, compresi i problemi noti.</span><span class="sxs-lookup"><span data-stu-id="29782-135">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) for updated release information, including known issues.</span></span>

### <a name="information"></a><span data-ttu-id="29782-136">Informazioni</span><span class="sxs-lookup"><span data-stu-id="29782-136">Information</span></span>

* [<span data-ttu-id="29782-137">Pacchetto NuGet dotnet-svcutil</span><span class="sxs-lookup"><span data-stu-id="29782-137">dotnet-svcutil NuGet Package</span></span>](https://nuget.org/packages/dotnet-svcutil)

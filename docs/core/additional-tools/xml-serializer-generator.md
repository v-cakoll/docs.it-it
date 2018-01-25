---
title: Uso dello strumento Microsoft per la generazione di serializzatori XML in .NET Core
description: Panoramica dello strumento Microsoft per la generazione di serializzatori XML.
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2017
ms.topic: tutorial
ms.prod: .net-core
ms.custom: mvc
ms.openlocfilehash: 4b838cafe1f4835c1c5aa6086c0997a4a9e39a9e
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2018
---
# <a name="using-microsoft-xml-serializer-generator-on-net-core"></a><span data-ttu-id="60147-103">Uso dello strumento Microsoft per la generazione di serializzatori XML in .NET Core</span><span class="sxs-lookup"><span data-stu-id="60147-103">Using Microsoft XML Serializer Generator on .NET Core</span></span>

<span data-ttu-id="60147-104">In questa esercitazione viene illustrato come usare lo strumento Microsoft per la generazione di serializzatori XML in un'applicazione .NET Core di C#.</span><span class="sxs-lookup"><span data-stu-id="60147-104">This tutorial teaches you how to use the Microsoft XML Serializer Generator in a C# .NET Core application.</span></span> <span data-ttu-id="60147-105">Nel corso di questa esercitazione verranno illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="60147-105">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="60147-106">Come creare un'app .NET Core</span><span class="sxs-lookup"><span data-stu-id="60147-106">How to create a .NET Core app</span></span>
> * <span data-ttu-id="60147-107">Come aggiungere un riferimento al pacchetto Microsoft.XmlSerializer.Generator</span><span class="sxs-lookup"><span data-stu-id="60147-107">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> * <span data-ttu-id="60147-108">Come modificare il file MyApp.cspro per aggiungere dipendenze</span><span class="sxs-lookup"><span data-stu-id="60147-108">How to edit your MyApp.csproj to add dependencies</span></span>
> * <span data-ttu-id="60147-109">Come aggiungere una classe e un oggetto XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="60147-109">How to add a class and an XmlSerializer</span></span>
> * <span data-ttu-id="60147-110">Come compilare ed eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="60147-110">How to build and run the application</span></span> 

<span data-ttu-id="60147-111">Lo [strumento per la generazione di serializzatori XML (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) è la soluzione per .NET Framework, mentre il [pacchetto NuGet Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) è la soluzione equivalente per NET Core e .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="60147-111">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the equivalent for .NET Core and .NET Standard projects.</span></span> <span data-ttu-id="60147-112">Crea un assembly di serializzazione XML per tipi contenuti in un assembly per migliorare le prestazioni di avvio della serializzazione XML durante la serializzazione o deserializzazione di oggetti di questi tipi usando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="60147-112">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="60147-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="60147-113">Prerequisites</span></span>

<span data-ttu-id="60147-114">Per completare questa esercitazione:</span><span class="sxs-lookup"><span data-stu-id="60147-114">To complete this tutorial:</span></span>

* <span data-ttu-id="60147-115">Installare [.NET Core SDK 2.1.3 o versione successiva](https://www.microsoft.com/net/download)</span><span class="sxs-lookup"><span data-stu-id="60147-115">Install [.NET Core SDK 2.1.3 or later](https://www.microsoft.com/net/download)</span></span>
* <span data-ttu-id="60147-116">Installare l'editor del codice preferito, se non è già disponibile.</span><span class="sxs-lookup"><span data-stu-id="60147-116">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="60147-117">È necessario installare un editor del codice?</span><span class="sxs-lookup"><span data-stu-id="60147-117">Need to install a code editor?</span></span> <span data-ttu-id="60147-118">Provare [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).</span><span class="sxs-lookup"><span data-stu-id="60147-118">Try [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)!</span></span>
  
## <a name="use-microsoft-xml-serializer-generator-in-a-net-core-console-application"></a><span data-ttu-id="60147-119">Usare lo strumento Microsoft per la generazione di serializzatori XML in un'applicazione console .NET Core</span><span class="sxs-lookup"><span data-stu-id="60147-119">Use Microsoft XML Serializer Generator in a .NET Core console application</span></span> 

<span data-ttu-id="60147-120">Le istruzioni seguenti illustrano come usare lo strumento per la generazione di serializzatori XML in un'applicazione console .NET Core.</span><span class="sxs-lookup"><span data-stu-id="60147-120">The following instructions show you how to use XML Serializer Generator in a .NET Core console application.</span></span>

### <a name="create-a-net-core-console-application"></a><span data-ttu-id="60147-121">Creare un'applicazione console .NET Core</span><span class="sxs-lookup"><span data-stu-id="60147-121">Create a .NET Core console application</span></span>

<span data-ttu-id="60147-122">Aprire un prompt dei comandi e creare una cartella denominata *MyApp*.</span><span class="sxs-lookup"><span data-stu-id="60147-122">Open a command prompt and create a folder named *MyApp*.</span></span> <span data-ttu-id="60147-123">Passare alla cartella creata e digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="60147-123">Navigate to the folder you created and type the following command:</span></span>

```console
dotnet new console
```

### <a name="add-a-reference-to-the-microsoftxmlserializergenerator-package-in-the-myapp-project"></a><span data-ttu-id="60147-124">Aggiungere un riferimento al pacchetto Microsoft.XmlSerializer.Generator nel progetto MyApp</span><span class="sxs-lookup"><span data-stu-id="60147-124">Add a reference to the Microsoft.XmlSerializer.Generator package in the MyApp project</span></span>

<span data-ttu-id="60147-125">Usare il comando [`dotnet add package`](../tools//dotnet-add-package.md) per aggiungere il riferimento nel progetto.</span><span class="sxs-lookup"><span data-stu-id="60147-125">Use the [`dotnet add package`](../tools//dotnet-add-package.md) command to add the reference in your project.</span></span> 

<span data-ttu-id="60147-126">Tipo:</span><span class="sxs-lookup"><span data-stu-id="60147-126">Type:</span></span>
 
 ```console
 dotnet add package Microsoft.XmlSerializer.Generator -v 1.0.0
 ```
 
### <a name="verify-changes-to-myappcsproj-after-adding-the-package"></a><span data-ttu-id="60147-127">Verificare le modifiche a MyApp.csproj dopo aver aggiunto il pacchetto</span><span class="sxs-lookup"><span data-stu-id="60147-127">Verify changes to MyApp.csproj after adding the package</span></span>

<span data-ttu-id="60147-128">Prima di iniziare, aprire l'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="60147-128">Open your code editor and let's get started!</span></span> <span data-ttu-id="60147-129">Si lavorerà ancora dalla directory *MyApp* in cui è stata compilata l'app.</span><span class="sxs-lookup"><span data-stu-id="60147-129">We're still working from the *MyApp* directory we built the app in.</span></span>

<span data-ttu-id="60147-130">Aprire *MyApp.csproj* nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="60147-130">Open *MyApp.csproj* in your text editor.</span></span>

<span data-ttu-id="60147-131">Dopo aver eseguito il comando [`dotnet add package`](../tools//dotnet-add-package.md), al file di progetto *MyApp.csproj* vengono aggiunte le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="60147-131">After running the [`dotnet add package`](../tools//dotnet-add-package.md) command, the following lines are added to your *MyApp.csproj* project file:</span></span>

 ```xml
 <ItemGroup>
    <PackageReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-another-itemgroup-section-for-net-core-cli-tool-support"></a><span data-ttu-id="60147-132">Aggiungere un'altra sezione denominata ItemGroup per il supporto dello strumento dell'interfaccia della riga di comando .NET Core</span><span class="sxs-lookup"><span data-stu-id="60147-132">Add another ItemGroup section for .NET Core CLI Tool support</span></span>
 
 <span data-ttu-id="60147-133">Aggiungere le righe seguenti dopo la sezione `ItemGroup` analizzata:</span><span class="sxs-lookup"><span data-stu-id="60147-133">Add the following lines after the `ItemGroup` section that we inspected:</span></span>
 
 ```xml
 <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-a-class-in-the-application"></a><span data-ttu-id="60147-134">Aggiungere una classe nell'applicazione</span><span class="sxs-lookup"><span data-stu-id="60147-134">Add a class in the application</span></span>

<span data-ttu-id="60147-135">Aprire *Program.cs* nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="60147-135">Open *Program.cs* in your text editor.</span></span> <span data-ttu-id="60147-136">Aggiungere la classe denominata *MyClass* in *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="60147-136">Add the class named *MyClass* in *Program.cs*.</span></span>

```csharp
public class MyClass
{
   public int Value;
}
```

### <a name="create-an-xmlserializer-for-myclass"></a><span data-ttu-id="60147-137">Creare un oggetto `XmlSerializer` per MyClass</span><span class="sxs-lookup"><span data-stu-id="60147-137">Create an `XmlSerializer` for MyClass</span></span>

<span data-ttu-id="60147-138">Aggiungere la riga seguente in *Main* per creare un oggetto `XmlSerializer` per MyClass:</span><span class="sxs-lookup"><span data-stu-id="60147-138">Add the following line inside *Main* to create an `XmlSerializer` for MyClass:</span></span>

```csharp
var serializer = new System.Xml.Serialization.XmlSerializer(typeof(MyClass));
```

### <a name="build-and-run-the-application"></a><span data-ttu-id="60147-139">Compilazione ed esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="60147-139">Build and run the application</span></span>

<span data-ttu-id="60147-140">All'interno della cartella *MyApp* eseguire l'applicazione tramite [`dotnet run`](../tools/dotnet-run.md). In automatico vengono caricati e usati i serializzatori generati in precedenza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="60147-140">Still within the *MyApp* folder, run the application via [`dotnet run`](../tools/dotnet-run.md) and it automatically loads and uses the pre-generated serializers at runtime.</span></span>

<span data-ttu-id="60147-141">Nella finestra di console digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="60147-141">Type the following command in your console window:</span></span>

 ```console
 $ dotnet run
 ```
> [!NOTE]
> <span data-ttu-id="60147-142">[`dotnet run`](../tools/dotnet-run.md) chiama [`dotnet build`](../tools/dotnet-build.md) per assicurarsi che le destinazioni siano state compilate e quindi chiama `dotnet <assembly.dll>` per eseguire l'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="60147-142">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60147-143">I comandi e i passaggi illustrati in questa esercitazione per eseguire l'applicazione vengono usati solo durante la fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="60147-143">The commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="60147-144">Quando si è pronti a distribuire l'app, è opportuno esaminare le diverse [strategie di distribuzione](../deploying/index.md) per le app .NET Core e il comando [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="60147-144">Once you're ready to deploy your app, take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

<span data-ttu-id="60147-145">Se è stato eseguito tutto correttamente, un assembly denominato *MyApp.XmlSerializers.dll* viene generato nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="60147-145">If everything succeeds, an assembly named *MyApp.XmlSerializers.dll* is generated in the output folder.</span></span> 



<span data-ttu-id="60147-146">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="60147-146">Congratulations!</span></span> <span data-ttu-id="60147-147">Sono state eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="60147-147">You have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="60147-148">Creazione di un'app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="60147-148">Created a .NET Core app.</span></span>
> * <span data-ttu-id="60147-149">Aggiunta di un riferimento al pacchetto Microsoft.XmlSerializer.Generator.</span><span class="sxs-lookup"><span data-stu-id="60147-149">Added a reference to the Microsoft.XmlSerializer.Generator package.</span></span>
> * <span data-ttu-id="60147-150">Modifica del file MyApp.cspro per l'aggiunta di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="60147-150">Edited your MyApp.csproj to add dependencies.</span></span>
> * <span data-ttu-id="60147-151">Aggiunta di una classe e un oggetto XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="60147-151">Added a class and an XmlSerializer.</span></span>
> * <span data-ttu-id="60147-152">Compilazione ed esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="60147-152">Built and ran the application.</span></span> 

## <a name="related-resources"></a><span data-ttu-id="60147-153">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="60147-153">Related Resources</span></span>

* [<span data-ttu-id="60147-154">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="60147-154">Introducing XML Serialization</span></span>](../../standard/serialization/introducing-xml-serialization.md)
* [<span data-ttu-id="60147-155">Procedura: Serializzare tramite XmlSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="60147-155">How to: Serialize Using XmlSerializer (C#)</span></span>](../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer)
* [<span data-ttu-id="60147-156">Procedura: Serializzare tramite XmlSerializer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60147-156">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer)
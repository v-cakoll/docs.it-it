---
title: Strumento Microsoft per la generazione di serializzatori XML - .NET Core
description: Panoramica dello strumento Microsoft per la generazione di serializzatori XML. Usare lo strumento per la generazione di serializzatori XML per generare un assembly di serializzazione XML per i tipi contenuti nel progetto.
author: mlacouture
ms.author: johalex
ms.date: 01/19/2017
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 3712ac35a9e08b04a0f555642f43055e9e6232e2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151759"
---
# <a name="using-microsoft-xml-serializer-generator-on-net-core"></a><span data-ttu-id="bae9d-104">Uso dello strumento Microsoft per la generazione di serializzatori XML in .NET Core</span><span class="sxs-lookup"><span data-stu-id="bae9d-104">Using Microsoft XML Serializer Generator on .NET Core</span></span>

<span data-ttu-id="bae9d-105">In questa esercitazione viene illustrato come usare lo strumento Microsoft per la generazione di serializzatori XML in un'applicazione .NET Core di C#.</span><span class="sxs-lookup"><span data-stu-id="bae9d-105">This tutorial teaches you how to use the Microsoft XML Serializer Generator in a C# .NET Core application.</span></span> <span data-ttu-id="bae9d-106">Nel corso di questa esercitazione verranno illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="bae9d-106">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="bae9d-107">Come creare un'app .NET Core</span><span class="sxs-lookup"><span data-stu-id="bae9d-107">How to create a .NET Core app</span></span>
> * <span data-ttu-id="bae9d-108">Come aggiungere un riferimento al pacchetto Microsoft.XmlSerializer.Generator</span><span class="sxs-lookup"><span data-stu-id="bae9d-108">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> * <span data-ttu-id="bae9d-109">Come modificare il file MyApp.cspro per aggiungere dipendenze</span><span class="sxs-lookup"><span data-stu-id="bae9d-109">How to edit your MyApp.csproj to add dependencies</span></span>
> * <span data-ttu-id="bae9d-110">Come aggiungere una classe e un oggetto XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="bae9d-110">How to add a class and an XmlSerializer</span></span>
> * <span data-ttu-id="bae9d-111">Come compilare ed eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="bae9d-111">How to build and run the application</span></span> 

<span data-ttu-id="bae9d-112">Lo [strumento per la generazione di serializzatori XML (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) è la soluzione per .NET Framework, mentre il [pacchetto NuGet Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) è la soluzione equivalente per NET Core e .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="bae9d-112">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the equivalent for .NET Core and .NET Standard projects.</span></span> <span data-ttu-id="bae9d-113">Crea un assembly di serializzazione XML per tipi contenuti in un assembly per migliorare le prestazioni di avvio della serializzazione XML durante la serializzazione o deserializzazione di oggetti di questi tipi usando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="bae9d-113">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bae9d-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="bae9d-114">Prerequisites</span></span>

<span data-ttu-id="bae9d-115">Per completare questa esercitazione:</span><span class="sxs-lookup"><span data-stu-id="bae9d-115">To complete this tutorial:</span></span>

* <span data-ttu-id="bae9d-116">Installare [.NET Core 2.1 SDK o versione successiva](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="bae9d-116">Install [.NET Core 2.1 SDK or later](https://www.microsoft.com/net/download).</span></span>
* <span data-ttu-id="bae9d-117">Installare l'editor del codice preferito, se non è già disponibile.</span><span class="sxs-lookup"><span data-stu-id="bae9d-117">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="bae9d-118">È necessario installare un editor del codice?</span><span class="sxs-lookup"><span data-stu-id="bae9d-118">Need to install a code editor?</span></span> <span data-ttu-id="bae9d-119">Provare [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).</span><span class="sxs-lookup"><span data-stu-id="bae9d-119">Try [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)!</span></span>
  
## <a name="use-microsoft-xml-serializer-generator-in-a-net-core-console-application"></a><span data-ttu-id="bae9d-120">Usare lo strumento Microsoft per la generazione di serializzatori XML in un'applicazione console .NET Core</span><span class="sxs-lookup"><span data-stu-id="bae9d-120">Use Microsoft XML Serializer Generator in a .NET Core console application</span></span> 

<span data-ttu-id="bae9d-121">Le istruzioni seguenti illustrano come usare lo strumento per la generazione di serializzatori XML in un'applicazione console .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bae9d-121">The following instructions show you how to use XML Serializer Generator in a .NET Core console application.</span></span>

### <a name="create-a-net-core-console-application"></a><span data-ttu-id="bae9d-122">Creare un'applicazione console .NET Core</span><span class="sxs-lookup"><span data-stu-id="bae9d-122">Create a .NET Core console application</span></span>

<span data-ttu-id="bae9d-123">Aprire un prompt dei comandi e creare una cartella denominata *MyApp*.</span><span class="sxs-lookup"><span data-stu-id="bae9d-123">Open a command prompt and create a folder named *MyApp*.</span></span> <span data-ttu-id="bae9d-124">Passare alla cartella creata e digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="bae9d-124">Navigate to the folder you created and type the following command:</span></span>

```console
dotnet new console
```

### <a name="add-a-reference-to-the-microsoftxmlserializergenerator-package-in-the-myapp-project"></a><span data-ttu-id="bae9d-125">Aggiungere un riferimento al pacchetto Microsoft.XmlSerializer.Generator nel progetto MyApp</span><span class="sxs-lookup"><span data-stu-id="bae9d-125">Add a reference to the Microsoft.XmlSerializer.Generator package in the MyApp project</span></span>

<span data-ttu-id="bae9d-126">Usare il comando [`dotnet add package`](../tools//dotnet-add-package.md) per aggiungere il riferimento nel progetto.</span><span class="sxs-lookup"><span data-stu-id="bae9d-126">Use the [`dotnet add package`](../tools//dotnet-add-package.md) command to add the reference in your project.</span></span> 

<span data-ttu-id="bae9d-127">Tipo:</span><span class="sxs-lookup"><span data-stu-id="bae9d-127">Type:</span></span>
 
 ```console
 dotnet add package Microsoft.XmlSerializer.Generator -v 1.0.0
 ```
 
### <a name="verify-changes-to-myappcsproj-after-adding-the-package"></a><span data-ttu-id="bae9d-128">Verificare le modifiche a MyApp.csproj dopo aver aggiunto il pacchetto</span><span class="sxs-lookup"><span data-stu-id="bae9d-128">Verify changes to MyApp.csproj after adding the package</span></span>

<span data-ttu-id="bae9d-129">Prima di iniziare, aprire l'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="bae9d-129">Open your code editor and let's get started!</span></span> <span data-ttu-id="bae9d-130">Si lavorerà ancora dalla directory *MyApp* in cui è stata compilata l'app.</span><span class="sxs-lookup"><span data-stu-id="bae9d-130">We're still working from the *MyApp* directory we built the app in.</span></span>

<span data-ttu-id="bae9d-131">Aprire *MyApp.csproj* nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="bae9d-131">Open *MyApp.csproj* in your text editor.</span></span>

<span data-ttu-id="bae9d-132">Dopo aver eseguito il comando [`dotnet add package`](../tools//dotnet-add-package.md), al file di progetto *MyApp.csproj* vengono aggiunte le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="bae9d-132">After running the [`dotnet add package`](../tools//dotnet-add-package.md) command, the following lines are added to your *MyApp.csproj* project file:</span></span>

 ```xml
 <ItemGroup>
    <PackageReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-another-itemgroup-section-for-net-core-cli-tool-support"></a><span data-ttu-id="bae9d-133">Aggiungere un'altra sezione denominata ItemGroup per il supporto dello strumento dell'interfaccia della riga di comando .NET Core</span><span class="sxs-lookup"><span data-stu-id="bae9d-133">Add another ItemGroup section for .NET Core CLI Tool support</span></span>
 
 <span data-ttu-id="bae9d-134">Aggiungere le righe seguenti dopo la sezione `ItemGroup` analizzata:</span><span class="sxs-lookup"><span data-stu-id="bae9d-134">Add the following lines after the `ItemGroup` section that we inspected:</span></span>
 
 ```xml
 <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-a-class-in-the-application"></a><span data-ttu-id="bae9d-135">Aggiungere una classe nell'applicazione</span><span class="sxs-lookup"><span data-stu-id="bae9d-135">Add a class in the application</span></span>

<span data-ttu-id="bae9d-136">Aprire *Program.cs* nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="bae9d-136">Open *Program.cs* in your text editor.</span></span> <span data-ttu-id="bae9d-137">Aggiungere la classe denominata *MyClass* in *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="bae9d-137">Add the class named *MyClass* in *Program.cs*.</span></span>

```csharp
public class MyClass
{
   public int Value;
}
```

### <a name="create-an-xmlserializer-for-myclass"></a><span data-ttu-id="bae9d-138">Creare un oggetto `XmlSerializer` per MyClass</span><span class="sxs-lookup"><span data-stu-id="bae9d-138">Create an `XmlSerializer` for MyClass</span></span>

<span data-ttu-id="bae9d-139">Aggiungere la riga seguente in *Main* per creare un oggetto `XmlSerializer` per MyClass:</span><span class="sxs-lookup"><span data-stu-id="bae9d-139">Add the following line inside *Main* to create an `XmlSerializer` for MyClass:</span></span>

```csharp
var serializer = new System.Xml.Serialization.XmlSerializer(typeof(MyClass));
```

### <a name="build-and-run-the-application"></a><span data-ttu-id="bae9d-140">Compilazione ed esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="bae9d-140">Build and run the application</span></span>

<span data-ttu-id="bae9d-141">All'interno della cartella *MyApp* eseguire l'applicazione tramite [`dotnet run`](../tools/dotnet-run.md). In automatico vengono caricati e usati i serializzatori generati in precedenza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bae9d-141">Still within the *MyApp* folder, run the application via [`dotnet run`](../tools/dotnet-run.md) and it automatically loads and uses the pre-generated serializers at runtime.</span></span>

<span data-ttu-id="bae9d-142">Nella finestra di console digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="bae9d-142">Type the following command in your console window:</span></span>

 ```console
 $ dotnet run
 ```
> [!NOTE]
> <span data-ttu-id="bae9d-143">[`dotnet run`](../tools/dotnet-run.md) chiama [`dotnet build`](../tools/dotnet-build.md) per assicurarsi che le destinazioni siano state compilate e quindi chiama `dotnet <assembly.dll>` per eseguire l'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bae9d-143">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bae9d-144">I comandi e i passaggi illustrati in questa esercitazione per eseguire l'applicazione vengono usati solo durante la fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="bae9d-144">The commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="bae9d-145">Quando si è pronti a distribuire l'app, è opportuno esaminare le diverse [strategie di distribuzione](../deploying/index.md) per le app .NET Core e il comando [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="bae9d-145">Once you're ready to deploy your app, take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

<span data-ttu-id="bae9d-146">Se è stato eseguito tutto correttamente, un assembly denominato *MyApp.XmlSerializers.dll* viene generato nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="bae9d-146">If everything succeeds, an assembly named *MyApp.XmlSerializers.dll* is generated in the output folder.</span></span> 



<span data-ttu-id="bae9d-147">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="bae9d-147">Congratulations!</span></span> <span data-ttu-id="bae9d-148">Sono state eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="bae9d-148">You have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="bae9d-149">Creazione di un'app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bae9d-149">Created a .NET Core app.</span></span>
> * <span data-ttu-id="bae9d-150">Aggiunta di un riferimento al pacchetto Microsoft.XmlSerializer.Generator.</span><span class="sxs-lookup"><span data-stu-id="bae9d-150">Added a reference to the Microsoft.XmlSerializer.Generator package.</span></span>
> * <span data-ttu-id="bae9d-151">Modifica del file MyApp.cspro per l'aggiunta di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="bae9d-151">Edited your MyApp.csproj to add dependencies.</span></span>
> * <span data-ttu-id="bae9d-152">Aggiunta di una classe e un oggetto XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="bae9d-152">Added a class and an XmlSerializer.</span></span>
> * <span data-ttu-id="bae9d-153">Compilazione ed esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bae9d-153">Built and ran the application.</span></span> 

## <a name="related-resources"></a><span data-ttu-id="bae9d-154">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="bae9d-154">Related Resources</span></span>

* [<span data-ttu-id="bae9d-155">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="bae9d-155">Introducing XML Serialization</span></span>](../../standard/serialization/introducing-xml-serialization.md)
* [<span data-ttu-id="bae9d-156">Procedura: Serializzare tramite XmlSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="bae9d-156">How to: Serialize Using XmlSerializer (C#)</span></span>](../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
* [<span data-ttu-id="bae9d-157">Procedura: Serializzare tramite XmlSerializer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bae9d-157">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)

---
title: Strumento Microsoft per la generazione di serializzatori XML
description: Panoramica dello strumento Microsoft per la generazione di serializzatori XML. Usare lo strumento per la generazione di serializzatori XML per generare un assembly di serializzazione XML per i tipi contenuti nel progetto.
author: mlacouture
ms.date: 01/19/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c3f1fcda8a8a6abc58d35bf37e51485bb3590fa3
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794637"
---
# <a name="using-microsoft-xml-serializer-generator-on-net-core"></a><span data-ttu-id="df3ee-104">Uso dello strumento Microsoft per la generazione di serializzatori XML in .NET Core</span><span class="sxs-lookup"><span data-stu-id="df3ee-104">Using Microsoft XML Serializer Generator on .NET Core</span></span>

<span data-ttu-id="df3ee-105">In questa esercitazione viene illustrato come usare lo strumento Microsoft per la generazione di serializzatori XML in un'applicazione .NET Core di C#.</span><span class="sxs-lookup"><span data-stu-id="df3ee-105">This tutorial teaches you how to use the Microsoft XML Serializer Generator in a C# .NET Core application.</span></span> <span data-ttu-id="df3ee-106">Nel corso di questa esercitazione verranno illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="df3ee-106">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="df3ee-107">Come creare un'app .NET Core</span><span class="sxs-lookup"><span data-stu-id="df3ee-107">How to create a .NET Core app</span></span>
> - <span data-ttu-id="df3ee-108">Come aggiungere un riferimento al pacchetto Microsoft.XmlSerializer.Generator</span><span class="sxs-lookup"><span data-stu-id="df3ee-108">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> - <span data-ttu-id="df3ee-109">Come modificare il file MyApp.cspro per aggiungere dipendenze</span><span class="sxs-lookup"><span data-stu-id="df3ee-109">How to edit your MyApp.csproj to add dependencies</span></span>
> - <span data-ttu-id="df3ee-110">Come aggiungere una classe e un oggetto XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="df3ee-110">How to add a class and an XmlSerializer</span></span>
> - <span data-ttu-id="df3ee-111">Come compilare ed eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="df3ee-111">How to build and run the application</span></span>

<span data-ttu-id="df3ee-112">Lo [strumento per la generazione di serializzatori XML (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) è la soluzione per .NET Framework, mentre il [pacchetto NuGet Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) è la soluzione equivalente per NET Core e .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="df3ee-112">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the equivalent for .NET Core and .NET Standard projects.</span></span> <span data-ttu-id="df3ee-113">Crea un assembly di serializzazione XML per tipi contenuti in un assembly per migliorare le prestazioni di avvio della serializzazione XML durante la serializzazione o deserializzazione di oggetti di questi tipi usando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="df3ee-113">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df3ee-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="df3ee-114">Prerequisites</span></span>

<span data-ttu-id="df3ee-115">Per completare questa esercitazione:</span><span class="sxs-lookup"><span data-stu-id="df3ee-115">To complete this tutorial:</span></span>

- <span data-ttu-id="df3ee-116">[.NET Core 2,1 SDK](https://dotnet.microsoft.com/download) o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="df3ee-116">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later.</span></span>
- <span data-ttu-id="df3ee-117">Editor di codice preferito.</span><span class="sxs-lookup"><span data-stu-id="df3ee-117">Your favorite code editor.</span></span>

> [!TIP]
> <span data-ttu-id="df3ee-118">È necessario installare un editor del codice?</span><span class="sxs-lookup"><span data-stu-id="df3ee-118">Need to install a code editor?</span></span> <span data-ttu-id="df3ee-119">Provare [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).</span><span class="sxs-lookup"><span data-stu-id="df3ee-119">Try [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)!</span></span>

## <a name="use-microsoft-xml-serializer-generator-in-a-net-core-console-application"></a><span data-ttu-id="df3ee-120">Usare lo strumento Microsoft per la generazione di serializzatori XML in un'applicazione console .NET Core</span><span class="sxs-lookup"><span data-stu-id="df3ee-120">Use Microsoft XML Serializer Generator in a .NET Core console application</span></span>

<span data-ttu-id="df3ee-121">Le istruzioni seguenti illustrano come usare lo strumento per la generazione di serializzatori XML in un'applicazione console .NET Core.</span><span class="sxs-lookup"><span data-stu-id="df3ee-121">The following instructions show you how to use XML Serializer Generator in a .NET Core console application.</span></span>

### <a name="create-a-net-core-console-application"></a><span data-ttu-id="df3ee-122">Creare un'applicazione console .NET Core</span><span class="sxs-lookup"><span data-stu-id="df3ee-122">Create a .NET Core console application</span></span>

<span data-ttu-id="df3ee-123">Aprire un prompt dei comandi e creare una cartella denominata *MyApp*.</span><span class="sxs-lookup"><span data-stu-id="df3ee-123">Open a command prompt and create a folder named *MyApp*.</span></span> <span data-ttu-id="df3ee-124">Passare alla cartella creata e digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="df3ee-124">Navigate to the folder you created and type the following command:</span></span>

```dotnetcli
dotnet new console
```

### <a name="add-a-reference-to-the-microsoftxmlserializergenerator-package-in-the-myapp-project"></a><span data-ttu-id="df3ee-125">Aggiungere un riferimento al pacchetto Microsoft.XmlSerializer.Generator nel progetto MyApp</span><span class="sxs-lookup"><span data-stu-id="df3ee-125">Add a reference to the Microsoft.XmlSerializer.Generator package in the MyApp project</span></span>

<span data-ttu-id="df3ee-126">Usare il [`dotnet add package`](../tools/dotnet-add-package.md) comando per aggiungere il riferimento nel progetto.</span><span class="sxs-lookup"><span data-stu-id="df3ee-126">Use the [`dotnet add package`](../tools/dotnet-add-package.md) command to add the reference in your project.</span></span>

<span data-ttu-id="df3ee-127">Digitare:</span><span class="sxs-lookup"><span data-stu-id="df3ee-127">Type:</span></span>

```dotnetcli
dotnet add package Microsoft.XmlSerializer.Generator -v 1.0.0
```

### <a name="verify-changes-to-myappcsproj-after-adding-the-package"></a><span data-ttu-id="df3ee-128">Verificare le modifiche a MyApp.csproj dopo aver aggiunto il pacchetto</span><span class="sxs-lookup"><span data-stu-id="df3ee-128">Verify changes to MyApp.csproj after adding the package</span></span>

<span data-ttu-id="df3ee-129">Prima di iniziare, aprire l'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="df3ee-129">Open your code editor and let's get started!</span></span> <span data-ttu-id="df3ee-130">Si lavorerà ancora dalla directory *MyApp* in cui è stata compilata l'app.</span><span class="sxs-lookup"><span data-stu-id="df3ee-130">We're still working from the *MyApp* directory we built the app in.</span></span>

<span data-ttu-id="df3ee-131">Aprire *MyApp.csproj* nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="df3ee-131">Open *MyApp.csproj* in your text editor.</span></span>

<span data-ttu-id="df3ee-132">Dopo aver eseguito [`dotnet add package`](../tools/dotnet-add-package.md) il comando, vengono aggiunte le righe seguenti al file di progetto *MyApp. csproj* :</span><span class="sxs-lookup"><span data-stu-id="df3ee-132">After running the [`dotnet add package`](../tools/dotnet-add-package.md) command, the following lines are added to your *MyApp.csproj* project file:</span></span>

 ```xml
 <ItemGroup>
    <PackageReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```

### <a name="add-another-itemgroup-section-for-net-core-cli-tool-support"></a><span data-ttu-id="df3ee-133">Aggiungere un'altra sezione denominata ItemGroup per il supporto dello strumento dell'interfaccia della riga di comando .NET Core</span><span class="sxs-lookup"><span data-stu-id="df3ee-133">Add another ItemGroup section for .NET Core CLI Tool support</span></span>

<span data-ttu-id="df3ee-134">Aggiungere le righe seguenti dopo la sezione `ItemGroup` analizzata:</span><span class="sxs-lookup"><span data-stu-id="df3ee-134">Add the following lines after the `ItemGroup` section that we inspected:</span></span>

 ```xml
 <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```

### <a name="add-a-class-in-the-application"></a><span data-ttu-id="df3ee-135">Aggiungere una classe nell'applicazione</span><span class="sxs-lookup"><span data-stu-id="df3ee-135">Add a class in the application</span></span>

<span data-ttu-id="df3ee-136">Aprire *Program.cs* nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="df3ee-136">Open *Program.cs* in your text editor.</span></span> <span data-ttu-id="df3ee-137">Aggiungere la classe denominata *MyClass* in *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="df3ee-137">Add the class named *MyClass* in *Program.cs*.</span></span>

```csharp
public class MyClass
{
   public int Value;
}
```

### <a name="create-an-xmlserializer-for-myclass"></a><span data-ttu-id="df3ee-138">Creare un oggetto `XmlSerializer` per MyClass</span><span class="sxs-lookup"><span data-stu-id="df3ee-138">Create an `XmlSerializer` for MyClass</span></span>

<span data-ttu-id="df3ee-139">Aggiungere la riga seguente in *Main* per creare un oggetto `XmlSerializer` per MyClass:</span><span class="sxs-lookup"><span data-stu-id="df3ee-139">Add the following line inside *Main* to create an `XmlSerializer` for MyClass:</span></span>

```csharp
var serializer = new System.Xml.Serialization.XmlSerializer(typeof(MyClass));
```

### <a name="build-and-run-the-application"></a><span data-ttu-id="df3ee-140">Compilare ed eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="df3ee-140">Build and run the application</span></span>

<span data-ttu-id="df3ee-141">All'interno della cartella *MyApp* eseguire l'applicazione tramite [`dotnet run`](../tools/dotnet-run.md). In automatico vengono caricati e usati i serializzatori generati in precedenza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="df3ee-141">Still within the *MyApp* folder, run the application via [`dotnet run`](../tools/dotnet-run.md) and it automatically loads and uses the pre-generated serializers at runtime.</span></span>

<span data-ttu-id="df3ee-142">Nella finestra di console digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="df3ee-142">Type the following command in your console window:</span></span>

```dotnetcli
dotnet run
```

> [!NOTE]
> <span data-ttu-id="df3ee-143">[`dotnet run`](../tools/dotnet-run.md)chiama [`dotnet build`](../tools/dotnet-build.md) per assicurarsi che le destinazioni di compilazione siano state compilate e `dotnet <assembly.dll>` quindi chiama per eseguire l'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="df3ee-143">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df3ee-144">I comandi e i passaggi illustrati in questa esercitazione per eseguire l'applicazione vengono usati solo durante la fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="df3ee-144">The commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="df3ee-145">Quando si è pronti a distribuire l'app, è opportuno esaminare le diverse [strategie di distribuzione](../deploying/index.md) per le app .NET Core e il comando [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="df3ee-145">Once you're ready to deploy your app, take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

<span data-ttu-id="df3ee-146">Se è stato eseguito tutto correttamente, un assembly denominato *MyApp.XmlSerializers.dll* viene generato nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="df3ee-146">If everything succeeds, an assembly named *MyApp.XmlSerializers.dll* is generated in the output folder.</span></span>

<span data-ttu-id="df3ee-147">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="df3ee-147">Congratulations!</span></span> <span data-ttu-id="df3ee-148">Sono state eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="df3ee-148">You have just:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="df3ee-149">Creazione di un'app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="df3ee-149">Created a .NET Core app.</span></span>
> - <span data-ttu-id="df3ee-150">Aggiunta di un riferimento al pacchetto Microsoft.XmlSerializer.Generator.</span><span class="sxs-lookup"><span data-stu-id="df3ee-150">Added a reference to the Microsoft.XmlSerializer.Generator package.</span></span>
> - <span data-ttu-id="df3ee-151">Modifica del file MyApp.cspro per l'aggiunta di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="df3ee-151">Edited your MyApp.csproj to add dependencies.</span></span>
> - <span data-ttu-id="df3ee-152">Aggiunta di una classe e un oggetto XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="df3ee-152">Added a class and an XmlSerializer.</span></span>
> - <span data-ttu-id="df3ee-153">Compilazione ed esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="df3ee-153">Built and ran the application.</span></span>

## <a name="related-resources"></a><span data-ttu-id="df3ee-154">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="df3ee-154">Related resources</span></span>

- [<span data-ttu-id="df3ee-155">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="df3ee-155">Introducing XML Serialization</span></span>](../../standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="df3ee-156">Come serializzare tramite XmlSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="df3ee-156">How to serialize using XmlSerializer (C#)</span></span>](../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
- [<span data-ttu-id="df3ee-157">Procedura: Serializzare tramite XmlSerializer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df3ee-157">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)

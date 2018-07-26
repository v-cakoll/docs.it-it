---
title: Distribuzione di app .NET Core con strumenti dell'interfaccia della riga di comando
description: Informazioni sulla distribuzione di app .NET Core con strumenti dell'interfaccia della riga di comando (CLI)
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.openlocfilehash: 7b009068422686442ebff83b9400c365f34a3154
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244751"
---
# <a name="deploying-net-core-apps-with-command-line-interface-cli-tools"></a><span data-ttu-id="7d860-103">Distribuire app .NET Core con strumenti dell'interfaccia della riga di comando (CLI)</span><span class="sxs-lookup"><span data-stu-id="7d860-103">Deploying .NET Core apps with command-line interface (CLI) tools</span></span>

<span data-ttu-id="7d860-104">È possibile distribuire un'app .NET Core come *distribuzione dipendente dal framework*, che include i file binari dell'applicazione ma dipende dalla presenza di .NET Core nel sistema di destinazione, oppure come *distribuzione autonoma*, che include l'applicazione e i file binari di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7d860-104">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and the .NET Core binaries.</span></span> <span data-ttu-id="7d860-105">Per una panoramica, vedere [Distribuzione di applicazioni .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="7d860-105">For an overview, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="7d860-106">Le sezioni seguenti illustrano come usare gli [strumenti dell'interfaccia della riga di comando .NET Core](../tools/index.md) per creare i tipi di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d860-106">The following sections show how to use [.NET Core command-line interface tools](../tools/index.md) to create the following kinds of deployments:</span></span>

- <span data-ttu-id="7d860-107">Distribuzione dipendente dal framework</span><span class="sxs-lookup"><span data-stu-id="7d860-107">Framework-dependent deployment</span></span>
- <span data-ttu-id="7d860-108">Distribuzione dipendente dal framework con dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="7d860-108">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="7d860-109">Distribuzione autonoma</span><span class="sxs-lookup"><span data-stu-id="7d860-109">Self-contained deployment</span></span>
- <span data-ttu-id="7d860-110">Distribuzione autonoma con dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="7d860-110">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="7d860-111">Con la riga di comando è possibile usare l'editor di codice desiderato.</span><span class="sxs-lookup"><span data-stu-id="7d860-111">When working from the command line, you can use a program editor of your choice.</span></span> <span data-ttu-id="7d860-112">Se l'editor di codice è [Visual Studio Code](https://code.visualstudio.com) è possibile aprire una console dei comandi all'interno dell'ambiente di Visual Studio Code selezionando **Visualizza** > **Terminale integrato**.</span><span class="sxs-lookup"><span data-stu-id="7d860-112">If your program editor is [Visual Studio Code](https://code.visualstudio.com), you can open a command console inside your Visual Studio Code environment by selecting **View** > **Integrated Terminal**.</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="7d860-113">Distribuzione dipendente dal framework</span><span class="sxs-lookup"><span data-stu-id="7d860-113">Framework-dependent deployment</span></span>

<span data-ttu-id="7d860-114">Una distribuzione dipendente dal framework senza dipendenze di terze parti richiede la compilazione, il testing e la pubblicazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="7d860-114">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="7d860-115">Il processo viene illustrato da un semplice esempio scritto in C#.</span><span class="sxs-lookup"><span data-stu-id="7d860-115">A simple example written in C# illustrates the process.</span></span> 

1. <span data-ttu-id="7d860-116">Creare una directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="7d860-116">Create a project directory.</span></span>

   <span data-ttu-id="7d860-117">Creare una directory per il progetto e impostarla come directory corrente.</span><span class="sxs-lookup"><span data-stu-id="7d860-117">Create a directory for your project and make it your current directory.</span></span>

1. <span data-ttu-id="7d860-118">Creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="7d860-118">Create the project.</span></span>

   <span data-ttu-id="7d860-119">Nella riga di comando digitare [dotnet new console](../tools/dotnet-new.md) per creare un nuovo progetto console C# in tale directory.</span><span class="sxs-lookup"><span data-stu-id="7d860-119">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="7d860-120">Aggiungere il codice sorgente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7d860-120">Add the application's source code.</span></span>

   <span data-ttu-id="7d860-121">Aprire il file *Program.cs* nell'editor e sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7d860-121">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="7d860-122">Questo codice richiede all'utente di immettere del testo e visualizza le singole parole immesse dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7d860-122">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="7d860-123">Usa l'espressione regolare `\w+` per separare le parole nel testo di input.</span><span class="sxs-lookup"><span data-stu-id="7d860-123">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. <span data-ttu-id="7d860-124">Aggiornare le dipendenze e gli strumenti del progetto.</span><span class="sxs-lookup"><span data-stu-id="7d860-124">Update the project's dependencies and tools.</span></span>
 
   <span data-ttu-id="7d860-125">Eseguire il comando [dotnet-restore](../tools/dotnet-restore.md) ([vedere la nota](#dotnet-restore-note)) per ripristinare le dipendenze specificate nel progetto.</span><span class="sxs-lookup"><span data-stu-id="7d860-125">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="7d860-126">Creare una build di debug dell'app.</span><span class="sxs-lookup"><span data-stu-id="7d860-126">Create a Debug build of your app.</span></span>

   <span data-ttu-id="7d860-127">Usare il comando [dotnet build](../tools/dotnet-build.md) per compilare l'applicazione o il comando [dotnet run](../tools/dotnet-run.md) per compilarla ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="7d860-127">Use the [dotnet build](../tools/dotnet-build.md) command to build your application or the [dotnet run](../tools/dotnet-run.md) command to build and run it.</span></span>

1. <span data-ttu-id="7d860-128">Distribuire l'app.</span><span class="sxs-lookup"><span data-stu-id="7d860-128">Deploy your app.</span></span>

   <span data-ttu-id="7d860-129">Dopo il debug e il test del programma, creare la distribuzione mediante il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7d860-129">After you've debugged and tested the program, create the deployment by using the following command:</span></span>

      ```console
      dotnet publish -f netcoreapp1.1 -c Release
      ```
   <span data-ttu-id="7d860-130">In questo modo viene creata una versione di rilascio dell'app anziché una versione di debug.</span><span class="sxs-lookup"><span data-stu-id="7d860-130">This creates a Release (rather than a Debug) version of your app.</span></span> <span data-ttu-id="7d860-131">I file risultanti vengono inseriti in una directory *publish* in una sottodirectory della directory *bin* del progetto.</span><span class="sxs-lookup"><span data-stu-id="7d860-131">The resulting files are placed in a directory named *publish*      that's in a subdirectory of your project's *bin* directory.</span></span>

   <span data-ttu-id="7d860-132">Insieme ai file dell'applicazione, il processo di pubblicazione genera un file del database di programma (con estensione pdb) che contiene le informazioni di debug relative all'app.</span><span class="sxs-lookup"><span data-stu-id="7d860-132">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="7d860-133">Il file è utile soprattutto per il debug delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="7d860-133">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="7d860-134">È possibile scegliere di non distribuirlo con i file dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7d860-134">You can choose not to distribute it with your application's files.</span></span> <span data-ttu-id="7d860-135">È tuttavia consigliabile salvarlo perché può risultare utile per il debug della build di rilascio dell'app.</span><span class="sxs-lookup"><span data-stu-id="7d860-135">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

   <span data-ttu-id="7d860-136">È possibile distribuire il set completo dei file dell'applicazione con il metodo desiderato.</span><span class="sxs-lookup"><span data-stu-id="7d860-136">You can deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="7d860-137">È ad esempio possibile inserire i file in un file zip, usare un semplice comando `copy` o distribuire i file con un pacchetto di installazione a scelta.</span><span class="sxs-lookup"><span data-stu-id="7d860-137">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

1. <span data-ttu-id="7d860-138">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="7d860-138">Run your app</span></span>

   <span data-ttu-id="7d860-139">Dopo aver completato l'installazione gli utenti possono eseguire l'applicazione usando il comando `dotnet` e fornendo il nome file dell'applicazione, ad esempio `dotnet fdd.dll`.</span><span class="sxs-lookup"><span data-stu-id="7d860-139">Once installed, users can execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

   <span data-ttu-id="7d860-140">Oltre ai file binari dell'applicazione, il programma di installazione deve aggregare il programma di installazione framework condiviso oppure rilevarlo come prerequisito durante l'installazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7d860-140">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="7d860-141">L'installazione del framework condiviso richiede l'accesso amministratore o alla radice.</span><span class="sxs-lookup"><span data-stu-id="7d860-141">Installation of the shared framework requires Administrator/root access.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="7d860-142">Distribuzione dipendente dal framework con dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="7d860-142">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="7d860-143">In una distribuzione dipendente dal framework con una o più dipendenze di terze parti, tali dipendenze devono essere disponibili per il progetto.</span><span class="sxs-lookup"><span data-stu-id="7d860-143">Deploying a framework-dependent deployment with one or more third-party dependencies requires that those dependencies be available to your project.</span></span> <span data-ttu-id="7d860-144">Prima dell'esecuzione del comando `dotnet restore` ([vedere la nota](#dotnet-restore-note)) è necessario eseguire due passaggi aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="7d860-144">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="7d860-145">Aggiungere riferimenti alle librerie di terze parti necessarie nella sezione `<ItemGroup>` del file *csproj*.</span><span class="sxs-lookup"><span data-stu-id="7d860-145">Add references to required third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="7d860-146">La sezione `<ItemGroup>` seguente contiene una dipendenza da [Json.NET](http://www.newtonsoft.com/json) come libreria di terze parti:</span><span class="sxs-lookup"><span data-stu-id="7d860-146">The following `<ItemGroup>` section contains a dependency on [Json.NET](http://www.newtonsoft.com/json) as a third-party library:</span></span>

      ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
      ```

1. <span data-ttu-id="7d860-147">Se non lo si è già fatto, scaricare il pacchetto NuGet contenente la dipendenza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="7d860-147">If you haven't already, download the NuGet package containing the third-party dependency.</span></span> <span data-ttu-id="7d860-148">Per scaricare il pacchetto, eseguire il comando `dotnet restore` ([vedere la nota](#dotnet-restore-note)) dopo l'aggiunta della dipendenza.</span><span class="sxs-lookup"><span data-stu-id="7d860-148">To download the package, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="7d860-149">Poiché la dipendenza viene risolta dalla cache NuGet locale in fase di pubblicazione, deve essere disponibile nel sistema.</span><span class="sxs-lookup"><span data-stu-id="7d860-149">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="7d860-150">Si noti che la portabilità di una distribuzione dipendente dal framework con dipendenze di terze parti corrisponde esattamente alla portabilità delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="7d860-150">Note that a framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="7d860-151">Se ad esempio una libreria di terze parti supporta solo macOS, l'app non è portabile in sistemi Windows.</span><span class="sxs-lookup"><span data-stu-id="7d860-151">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="7d860-152">Questa situazione si verifica se la dipendenza di terze parti stessa dipende da codice nativo.</span><span class="sxs-lookup"><span data-stu-id="7d860-152">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="7d860-153">Un buon esempio è il [server Kestrel](/aspnet/core/fundamentals/servers/kestrel), che richiede una dipendenza nativa da [libuv](https://github.com/libuv/libuv).</span><span class="sxs-lookup"><span data-stu-id="7d860-153">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="7d860-154">Quando viene creata una distribuzione dipendente dal framework per un'applicazione con questo tipo di dipendenze di terze parti, l'output pubblicato contiene una cartella per ogni [identificatore di runtime (RID)](../rid-catalog.md) supportato dalla dipendenza nativa (e presente nel relativo pacchetto NuGet).</span><span class="sxs-lookup"><span data-stu-id="7d860-154">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <a name="simpleSelf"></a> <span data-ttu-id="7d860-155">Distribuzione autonoma senza dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="7d860-155">Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="7d860-156">Una distribuzione autonoma senza dipendenze di terze parti comporta la creazione del progetto, la modifica del file *csproj*, la compilazione, il test e la pubblicazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="7d860-156">Deploying a self-contained deployment without third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="7d860-157">Il processo viene illustrato da un semplice esempio scritto in C#.</span><span class="sxs-lookup"><span data-stu-id="7d860-157">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="7d860-158">L'esempio seguente visualizza come creare una distribuzione autonoma con l'[utilità dotnet](../tools/dotnet.md) dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="7d860-158">The example shows how to create a self-contained deployment using the [dotnet utility](../tools/dotnet.md) from the command line.</span></span>

1. <span data-ttu-id="7d860-159">Creare una directory per il progetto.</span><span class="sxs-lookup"><span data-stu-id="7d860-159">Create a directory for the project.</span></span>

   <span data-ttu-id="7d860-160">Creare una directory per il progetto e impostarla come directory corrente.</span><span class="sxs-lookup"><span data-stu-id="7d860-160">Create a directory for your project, and make it your current directory.</span></span>

1. <span data-ttu-id="7d860-161">Creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="7d860-161">Create the project.</span></span>

   <span data-ttu-id="7d860-162">Nella riga di comando digitare [dotnet new console](../tools/dotnet-new.md) per creare un nuovo progetto console C# in tale directory.</span><span class="sxs-lookup"><span data-stu-id="7d860-162">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="7d860-163">Aggiungere il codice sorgente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7d860-163">Add the application's source code.</span></span>

   <span data-ttu-id="7d860-164">Aprire il file *Program.cs* nell'editor e sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7d860-164">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="7d860-165">Questo codice richiede all'utente di immettere del testo e visualizza le singole parole immesse dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7d860-165">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="7d860-166">Usa l'espressione regolare `\w+` per separare le parole nel testo di input.</span><span class="sxs-lookup"><span data-stu-id="7d860-166">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. <span data-ttu-id="7d860-167">Definire le piattaforme di destinazione per l'app.</span><span class="sxs-lookup"><span data-stu-id="7d860-167">Define the platforms that your app will target.</span></span>

   <span data-ttu-id="7d860-168">Creare un tag `<RuntimeIdentifiers>` nella sezione `<PropertyGroup>` del file *csproj* che definisce le piattaforme di destinazione dell'app e specificare l'identificatore di runtime di ogni piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7d860-168">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets and specify the runtime identifier (RID) for each platform that you target.</span></span> <span data-ttu-id="7d860-169">Si noti che è inoltre necessario aggiungere un punto e virgola per separare i RID.</span><span class="sxs-lookup"><span data-stu-id="7d860-169">Note that you also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="7d860-170">Per un elenco degli identificatori di runtime, vedere [Runtime IDentifier catalog](../rid-catalog.md) (Catalogo degli identificatori di runtime).</span><span class="sxs-lookup"><span data-stu-id="7d860-170">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span> 

   <span data-ttu-id="7d860-171">Ad esempio, la sezione `<PropertyGroup>` seguente indica che l'app viene eseguita in sistemi operativi Windows 10 a 64 bit e nel sistema operativo OS X versione 10.11 a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="7d860-171">For example, the following `<PropertyGroup>` section indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

     ```xml
     <PropertyGroup>
         <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
     </PropertyGroup>
     ```

   <span data-ttu-id="7d860-172">Si noti che l'elemento `<RuntimeIdentifiers>` può essere visualizzato in qualsiasi `<PropertyGroup>` nel file *csproj*.</span><span class="sxs-lookup"><span data-stu-id="7d860-172">Note that the `<RuntimeIdentifiers>` element can appear in any `<PropertyGroup>` in your *csproj* file.</span></span> <span data-ttu-id="7d860-173">Un file di esempio *csproj* completo è disponibile più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="7d860-173">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="7d860-174">Aggiornare le dipendenze e gli strumenti del progetto.</span><span class="sxs-lookup"><span data-stu-id="7d860-174">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="7d860-175">Eseguire il comando [dotnet-restore](../tools/dotnet-restore.md) ([vedere la nota](#dotnet-restore-note)) per ripristinare le dipendenze specificate nel progetto.</span><span class="sxs-lookup"><span data-stu-id="7d860-175">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="7d860-176">Creare una build di debug dell'app.</span><span class="sxs-lookup"><span data-stu-id="7d860-176">Create a Debug build of your app.</span></span>

   <span data-ttu-id="7d860-177">Dalla riga di comando usare il comando [dotnet build](../tools/dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="7d860-177">From the command line, use the [dotnet build](../tools/dotnet-build.md) command.</span></span>

1. <span data-ttu-id="7d860-178">Dopo aver eseguito il debug e il test del programma creare i file da distribuire con l'app per ogni piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7d860-178">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="7d860-179">Usare il comando `dotnet publish` per entrambe le piattaforme di destinazione come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7d860-179">Use the `dotnet publish` command for both target platforms as follows:</span></span>

      ```console
      dotnet publish -c Release -r win10-x64
      dotnet publish -c Release -r osx.10.11-x64
      ```

   <span data-ttu-id="7d860-180">In questo modo, viene creata una versione di rilascio dell'app per ogni piattaforma di destinazione anziché una versione di debug.</span><span class="sxs-lookup"><span data-stu-id="7d860-180">This creates a Release (rather than a Debug) version of your app for each target platform.</span></span> <span data-ttu-id="7d860-181">I file risultanti vengono inseriti in una directory *publish* in una sottodirectory della directory *.\bin\Release\netcoreapp1.1\<runtime_identifier>* del progetto.</span><span class="sxs-lookup"><span data-stu-id="7d860-181">The resulting files are placed in a subdirectory named *publish* that's in a subdirectory of your project's *.\bin\Release\netcoreapp1.1\<runtime_identifier>* subdirectory.</span></span> <span data-ttu-id="7d860-182">Si noti che ogni sottodirectory contiene il set completo di file (i file dell'app e tutti i file di .NET Core) necessario per avviare l'app.</span><span class="sxs-lookup"><span data-stu-id="7d860-182">Note that each subdirectory contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="7d860-183">Insieme ai file dell'applicazione, il processo di pubblicazione genera un file del database di programma (con estensione pdb) che contiene le informazioni di debug relative all'app.</span><span class="sxs-lookup"><span data-stu-id="7d860-183">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="7d860-184">Il file è utile soprattutto per il debug delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="7d860-184">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="7d860-185">È possibile scegliere di non includerlo nel pacchetto dei file dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7d860-185">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="7d860-186">È tuttavia consigliabile salvarlo perché può risultare utile per il debug della build di rilascio dell'app.</span><span class="sxs-lookup"><span data-stu-id="7d860-186">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="7d860-187">Distribuire i file pubblicati con il metodo desiderato.</span><span class="sxs-lookup"><span data-stu-id="7d860-187">Deploy the published files in any way you like.</span></span> <span data-ttu-id="7d860-188">È ad esempio possibile inserire i file in un file zip, usare un semplice comando `copy` o distribuire i file con un pacchetto di installazione a scelta.</span><span class="sxs-lookup"><span data-stu-id="7d860-188">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="7d860-189">Di seguito è riportato il file *csproj* completo per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="7d860-189">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="7d860-190">Distribuzione autonoma con dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="7d860-190">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="7d860-191">Una distribuzione autonoma con una o più dipendenze di terze parti comporta l'aggiunta delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="7d860-191">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="7d860-192">Prima dell'esecuzione del comando `dotnet restore` ([vedere la nota](#dotnet-restore-note)) è necessario eseguire due passaggi aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="7d860-192">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="7d860-193">Aggiungere i riferimenti alle eventuali librerie di terze parti alla sezione `<ItemGroup>` del file *csproj*.</span><span class="sxs-lookup"><span data-stu-id="7d860-193">Add references to any third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="7d860-194">La sezione `<ItemGroup>` seguente usa Json.NET come libreria di terze parti.</span><span class="sxs-lookup"><span data-stu-id="7d860-194">The following `<ItemGroup>` section uses Json.NET as a third-party library.</span></span>

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
    ```

1. <span data-ttu-id="7d860-195">Se non lo si è già fatto, scaricare nel sistema il pacchetto NuGet contenente la dipendenza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="7d860-195">If you haven't already, download the NuGet package containing the third-party dependency to your system.</span></span> <span data-ttu-id="7d860-196">Per rendere la dipendenza disponibile per l'app, eseguire il comando `dotnet restore` ([vedere la nota](#dotnet-restore-note)) dopo l'aggiunta della dipendenza.</span><span class="sxs-lookup"><span data-stu-id="7d860-196">To make the dependency available to your app, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="7d860-197">Poiché la dipendenza viene risolta dalla cache NuGet locale in fase di pubblicazione, deve essere disponibile nel sistema.</span><span class="sxs-lookup"><span data-stu-id="7d860-197">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="7d860-198">Di seguito è riportato il file *csproj* completo per questo progetto:</span><span class="sxs-lookup"><span data-stu-id="7d860-198">The following is the complete *csproj* file for this project:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="7d860-199">Quando si distribuisce l'applicazione, anche le dipendenze di terze parti usate nell'app sono contenute nei file dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7d860-199">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="7d860-200">Non è necessario che le librerie di terze parti siano già presenti nel sistema in cui viene eseguita l'app.</span><span class="sxs-lookup"><span data-stu-id="7d860-200">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="7d860-201">Si noti che è possibile distribuire una distribuzione autonoma solo con una libreria di terze parti alle piattaforme supportate da tale libreria.</span><span class="sxs-lookup"><span data-stu-id="7d860-201">Note that you can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="7d860-202">Il caso è simile alla presenza di dipendenze di terze parti con dipendenze native in una distribuzione dipendente dal framework, nella quale le dipendenze native devono essere compatibili con la piattaforma in cui viene distribuita l'app.</span><span class="sxs-lookup"><span data-stu-id="7d860-202">This is similar to having third-party dependencies with native dependencies in a framework-dependent deployment, where the native dependencies must be compatible with the platform to which the app is deployed.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

# <a name="see-also"></a><span data-ttu-id="7d860-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d860-203">See also</span></span>

<span data-ttu-id="7d860-204">[Distribuzione di applicazioni .NET Core](index.md) </span><span class="sxs-lookup"><span data-stu-id="7d860-204">[.NET Core Application Deployment](index.md) </span></span>  
[<span data-ttu-id="7d860-205">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="7d860-205">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)   


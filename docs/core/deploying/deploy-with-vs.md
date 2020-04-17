---
title: Distribuire app .NET Core con Visual Studio
description: Informazioni su come distribuire un'app .NET Core con Visual Studio.
ms.date: 09/03/2018
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: f2299ac807c845dab482306cc4c710560bb7f1e7
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607862"
---
# <a name="deploy-net-core-apps-with-visual-studio"></a><span data-ttu-id="337d0-103">Distribuire app .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="337d0-103">Deploy .NET Core apps with Visual Studio</span></span>

<span data-ttu-id="337d0-104">È possibile distribuire un'app .NET Core come *distribuzione dipendente dal framework*, che include i file binari dell'applicazione ma dipende dalla presenza di .NET Core nel sistema di destinazione oppure come *distribuzione autonoma*, che include l'applicazione e i file binari di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="337d0-104">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and .NET Core binaries.</span></span> <span data-ttu-id="337d0-105">Per una panoramica della distribuzione di applicazioni .NET Core, vedere [Distribuzione di applicazioni .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="337d0-105">For an overview of .NET Core application deployment, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="337d0-106">Le sezioni seguenti illustrano l'uso di Microsoft Visual Studio per creare i tipi di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="337d0-106">The following sections show how to use Microsoft Visual Studio to create the following kinds of deployments:</span></span>

- <span data-ttu-id="337d0-107">Distribuzione dipendente dal framework</span><span class="sxs-lookup"><span data-stu-id="337d0-107">Framework-dependent deployment</span></span>
- <span data-ttu-id="337d0-108">Distribuzione dipendente dal framework con dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="337d0-108">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="337d0-109">Distribuzione autonoma</span><span class="sxs-lookup"><span data-stu-id="337d0-109">Self-contained deployment</span></span>
- <span data-ttu-id="337d0-110">Distribuzione autonoma con dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="337d0-110">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="337d0-111">Per informazioni sull'utilizzo di Visual Studio per sviluppare applicazioni .NET Core, vedere [Dipendenze e requisiti di .NET Core](../install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="337d0-111">For information on using Visual Studio to develop .NET Core applications, see [.NET Core dependencies and requirements](../install/dependencies.md?pivots=os-windows).</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="337d0-112">Distribuzione dipendente dal framework</span><span class="sxs-lookup"><span data-stu-id="337d0-112">Framework-dependent deployment</span></span>

<span data-ttu-id="337d0-113">Una distribuzione dipendente dal framework senza dipendenze di terze parti richiede la compilazione, il testing e la pubblicazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-113">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="337d0-114">Il processo viene illustrato da un semplice esempio scritto in C#.</span><span class="sxs-lookup"><span data-stu-id="337d0-114">A simple example written in C# illustrates the process.</span></span>

1. <span data-ttu-id="337d0-115">Creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="337d0-115">Create the project.</span></span>

   <span data-ttu-id="337d0-116">Selezionare **File** > **nuovo** > **progetto**.</span><span class="sxs-lookup"><span data-stu-id="337d0-116">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="337d0-117">Nella finestra di dialogo **Nuovo progetto** espandere le categorie di progetti del linguaggio (C# o Visual Basic) nel riquadro dei tipi di progetti **Installati**, scegliere il modello **.NET Core** e selezionare il modello **Console App (.NET Core)** (App console (.NET Core)) nel riquadro centrale.</span><span class="sxs-lookup"><span data-stu-id="337d0-117">In the **New Project** dialog, expand your language's (C# or Visual Basic) project categories in the **Installed** project types pane, choose **.NET Core**, and then select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="337d0-118">Immettere un nome di progetto, ad esempio "FDD", nella casella di testo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="337d0-118">Enter a project name, such as "FDD", in the **Name** text box.</span></span> <span data-ttu-id="337d0-119">Selezionare il pulsante **OK.**</span><span class="sxs-lookup"><span data-stu-id="337d0-119">Select the **OK** button.</span></span>

1. <span data-ttu-id="337d0-120">Aggiungere il codice sorgente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-120">Add the application's source code.</span></span>

   <span data-ttu-id="337d0-121">Aprire il file *Program.cs* o *Program.vb* nell'editor e sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="337d0-121">Open the *Program.cs* or *Program.vb* file in the editor and replace the autogenerated code with the following code.</span></span> <span data-ttu-id="337d0-122">Questo codice richiede all'utente di immettere del testo e visualizza le singole parole immesse dall'utente.</span><span class="sxs-lookup"><span data-stu-id="337d0-122">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="337d0-123">Usa l'espressione regolare `\w+` per separare le parole nel testo di input.</span><span class="sxs-lookup"><span data-stu-id="337d0-123">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]

1. <span data-ttu-id="337d0-124">Creare una build di debug dell'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-124">Create a Debug build of your app.</span></span>

   <span data-ttu-id="337d0-125">Selezionare **Compila** > **soluzione**.</span><span class="sxs-lookup"><span data-stu-id="337d0-125">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="337d0-126">È inoltre possibile compilare ed eseguire la build di debug dell'applicazione selezionando **Debug** > **Start Debugging**debug .</span><span class="sxs-lookup"><span data-stu-id="337d0-126">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="337d0-127">Distribuire l'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-127">Deploy your app.</span></span>

   <span data-ttu-id="337d0-128">Dopo aver eseguito il debug e il test del programma, creare i file da distribuire con l'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-128">After you've debugged and tested the program, create the files to be deployed with your app.</span></span> <span data-ttu-id="337d0-129">Per la pubblicazione da Visual Studio eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="337d0-129">To publish from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="337d0-130">Modificare la configurazione della soluzione da **Debug** a **Release** sulla barra degli strumenti, per creare una versione di rilascio dell'app (invece di una versione di debug).</span><span class="sxs-lookup"><span data-stu-id="337d0-130">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="337d0-131">Fare clic con il pulsante destro del mouse sul progetto (non sulla soluzione) in **Esplora soluzioni** e selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="337d0-131">Right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

      1. <span data-ttu-id="337d0-132">Nella scheda **Pubblica** selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="337d0-132">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="337d0-133">I file che costituiscono l'applicazione vengono salvati nel file system locale.</span><span class="sxs-lookup"><span data-stu-id="337d0-133">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="337d0-134">La scheda **Pubblica** ora visualizza un unico profilo **FolderProfile**.</span><span class="sxs-lookup"><span data-stu-id="337d0-134">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="337d0-135">Le impostazioni di configurazione del profilo vengono visualizzate nella sezione **Riepilogo** della scheda.</span><span class="sxs-lookup"><span data-stu-id="337d0-135">The profile's configuration settings are shown in the **Summary** section of the tab.</span></span>

   <span data-ttu-id="337d0-136">I file risultanti vengono inseriti in una directory di nome `Publish` in Windows e `publish` nei sistemi Unix, che è una sottodirectory della directory *.\bin\release\netcoreapp2.1* del progetto.</span><span class="sxs-lookup"><span data-stu-id="337d0-136">The resulting files are placed in a directory named `Publish` on Windows and `publish` on Unix systems that is in a subdirectory of your project's *.\bin\release\netcoreapp2.1* subdirectory.</span></span>

<span data-ttu-id="337d0-137">Insieme ai file dell'applicazione, il processo di pubblicazione genera un file del database di programma (con estensione pdb) che contiene le informazioni di debug relative all'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-137">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="337d0-138">Il file è utile soprattutto per il debug delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="337d0-138">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="337d0-139">È possibile scegliere di non includerlo nel pacchetto dei file dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-139">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="337d0-140">È tuttavia consigliabile salvarlo perché può risultare utile per il debug della build di rilascio dell'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-140">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="337d0-141">Distribuire il set completo dei file dell'applicazione con il metodo desiderato.</span><span class="sxs-lookup"><span data-stu-id="337d0-141">Deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="337d0-142">È ad esempio possibile inserire i file in un file zip, usare un semplice comando `copy` o distribuire i file con un pacchetto di installazione a scelta.</span><span class="sxs-lookup"><span data-stu-id="337d0-142">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span> <span data-ttu-id="337d0-143">Dopo aver completato l'installazione gli utenti possono eseguire l'applicazione usando il comando `dotnet` e fornendo il nome file dell'applicazione, ad esempio `dotnet fdd.dll`.</span><span class="sxs-lookup"><span data-stu-id="337d0-143">Once installed, users can then execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

<span data-ttu-id="337d0-144">Oltre ai file binari dell'applicazione, il programma di installazione deve aggregare il programma di installazione framework condiviso oppure rilevarlo come prerequisito durante l'installazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-144">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="337d0-145">L'installazione del framework condiviso richiede l'accesso amministratore o alla radice perché è a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="337d0-145">Installation of the shared framework requires Administrator/root access since it is machine-wide.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="337d0-146">Distribuzione dipendente dal framework con dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="337d0-146">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="337d0-147">In una distribuzione dipendente dal framework con una o più dipendenze di terze parti, le dipendenze devono essere disponibili per il progetto.</span><span class="sxs-lookup"><span data-stu-id="337d0-147">Deploying a framework-dependent deployment with one or more third-party dependencies requires that any dependencies be available to your project.</span></span> <span data-ttu-id="337d0-148">Prima della compilazione dell'app è necessario eseguire i passaggi aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="337d0-148">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="337d0-149">Usare **Gestione pacchetti NuGet** per aggiungere al progetto un riferimento a un pacchetto NuGet e per installare il pacchetto se non è già disponibile nel sistema.</span><span class="sxs-lookup"><span data-stu-id="337d0-149">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="337d0-150">Per aprire Gestione pacchetti, selezionare **Strumenti** > **NuGet Gestione** > pacchetti**Gestisci pacchetti NuGet per soluzione**.</span><span class="sxs-lookup"><span data-stu-id="337d0-150">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="337d0-151">Verificare che le dipendenze di `Newtonsoft.Json`terze parti ( ad esempio, ) siano installate nel sistema e, in caso contrario, installarle.</span><span class="sxs-lookup"><span data-stu-id="337d0-151">Confirm that your third-party dependencies (for example, `Newtonsoft.Json`) are installed on your system and, if they aren't, install them.</span></span> <span data-ttu-id="337d0-152">La scheda **Installati** elenca i pacchetti NuGet installati nel sistema.</span><span class="sxs-lookup"><span data-stu-id="337d0-152">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="337d0-153">Se `Newtonsoft.Json` non è presente nell'elenco, selezionare la scheda **Sfoglia** e immettere "Newtonsoft.Json" nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="337d0-153">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="337d0-154">Selezionare `Newtonsoft.Json`, selezionare il progetto nel riquadro destro e quindi selezionare **Installa**.</span><span class="sxs-lookup"><span data-stu-id="337d0-154">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="337d0-155">Se `Newtonsoft.Json` è già installato nel sistema aggiungerlo al progetto selezionando il progetto stesso nel riquadro destro della scheda **Gestisci i pacchetti per la soluzione**.</span><span class="sxs-lookup"><span data-stu-id="337d0-155">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of the **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="337d0-156">Una distribuzione dipendente dal framework con dipendenze di terze parti è portabile solo come le dipendenze di terze parti.</span><span class="sxs-lookup"><span data-stu-id="337d0-156">A framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="337d0-157">Se ad esempio una libreria di terze parti supporta solo macOS, l'app non è portabile in sistemi Windows.</span><span class="sxs-lookup"><span data-stu-id="337d0-157">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="337d0-158">Questa situazione si verifica se la dipendenza di terze parti stessa dipende da codice nativo.</span><span class="sxs-lookup"><span data-stu-id="337d0-158">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="337d0-159">Un buon esempio è il [server Kestrel](/aspnet/core/fundamentals/servers/kestrel), che richiede una dipendenza nativa da [libuv](https://github.com/libuv/libuv).</span><span class="sxs-lookup"><span data-stu-id="337d0-159">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="337d0-160">Quando viene creata una distribuzione dipendente dal framework per un'applicazione con questo tipo di dipendenze di terze parti, l'output pubblicato contiene una cartella per ogni [identificatore di runtime (RID)](../rid-catalog.md) supportato dalla dipendenza nativa (e presente nel relativo pacchetto NuGet).</span><span class="sxs-lookup"><span data-stu-id="337d0-160">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <a name="self-contained-deployment-without-third-party-dependencies"></a><a name="simpleSelf"></a> <span data-ttu-id="337d0-161">Distribuzione autonoma senza dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="337d0-161">Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="337d0-162">La pubblicazione di una distribuzione autonoma senza dipendenze di terze parti comporta la creazione del progetto, la modifica del file *csproj*, la compilazione, il test e la pubblicazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-162">Deploying a self-contained deployment with no third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="337d0-163">Il processo viene illustrato da un semplice esempio scritto in C#.</span><span class="sxs-lookup"><span data-stu-id="337d0-163">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="337d0-164">Creare, codificare e testare inizialmente il progetto come nel caso di una distribuzione dipendente dal framework:</span><span class="sxs-lookup"><span data-stu-id="337d0-164">You begin by creating, coding, and testing your project just as you would a framework-dependent deployment:</span></span>

1. <span data-ttu-id="337d0-165">Creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="337d0-165">Create the project.</span></span>

   <span data-ttu-id="337d0-166">Selezionare **File** > **nuovo** > **progetto**.</span><span class="sxs-lookup"><span data-stu-id="337d0-166">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="337d0-167">Nella finestra di dialogo **Nuovo progetto** espandere le categorie di progetti del linguaggio (C# o Visual Basic) nel riquadro dei tipi di progetti **Installati**, scegliere il modello **.NET Core** e selezionare il modello **Console App (.NET Core)** (App console (.NET Core)) nel riquadro centrale.</span><span class="sxs-lookup"><span data-stu-id="337d0-167">In the **New Project** dialog, expand your language's (C# or Visual Basic) project categories in the **Installed** project types pane, choose **.NET Core**, and then select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="337d0-168">Immettere un nome di progetto, ad esempio "SCD" nella casella di testo **Nome**, quindi selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="337d0-168">Enter a project name, such as "SCD", in the **Name** text box, and select the **OK** button.</span></span>

1. <span data-ttu-id="337d0-169">Aggiungere il codice sorgente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-169">Add the application's source code.</span></span>

   <span data-ttu-id="337d0-170">Aprire il *file Program.cs* o *Program.vb* nell'editor e sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="337d0-170">Open the *Program.cs* or *Program.vb* file in your editor, and replace the autogenerated code with the following code.</span></span> <span data-ttu-id="337d0-171">Questo codice richiede all'utente di immettere del testo e visualizza le singole parole immesse dall'utente.</span><span class="sxs-lookup"><span data-stu-id="337d0-171">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="337d0-172">Usa l'espressione regolare `\w+` per separare le parole nel testo di input.</span><span class="sxs-lookup"><span data-stu-id="337d0-172">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]

1. <span data-ttu-id="337d0-173">Specificare se si intende usare la modalità invariante della globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-173">Determine whether you want to use globalization invariant mode.</span></span>

   <span data-ttu-id="337d0-174">In particolare, se l'app è destinata a Linux, è possibile ridurre le dimensioni totali della distribuzione sfruttando la [modalità invariante della globalizzazione](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="337d0-174">Particularly if your app targets Linux, you can reduce the total size of your deployment by taking advantage of [globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span> <span data-ttu-id="337d0-175">La modalità invariante della globalizzazione è utile per le applicazioni che non sono compatibili a livello globale e possono usare le convenzioni di formattazione, le convenzioni sulla combinazione di maiuscole e minuscole, il confronto tra stringhe e l'ordinamento delle [impostazioni cultura invarianti](xref:System.Globalization.CultureInfo.InvariantCulture).</span><span class="sxs-lookup"><span data-stu-id="337d0-175">Globalization invariant mode is useful for applications that are not globally aware and that can use the formatting conventions, casing conventions, and string comparison and sort order of the [invariant culture](xref:System.Globalization.CultureInfo.InvariantCulture).</span></span>

   <span data-ttu-id="337d0-176">Per abilitare la modalità invariante fare clic con il pulsante destro del mouse sul progetto (non sulla soluzione) in **Esplora soluzioni** e selezionare **Modifica SCD.csproj** o **Modifica SCD.vbproj**.</span><span class="sxs-lookup"><span data-stu-id="337d0-176">To enable invariant mode, right-click on your project (not the solution) in **Solution Explorer**, and select **Edit SCD.csproj** or **Edit SCD.vbproj**.</span></span> <span data-ttu-id="337d0-177">Aggiungere al file le seguenti righe evidenziate:</span><span class="sxs-lookup"><span data-stu-id="337d0-177">Then add the following highlighted lines to the file:</span></span>

   [!code-xml[globalization-invariant-mode](~/samples/snippets/core/deploying/xml/invariant.csproj?highlight=6-8)]

1. <span data-ttu-id="337d0-178">Creare una build di debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-178">Create a Debug build of your application.</span></span>

   <span data-ttu-id="337d0-179">Selezionare **Compila** > **soluzione**.</span><span class="sxs-lookup"><span data-stu-id="337d0-179">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="337d0-180">È inoltre possibile compilare ed eseguire la build di debug dell'applicazione selezionando **Debug** > **Start Debugging**debug .</span><span class="sxs-lookup"><span data-stu-id="337d0-180">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span> <span data-ttu-id="337d0-181">Questo passaggio di debug consente di identificare i problemi dell'applicazione quando è in esecuzione sulla piattaforma host.</span><span class="sxs-lookup"><span data-stu-id="337d0-181">This debugging step lets you identify problems with your application when it's running on your host platform.</span></span> <span data-ttu-id="337d0-182">È tuttavia necessario testarla sulle singole piattaforme di destinazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-182">You still will have to test it on each of your target platforms.</span></span>

   <span data-ttu-id="337d0-183">Se è stata abilitata la modalità invariante della globalizzazione, verificare soprattutto se l'assenza di dati dipendenti dalle impostazioni cultura sia adatta per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-183">If you've enabled globalization invariant mode, be particularly sure to test whether the absence of culture-sensitive data is suitable for your application.</span></span>

<span data-ttu-id="337d0-184">Dopo aver terminato il debug, è possibile pubblicare la distribuzione autonoma:</span><span class="sxs-lookup"><span data-stu-id="337d0-184">Once you've finished debugging, you can publish your self-contained deployment:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="visual-studio-156-and-earlier"></a>[<span data-ttu-id="337d0-185">Visual Studio 15.6 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="337d0-185">Visual Studio 15.6 and earlier</span></span>](#tab/vs156)

<span data-ttu-id="337d0-186">Dopo aver eseguito il debug e il test del programma creare i file da distribuire con l'app per ogni piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-186">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

<span data-ttu-id="337d0-187">Per pubblicare l'app da Visual Studio eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="337d0-187">To publish your app from Visual Studio, do the following:</span></span>

1. <span data-ttu-id="337d0-188">Definire le piattaforme di destinazione per l'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-188">Define the platforms that your app will target.</span></span>

   1. <span data-ttu-id="337d0-189">Fare clic con il pulsante destro del mouse sul progetto (non sulla soluzione) in **Esplora soluzioni** e selezionare **Modifica SCD.csproj**.</span><span class="sxs-lookup"><span data-stu-id="337d0-189">Right-click on your project (not the solution) in **Solution Explorer** and select **Edit SCD.csproj**.</span></span>

   1. <span data-ttu-id="337d0-190">Creare un tag `<RuntimeIdentifiers>` nella sezione `<PropertyGroup>` del file *csproj* che definisce le piattaforme di destinazione dell'app e specifica l'identificatore di runtime di ogni piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-190">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets, and specify the runtime identifier (RID) of each platform that you target.</span></span> <span data-ttu-id="337d0-191">È inoltre necessario aggiungere un punto e virgola per separare i RID.</span><span class="sxs-lookup"><span data-stu-id="337d0-191">You also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="337d0-192">Per un elenco degli identificatori di runtime, vedere [Runtime IDentifier catalog](../rid-catalog.md) (Catalogo degli identificatori di runtime).</span><span class="sxs-lookup"><span data-stu-id="337d0-192">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span>

   <span data-ttu-id="337d0-193">L'esempio seguente indica che l'app viene eseguita in sistemi operativi Windows 10 a 64 bit e nel sistema operativo OS X versione 10.11 a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="337d0-193">For example, the following example indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

   ```xml
   <PropertyGroup>
      <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
   </PropertyGroup>
   ```

   <span data-ttu-id="337d0-194">L'elemento `<RuntimeIdentifiers>` può `<PropertyGroup>` andare in qualsiasi che avete nel file *csproj.*</span><span class="sxs-lookup"><span data-stu-id="337d0-194">The `<RuntimeIdentifiers>` element can go into any `<PropertyGroup>` that you have in your *csproj* file.</span></span> <span data-ttu-id="337d0-195">Un file di esempio *csproj* completo è disponibile più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="337d0-195">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="337d0-196">Pubblicare l'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-196">Publish your app.</span></span>

   <span data-ttu-id="337d0-197">Dopo aver eseguito il debug e il test del programma creare i file da distribuire con l'app per ogni piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-197">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="337d0-198">Per pubblicare l'app da Visual Studio eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="337d0-198">To publish your app from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="337d0-199">Modificare la configurazione della soluzione da **Debug** a **Release** sulla barra degli strumenti, per creare una versione di rilascio dell'app (invece di una versione di debug).</span><span class="sxs-lookup"><span data-stu-id="337d0-199">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="337d0-200">Fare clic con il pulsante destro del mouse sul progetto (non sulla soluzione) in **Esplora soluzioni** e selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="337d0-200">Right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

      1. <span data-ttu-id="337d0-201">Nella scheda **Pubblica** selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="337d0-201">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="337d0-202">I file che costituiscono l'applicazione vengono salvati nel file system locale.</span><span class="sxs-lookup"><span data-stu-id="337d0-202">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="337d0-203">La scheda **Pubblica** ora visualizza un unico profilo **FolderProfile**.</span><span class="sxs-lookup"><span data-stu-id="337d0-203">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="337d0-204">Le impostazioni di configurazione del profilo vengono visualizzate nella sezione **Riepilogo** della scheda **Target Location** **Runtime** di destinazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-204">The profile's configuration settings are shown in the **Summary** section of the tab. **Target Runtime** identifies which runtime has been published, and **Target Location** identifies where the files for the self-contained deployment were written.</span></span>

      1. <span data-ttu-id="337d0-205">Per impostazione predefinita tutti i file pubblicati vengono salvati in una singola directory.</span><span class="sxs-lookup"><span data-stu-id="337d0-205">Visual Studio by default writes all published files to a single directory.</span></span> <span data-ttu-id="337d0-206">Per praticità è consigliabile creare un profilo separato per ogni runtime di destinazione e inserire i file pubblicati in una directory specifica per la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="337d0-206">For convenience, it's best to create separate profiles for each target runtime and to place published files in a platform-specific directory.</span></span> <span data-ttu-id="337d0-207">Questo richiede la creazione di un profilo di pubblicazione separato per ogni piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-207">This involves creating a separate publishing profile for each target platform.</span></span> <span data-ttu-id="337d0-208">A questo punto ricompilare l'applicazione per ogni piattaforma procedendo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="337d0-208">So now rebuild the application for each platform by doing the following:</span></span>

         1. <span data-ttu-id="337d0-209">Selezionare **Crea nuovo profilo** nella finestra di dialogo **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="337d0-209">Select **Create new profile** in the **Publish** dialog.</span></span>

         1. <span data-ttu-id="337d0-210">Nella finestra di dialogo **Selezionare una destinazione di pubblicazione**, in **Scegliere una cartella** impostare il percorso su *bin\Release\PublishOutput\win10-x64*.</span><span class="sxs-lookup"><span data-stu-id="337d0-210">In the **Pick a publish target** dialog, change the **Choose a folder** location to *bin\Release\PublishOutput\win10-x64*.</span></span> <span data-ttu-id="337d0-211">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="337d0-211">Select **OK**.</span></span>

         1. <span data-ttu-id="337d0-212">Selezionare il nuovo profilo (**FolderProfile1**) nell'elenco dei profili e assicurarsi che **Runtime di destinazione** sia `win10-x64`.</span><span class="sxs-lookup"><span data-stu-id="337d0-212">Select the new profile (**FolderProfile1**) in the list of profiles, and make sure that the **Target Runtime** is `win10-x64`.</span></span> <span data-ttu-id="337d0-213">In caso contrario, selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="337d0-213">If it isn't, select **Settings**.</span></span> <span data-ttu-id="337d0-214">Nella finestra di dialogo **Impostazioni profilo** impostare **Runtime di destinazione** su `win10-x64` e selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="337d0-214">In the **Profile Settings** dialog, change the **Target Runtime** to `win10-x64` and select **Save**.</span></span> <span data-ttu-id="337d0-215">In caso contrario, selezionare **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="337d0-215">Otherwise, select **Cancel**.</span></span>

         1. <span data-ttu-id="337d0-216">Selezionare **Pubblica** per pubblicare l'app per le piattaforme Windows 10 a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="337d0-216">Select **Publish** to publish your app for 64-bit Windows 10 platforms.</span></span>

         1. <span data-ttu-id="337d0-217">Eseguire nuovamente la procedura per creare un profilo per la piattaforma `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="337d0-217">Follow the previous steps again to create a profile for the `osx.10.11-x64` platform.</span></span> <span data-ttu-id="337d0-218">Il valore di **Percorso di destinazione** deve essere *bin\Release\PublishOutput\osx.10.11-x64* e **Runtime di destinazione** deve essere `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="337d0-218">The **Target Location** is *bin\Release\PublishOutput\osx.10.11-x64*, and the **Target Runtime** is `osx.10.11-x64`.</span></span> <span data-ttu-id="337d0-219">Il nome assegnato a questo profilo in Visual Studio è **FolderProfile2**.</span><span class="sxs-lookup"><span data-stu-id="337d0-219">The name that Visual Studio assigns to this profile is **FolderProfile2**.</span></span>

      <span data-ttu-id="337d0-220">Ogni percorso di destinazione contiene il set completo di file (sia i file dell'app che tutti i file .NET Core) necessari per avviare l'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-220">Each target location contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="337d0-221">Insieme ai file dell'applicazione, il processo di pubblicazione genera un file del database di programma (con estensione pdb) che contiene le informazioni di debug relative all'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-221">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="337d0-222">Il file è utile soprattutto per il debug delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="337d0-222">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="337d0-223">È possibile scegliere di non includerlo nel pacchetto dei file dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-223">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="337d0-224">È tuttavia consigliabile salvarlo perché può risultare utile per il debug della build di rilascio dell'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-224">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="337d0-225">Distribuire i file pubblicati con il metodo desiderato.</span><span class="sxs-lookup"><span data-stu-id="337d0-225">Deploy the published files in any way you like.</span></span> <span data-ttu-id="337d0-226">È ad esempio possibile inserire i file in un file zip, usare un semplice comando `copy` o distribuire i file con un pacchetto di installazione a scelta.</span><span class="sxs-lookup"><span data-stu-id="337d0-226">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="337d0-227">Di seguito è riportato il file *csproj* completo per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="337d0-227">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

# <a name="visual-studio-157-and-later"></a>[<span data-ttu-id="337d0-228">Visual Studio 15.7 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="337d0-228">Visual Studio 15.7 and later</span></span>](#tab/vs157)

<span data-ttu-id="337d0-229">Dopo aver eseguito il debug e il test del programma creare i file da distribuire con l'app per ogni piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-229">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span> <span data-ttu-id="337d0-230">Questo richiede la creazione di un profilo separato per ogni piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-230">This involves creating a separate profile for each target platform.</span></span>

<span data-ttu-id="337d0-231">Eseguire le operazioni seguenti per ogni piattaforma a cui è destinata l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="337d0-231">For each platform that your application targets, do the following:</span></span>

1. <span data-ttu-id="337d0-232">Creare un profilo per la piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-232">Create a profile for your target platform.</span></span>

   <span data-ttu-id="337d0-233">Se si tratta del primo profilo creato, fare clic con il pulsante destro del mouse sul progetto (non sulla soluzione) in **Esplora soluzioni** e selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="337d0-233">If this is the first profile you've created, right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

   <span data-ttu-id="337d0-234">Se è già stato creato un profilo, fare clic con il pulsante destro del mouse sul progetto per aprire la finestra di dialogo **Pubblica** se non è già aperta.</span><span class="sxs-lookup"><span data-stu-id="337d0-234">If you've already created a profile, right-click on the project to open the **Publish** dialog if it isn't already open.</span></span> <span data-ttu-id="337d0-235">Selezionare quindi **Nuovo profilo**.</span><span class="sxs-lookup"><span data-stu-id="337d0-235">Then select **New Profile**.</span></span>

   <span data-ttu-id="337d0-236">Viene visualizzata la finestra di dialogo **Selezionare una destinazione di pubblicazione**.</span><span class="sxs-lookup"><span data-stu-id="337d0-236">The **Pick a Publish Target** dialog box opens.</span></span>

1. <span data-ttu-id="337d0-237">Selezionare la posizione in cui Visual Studio pubblica l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-237">Select the location where Visual Studio publishes your application.</span></span>

   <span data-ttu-id="337d0-238">Se si sta pubblicando solo su una singola piattaforma, è possibile accettare il valore predefinito nella casella di testo **Scegli una cartella;** in questo modo viene pubblicata la distribuzione dipendente dal framework dell'applicazione nella directory del \* \<progetto>\* .</span><span class="sxs-lookup"><span data-stu-id="337d0-238">If you're only publishing to a single platform, you can accept the default value in the **Choose a folder** text box; this publishes the framework-dependent deployment of your application to the *\<project-directory>\bin\Release\netcoreapp2.1\publish* directory.</span></span>

   <span data-ttu-id="337d0-239">Se esegue la pubblicazione in più di una piattaforma, aggiungere una stringa che identifica la piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-239">If you're publishing to more than one platform, append a string that identifies the target platform.</span></span> <span data-ttu-id="337d0-240">Ad esempio, se si aggiunge la stringa "linux" al percorso del file, Visual Studio pubblica la distribuzione dipendente dal framework dell'applicazione nella \* \<directory del progetto> .\*</span><span class="sxs-lookup"><span data-stu-id="337d0-240">For example, if you append the string "linux" to the file path, Visual Studio publishes the framework-dependent deployment of your application to the *\<project-directory>\bin\Release\netcoreapp2.1\publish\linux* directory.</span></span>

1. <span data-ttu-id="337d0-241">Creare il profilo selezionando l'icona dell'elenco a discesa accanto al pulsante **Pubblica** e selezionando **Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="337d0-241">Create the profile by selecting the drop-down list icon next to the **Publish** button and selecting **Create Profile**.</span></span> <span data-ttu-id="337d0-242">Selezionare il pulsante **Crea profilo** per creare il profilo.</span><span class="sxs-lookup"><span data-stu-id="337d0-242">Then select the **Create Profile** button to create the profile.</span></span>

1. <span data-ttu-id="337d0-243">Specificare che si sta pubblicando una distribuzione autonoma e definire una piattaforma di destinazione per l'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-243">Indicate that you are publishing a self-contained deployment and define a platform that your app will target.</span></span>

   1. <span data-ttu-id="337d0-244">Nella finestra di dialogo **Pubblica** selezionare il collegamento **Configura** per aprire la finestra di dialogo **Impostazioni profilo**.</span><span class="sxs-lookup"><span data-stu-id="337d0-244">In the **Publish** dialog, select the **Configure** link to open the **Profile Settings** dialog.</span></span>

   1. <span data-ttu-id="337d0-245">Selezionare **Indipendente** nella casella di riepilogo **Modalità di distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="337d0-245">Select **Self-contained** in the **Deployment Mode** list box.</span></span>

   1. <span data-ttu-id="337d0-246">Nella casella di riepilogo **Runtime di destinazione** selezionare una delle piattaforme di destinazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-246">In the **Target Runtime** list box, select one of the platforms that your application targets.</span></span>

   1. <span data-ttu-id="337d0-247">Selezionare **Salva** per salvare le modifiche e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="337d0-247">Select **Save** to accept your changes and close the dialog.</span></span>

1. <span data-ttu-id="337d0-248">Assegnare un nome al profilo.</span><span class="sxs-lookup"><span data-stu-id="337d0-248">Name your profile.</span></span>

   1. <span data-ttu-id="337d0-249">Selezionare **Azioni** > **Rinominare profilo** per assegnare un nome al profilo.</span><span class="sxs-lookup"><span data-stu-id="337d0-249">Select **Actions** > **Rename Profile** to name your profile.</span></span>

   2. <span data-ttu-id="337d0-250">Assegnare al profilo un nome che identifica la piattaforma di destinazione e quindi selezionare \**Salva*.</span><span class="sxs-lookup"><span data-stu-id="337d0-250">Assign your profile a name that identifies the target platform, then select \**Save*.</span></span>

<span data-ttu-id="337d0-251">Ripetere questi passaggi per definire eventuali piattaforme di destinazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-251">Repeat these steps to define any additional target platforms that your application targets.</span></span>

<span data-ttu-id="337d0-252">I profili sono stati configurati e ora si è pronti per pubblicare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-252">You've configured your profiles and are now ready to publish your app.</span></span> <span data-ttu-id="337d0-253">A tale scopo, effettuare l'operazione seguente:</span><span class="sxs-lookup"><span data-stu-id="337d0-253">To do this:</span></span>

   1. <span data-ttu-id="337d0-254">Se la finestra **Pubblica** non è attualmente aperta, fare clic con il pulsante destro del mouse sul progetto (non sulla soluzione) in **Esplora soluzioni** e selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="337d0-254">If the **Publish** window isn't currently open, right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

   2. <span data-ttu-id="337d0-255">Selezionare il profilo che si intende pubblicare e selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="337d0-255">Select the profile that you'd like to publish, then select **Publish**.</span></span> <span data-ttu-id="337d0-256">Eseguire questa operazione per ogni profilo da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="337d0-256">Do this for each profile to be published.</span></span>

   <span data-ttu-id="337d0-257">Ogni percorso di destinazione (nel caso del nostro esempio, bin,\\release, netcoreapp2.1, nome*del profilo di* pubblicazione contiene il set completo di file (sia i file dell'app che tutti i file .NET Core) necessari per avviare l'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-257">Each target location (in the case of our example, bin\release\netcoreapp2.1\publish\\*profile-name* contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="337d0-258">Insieme ai file dell'applicazione, il processo di pubblicazione genera un file del database di programma (con estensione pdb) che contiene le informazioni di debug relative all'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-258">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="337d0-259">Il file è utile soprattutto per il debug delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="337d0-259">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="337d0-260">È possibile scegliere di non includerlo nel pacchetto dei file dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-260">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="337d0-261">È tuttavia consigliabile salvarlo perché può risultare utile per il debug della build di rilascio dell'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-261">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="337d0-262">Distribuire i file pubblicati con il metodo desiderato.</span><span class="sxs-lookup"><span data-stu-id="337d0-262">Deploy the published files in any way you like.</span></span> <span data-ttu-id="337d0-263">È ad esempio possibile inserire i file in un file zip, usare un semplice comando `copy` o distribuire i file con un pacchetto di installazione a scelta.</span><span class="sxs-lookup"><span data-stu-id="337d0-263">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="337d0-264">Di seguito è riportato il file *csproj* completo per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="337d0-264">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="337d0-265">Visual Studio crea anche un profilo di pubblicazione separato (\*.pubxml) per ogni piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-265">In addition, Visual Studio creates a separate publishing profile (\*.pubxml) for each platform that you target.</span></span> <span data-ttu-id="337d0-266">Ad esempio, il file per il profilo di linux (linux.pubxml) viene visualizzato come segue:</span><span class="sxs-lookup"><span data-stu-id="337d0-266">For example, the file for our linux profile (linux.pubxml) appears as follows:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--
https://go.microsoft.com/fwlink/?LinkID=208121.
-->
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <PublishProtocol>FileSystem</PublishProtocol>
    <Configuration>Release</Configuration>
    <Platform>Any CPU</Platform>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <PublishDir>bin\Release\netcoreapp2.1\publish\linux</PublishDir>
    <RuntimeIdentifier>win-x86</RuntimeIdentifier>
    <SelfContained>true</SelfContained>
    <_IsPortable>false</_IsPortable>
  </PropertyGroup>
</Project>
```

---

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="337d0-267">Distribuzione autonoma con dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="337d0-267">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="337d0-268">Una distribuzione autonoma con una o più dipendenze di terze parti comporta l'aggiunta delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="337d0-268">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="337d0-269">Prima della compilazione dell'app è necessario eseguire i passaggi aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="337d0-269">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="337d0-270">Usare **Gestione pacchetti NuGet** per aggiungere al progetto un riferimento a un pacchetto NuGet e per installare il pacchetto se non è già disponibile nel sistema.</span><span class="sxs-lookup"><span data-stu-id="337d0-270">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="337d0-271">Per aprire Gestione pacchetti, selezionare **Strumenti** > **NuGet Gestione** > pacchetti**Gestisci pacchetti NuGet per soluzione**.</span><span class="sxs-lookup"><span data-stu-id="337d0-271">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="337d0-272">Verificare che le dipendenze di `Newtonsoft.Json`terze parti ( ad esempio, ) siano installate nel sistema e, in caso contrario, installarle.</span><span class="sxs-lookup"><span data-stu-id="337d0-272">Confirm that your third-party dependencies (for example, `Newtonsoft.Json`) are installed on your system and, if they aren't, install them.</span></span> <span data-ttu-id="337d0-273">La scheda **Installati** elenca i pacchetti NuGet installati nel sistema.</span><span class="sxs-lookup"><span data-stu-id="337d0-273">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="337d0-274">Se `Newtonsoft.Json` non è presente nell'elenco, selezionare la scheda **Sfoglia** e immettere "Newtonsoft.Json" nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="337d0-274">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="337d0-275">Selezionare `Newtonsoft.Json`, selezionare il progetto nel riquadro destro e quindi selezionare **Installa**.</span><span class="sxs-lookup"><span data-stu-id="337d0-275">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="337d0-276">Se `Newtonsoft.Json` è già installato nel sistema aggiungerlo al progetto selezionando il progetto stesso nel riquadro destro della scheda **Gestisci i pacchetti per la soluzione**.</span><span class="sxs-lookup"><span data-stu-id="337d0-276">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of the **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="337d0-277">Di seguito è riportato il file *csproj* completo per questo progetto:</span><span class="sxs-lookup"><span data-stu-id="337d0-277">The following is the complete *csproj* file for this project:</span></span>

# <a name="visual-studio-156-and-earlier"></a>[<span data-ttu-id="337d0-278">Visual Studio 15.6 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="337d0-278">Visual Studio 15.6 and earlier</span></span>](#tab/vs156)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

# <a name="visual-studio-157-and-later"></a>[<span data-ttu-id="337d0-279">Visual Studio 15.7 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="337d0-279">Visual Studio 15.7 and later</span></span>](#tab/vs157)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

---

<span data-ttu-id="337d0-280">Quando si distribuisce l'applicazione, anche le dipendenze di terze parti usate nell'app sono contenute nei file dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="337d0-280">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="337d0-281">Non è necessario che le librerie di terze parti siano già presenti nel sistema in cui viene eseguita l'app.</span><span class="sxs-lookup"><span data-stu-id="337d0-281">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="337d0-282">È possibile distribuire una distribuzione autonoma solo con una libreria di terze parti su piattaforme supportate da tale libreria.</span><span class="sxs-lookup"><span data-stu-id="337d0-282">You can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="337d0-283">Il caso è simile alla presenza di dipendenze di terze parti con dipendenze native in una distribuzione dipendente dal framework: le dipendenze native esistono nella piattaforma di destinazione solo se sono state installate in precedenza in tale piattaforma.</span><span class="sxs-lookup"><span data-stu-id="337d0-283">This is similar to having third-party dependencies with native dependencies in your framework-dependent deployment, where the native dependencies won't exist on the target platform unless they were previously installed there.</span></span>

## <a name="see-also"></a><span data-ttu-id="337d0-284">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="337d0-284">See also</span></span>

- [<span data-ttu-id="337d0-285">Distribuzione di applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="337d0-285">.NET Core Application Deployment</span></span>](index.md)
- [<span data-ttu-id="337d0-286">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="337d0-286">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

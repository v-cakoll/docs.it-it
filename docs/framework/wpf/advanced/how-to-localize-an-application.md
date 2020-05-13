---
title: Localizzare un'app
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: dc7d8f4f56b26fffbd883e1e1d6e420026e1f94f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209682"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="fe72e-102">Procedura: localizzare un'applicazione</span><span class="sxs-lookup"><span data-stu-id="fe72e-102">How to: Localize an application</span></span>

<span data-ttu-id="fe72e-103">Questa esercitazione spiega come creare un'applicazione localizzata usando lo strumento LocBaml.</span><span class="sxs-lookup"><span data-stu-id="fe72e-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe72e-104">Lo strumento LocBaml non è un'applicazione di produzione.</span><span class="sxs-lookup"><span data-stu-id="fe72e-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="fe72e-105">Viene presentato come esempio in cui vengono usate alcune delle API di localizzazione e illustra come scrivere uno strumento di localizzazione.</span><span class="sxs-lookup"><span data-stu-id="fe72e-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="fe72e-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="fe72e-106">Overview</span></span>

<span data-ttu-id="fe72e-107">Questo articolo offre un approccio dettagliato alla localizzazione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fe72e-107">This article gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="fe72e-108">Prima di tutto, preparare l'applicazione in modo che sia possibile estrarre il testo che verrà convertito.</span><span class="sxs-lookup"><span data-stu-id="fe72e-108">First, you prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="fe72e-109">Dopo la traduzione del testo, il testo tradotto viene unito in una nuova copia dell'applicazione originale.</span><span class="sxs-lookup"><span data-stu-id="fe72e-109">After the text is translated, you merge the translated text into a new copy of the original application.</span></span>
  
## <a name="create-a-sample-application"></a><span data-ttu-id="fe72e-110">Creare un'applicazione di esempio</span><span class="sxs-lookup"><span data-stu-id="fe72e-110">Create a sample application</span></span>

<span data-ttu-id="fe72e-111">In questo passaggio viene preparata l'applicazione per la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="fe72e-111">In this step, you prepare your app for localization.</span></span> <span data-ttu-id="fe72e-112">Negli esempi Windows Presentation Foundation (WPF) viene fornito un esempio HelloApp che verrà usato per gli esempi di codice in questa discussione.</span><span class="sxs-lookup"><span data-stu-id="fe72e-112">In the Windows Presentation Foundation (WPF) samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="fe72e-113">Se si vuole usare questo esempio, scaricare i file di Extensible Application Markup Language (XAML) dall'esempio di [strumento LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span><span class="sxs-lookup"><span data-stu-id="fe72e-113">If you would like to use this sample, download the Extensible Application Markup Language (XAML) files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
1. <span data-ttu-id="fe72e-114">Sviluppare l'applicazione fino al punto in cui si vuole iniziare la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="fe72e-114">Develop your application to the point where you want to start localization.</span></span>  
  
2. <span data-ttu-id="fe72e-115">Specificare il linguaggio di sviluppo nel file di progetto in modo che MSBuild generi un assembly principale e un assembly satellite (un file con estensione resources. dll) per contenere le risorse della lingua neutra.</span><span class="sxs-lookup"><span data-stu-id="fe72e-115">Specify the development language in the project file so that MSBuild generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="fe72e-116">Il file di progetto nell'esempio HelloApp è HelloApp.csproj.</span><span class="sxs-lookup"><span data-stu-id="fe72e-116">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="fe72e-117">In questo file la lingua di sviluppo viene identificata come segue:</span><span class="sxs-lookup"><span data-stu-id="fe72e-117">In that file, you will find the development language identified as follows:</span></span>  
  
   `<UICulture>en-US</UICulture>`  
  
3. <span data-ttu-id="fe72e-118">Aggiungere gli UID ai file XAML.</span><span class="sxs-lookup"><span data-stu-id="fe72e-118">Add Uids to your XAML files.</span></span> <span data-ttu-id="fe72e-119">Gli UID vengono usati per rilevare le modifiche apportate ai file e per identificare gli elementi da convertire.</span><span class="sxs-lookup"><span data-stu-id="fe72e-119">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="fe72e-120">Per aggiungere gli UID ai file, eseguire `updateuid` sul file di progetto:</span><span class="sxs-lookup"><span data-stu-id="fe72e-120">To add Uids to your files, run `updateuid` on your project file:</span></span>  

   `msbuild -t:updateuid helloapp.csproj`

   <span data-ttu-id="fe72e-121">Per verificare che non siano presenti UID mancanti o duplicati, eseguire `checkuid` :</span><span class="sxs-lookup"><span data-stu-id="fe72e-121">To verify that you have no missing or duplicate Uids, run `checkuid`:</span></span>  

   `msbuild -t:checkuid helloapp.csproj`

   <span data-ttu-id="fe72e-122">Dopo `updateuid` l'esecuzione, i file devono contenere gli UID.</span><span class="sxs-lookup"><span data-stu-id="fe72e-122">After running `updateuid`, your files should contain Uids.</span></span> <span data-ttu-id="fe72e-123">Nel file *pane1. XAML* di HelloApp, ad esempio, dovrebbe essere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fe72e-123">For example, in the *Pane1.xaml* file of HelloApp, you should find the following:</span></span>  

   ```xaml
   <StackPanel x:Uid="StackPanel_1">
     <TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>
     <TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>
   </StackPanel>
   ```

## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="fe72e-124">Creare l'assembly satellite per le risorse in lingua neutra</span><span class="sxs-lookup"><span data-stu-id="fe72e-124">Create the neutral-language resources satellite assembly</span></span>

<span data-ttu-id="fe72e-125">Quando l'applicazione viene configurata per generare un assembly satellite per le risorse di lingua neutra, l'applicazione viene compilata.</span><span class="sxs-lookup"><span data-stu-id="fe72e-125">After the application is configured to generate a neutral-language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="fe72e-126">Viene generato l'assembly principale dell'applicazione, nonché l'assembly satellite per le risorse di lingua neutra richiesto da LocBaml per la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="fe72e-126">This generates the main application assembly as well as the neutral-language resources satellite assembly that's required by LocBaml for localization.</span></span>

<span data-ttu-id="fe72e-127">Per compilare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="fe72e-127">To build the application:</span></span>  
  
1. <span data-ttu-id="fe72e-128">Compilare HelloApp per creare una libreria di collegamento dinamico (DLL):</span><span class="sxs-lookup"><span data-stu-id="fe72e-128">Compile HelloApp to create a dynamic-link library (DLL):</span></span>  
  
   `msbuild helloapp.csproj`
  
2. <span data-ttu-id="fe72e-129">L'assembly principale dell'applicazione appena creato, HelloApp. exe, viene creato nella cartella seguente: *C:\HelloApp\Bin\Debug*</span><span class="sxs-lookup"><span data-stu-id="fe72e-129">The newly created main application assembly, HelloApp.exe, is created in the following folder: *C:\HelloApp\Bin\Debug*</span></span>
  
3. <span data-ttu-id="fe72e-130">L'assembly satellite delle risorse della lingua neutra appena creato, HelloApp. resources. dll, viene creato nella cartella seguente: *C:\HelloApp\Bin\Debug\en-US*</span><span class="sxs-lookup"><span data-stu-id="fe72e-130">The newly created neutral-language resources satellite assembly, HelloApp.resources.dll, is created in the following folder: *C:\HelloApp\Bin\Debug\en-US*</span></span>
  
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="fe72e-131">Compilare lo strumento LocBaml</span><span class="sxs-lookup"><span data-stu-id="fe72e-131">Build the LocBaml tool</span></span>  
  
1. <span data-ttu-id="fe72e-132">Tutti i file necessari per compilare LocBaml si trovano negli esempi di WPF.</span><span class="sxs-lookup"><span data-stu-id="fe72e-132">All the files necessary to build LocBaml are located in the WPF samples.</span></span> <span data-ttu-id="fe72e-133">Scaricare i file C# dall' [esempio dello strumento LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span><span class="sxs-lookup"><span data-stu-id="fe72e-133">Download the C# files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
2. <span data-ttu-id="fe72e-134">Eseguire il file di progetto (LocBaml.csproj) per compilare lo strumento dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="fe72e-134">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  

   `msbuild locbaml.csproj`
  
3. <span data-ttu-id="fe72e-135">Passare alla directory *bin\release* per trovare il file eseguibile appena creato (LocBaml. exe).</span><span class="sxs-lookup"><span data-stu-id="fe72e-135">Go to the *Bin\Release* directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="fe72e-136">Esempio: *C:\LocBaml\Bin\Release\locbaml.exe*</span><span class="sxs-lookup"><span data-stu-id="fe72e-136">Example: *C:\LocBaml\Bin\Release\locbaml.exe*</span></span>
  
4. <span data-ttu-id="fe72e-137">Di seguito sono riportate le opzioni che è possibile specificare quando si esegue LocBaml.</span><span class="sxs-lookup"><span data-stu-id="fe72e-137">The options that you can specify when you run LocBaml are as follows.</span></span>

   | <span data-ttu-id="fe72e-138">Opzione</span><span class="sxs-lookup"><span data-stu-id="fe72e-138">Option</span></span> | <span data-ttu-id="fe72e-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe72e-139">Description</span></span>|
   | - | - |
   | <span data-ttu-id="fe72e-140">`parse` o `-p`</span><span class="sxs-lookup"><span data-stu-id="fe72e-140">`parse` or `-p`</span></span> | <span data-ttu-id="fe72e-141">Analizza il BAML, le risorse o i file DLL per generare un file CSV o txt.</span><span class="sxs-lookup"><span data-stu-id="fe72e-141">Parses Baml, resources, or DLL files to generate a .csv or .txt file.</span></span> |
   | <span data-ttu-id="fe72e-142">`generate` o `-g`</span><span class="sxs-lookup"><span data-stu-id="fe72e-142">`generate` or `-g`</span></span> | <span data-ttu-id="fe72e-143">Genera un file binario localizzato utilizzando un file convertito.</span><span class="sxs-lookup"><span data-stu-id="fe72e-143">Generates a localized binary file by using a translated file.</span></span> |
   | <span data-ttu-id="fe72e-144">`out`o `-o` {*FileDirectory*]</span><span class="sxs-lookup"><span data-stu-id="fe72e-144">`out` or `-o` {*filedirectory*]</span></span> | <span data-ttu-id="fe72e-145">Nome del file di output.</span><span class="sxs-lookup"><span data-stu-id="fe72e-145">Output file name.</span></span> |
   | <span data-ttu-id="fe72e-146">`culture`o `-cul` {*culture*]</span><span class="sxs-lookup"><span data-stu-id="fe72e-146">`culture` or `-cul` {*culture*]</span></span> | <span data-ttu-id="fe72e-147">Impostazioni locali degli assembly di output.</span><span class="sxs-lookup"><span data-stu-id="fe72e-147">Locale of output assemblies.</span></span> |
   | <span data-ttu-id="fe72e-148">`translation`o `-trans` {*Translation. csv*]</span><span class="sxs-lookup"><span data-stu-id="fe72e-148">`translation` or `-trans` {*translation.csv*]</span></span> | <span data-ttu-id="fe72e-149">File convertito o localizzato.</span><span class="sxs-lookup"><span data-stu-id="fe72e-149">Translated or localized file.</span></span> |
   | <span data-ttu-id="fe72e-150">`asmpath`o `-asmpath` {*FileDirectory*]</span><span class="sxs-lookup"><span data-stu-id="fe72e-150">`asmpath` or `-asmpath` {*filedirectory*]</span></span> | <span data-ttu-id="fe72e-151">Se il codice XAML contiene controlli personalizzati, è necessario fornire all' `asmpath` assembly del controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="fe72e-151">If your XAML code contains custom controls, you must supply the `asmpath` to the custom control assembly.</span></span> |
   | `nologo` | <span data-ttu-id="fe72e-152"> non visualizza loghi o informazioni sul copyright.</span><span class="sxs-lookup"><span data-stu-id="fe72e-152">Displays no logo or copyright information.</span></span> |
   | `verbose` | <span data-ttu-id="fe72e-153"> visualizza le informazioni sulla modalità dettagliata.</span><span class="sxs-lookup"><span data-stu-id="fe72e-153">Displays verbose mode information.</span></span> |
  
   > [!NOTE]
   > <span data-ttu-id="fe72e-154">Se è necessario un elenco delle opzioni quando si esegue lo strumento, immettere `LocBaml.exe` e quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="fe72e-154">If you need a list of the options when you are running the tool, enter `LocBaml.exe` and then press **Enter**.</span></span>
  
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="fe72e-155">Usare LocBaml per analizzare un file</span><span class="sxs-lookup"><span data-stu-id="fe72e-155">Use LocBaml to parse a file</span></span>

<span data-ttu-id="fe72e-156">Ora che è stato creato lo strumento LocBaml, è possibile usarlo per analizzare HelloApp.resources.dll ed estrarre il contenuto testuale che verrà localizzato.</span><span class="sxs-lookup"><span data-stu-id="fe72e-156">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1. <span data-ttu-id="fe72e-157">Copiare LocBaml.exe nella cartella bin\debug dell'applicazione in cui è stato creato l'assembly principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fe72e-157">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2. <span data-ttu-id="fe72e-158">Per analizzare il file dell'assembly satellite e archiviare l'output come file CSV, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="fe72e-158">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
   `LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv`
  
   > [!NOTE]
   > <span data-ttu-id="fe72e-159">Se il file di input, HelloApp.resources.dll, non è nella stessa directory di LocBaml.exe, spostare uno dei file in modo che entrambi siano nella stessa directory.</span><span class="sxs-lookup"><span data-stu-id="fe72e-159">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3. <span data-ttu-id="fe72e-160">Quando si esegue LocBaml per analizzare i file, l'output è costituito da sette campi delimitati da virgole (file CSV) o da tabulazioni (file TXT).</span><span class="sxs-lookup"><span data-stu-id="fe72e-160">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="fe72e-161">Di seguito viene visualizzato il file CSV analizzato per HelloApp.resources.dll:</span><span class="sxs-lookup"><span data-stu-id="fe72e-161">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="fe72e-162">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="fe72e-162">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="fe72e-163">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span><span class="sxs-lookup"><span data-stu-id="fe72e-163">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="fe72e-164">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span><span class="sxs-lookup"><span data-stu-id="fe72e-164">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="fe72e-165">I campi di sette sono:</span><span class="sxs-lookup"><span data-stu-id="fe72e-165">The seven fields are:</span></span>  
  
   - <span data-ttu-id="fe72e-166">**Nome BAML**.</span><span class="sxs-lookup"><span data-stu-id="fe72e-166">**BAML Name**.</span></span> <span data-ttu-id="fe72e-167">Il nome della risorsa BAML rispetto all'assembly satellite per la lingua di origine.</span><span class="sxs-lookup"><span data-stu-id="fe72e-167">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   - <span data-ttu-id="fe72e-168">**Chiave di risorsa**.</span><span class="sxs-lookup"><span data-stu-id="fe72e-168">**Resource Key**.</span></span> <span data-ttu-id="fe72e-169">L'identificatore della risorsa localizzata.</span><span class="sxs-lookup"><span data-stu-id="fe72e-169">The localized resource identifier.</span></span>  
  
   - <span data-ttu-id="fe72e-170">**Categoria**.</span><span class="sxs-lookup"><span data-stu-id="fe72e-170">**Category**.</span></span> <span data-ttu-id="fe72e-171">Tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="fe72e-171">The value type.</span></span> <span data-ttu-id="fe72e-172">Vedere [attributi e commenti di localizzazione](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="fe72e-172">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="fe72e-173">**Leggibilità**.</span><span class="sxs-lookup"><span data-stu-id="fe72e-173">**Readability**.</span></span> <span data-ttu-id="fe72e-174">Se il valore può essere letto da un localizzatore.</span><span class="sxs-lookup"><span data-stu-id="fe72e-174">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="fe72e-175">Vedere [attributi e commenti di localizzazione](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="fe72e-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="fe72e-176">**Modificabilità**.</span><span class="sxs-lookup"><span data-stu-id="fe72e-176">**Modifiability**.</span></span> <span data-ttu-id="fe72e-177">Se il valore può essere modificato da un localizzatore.</span><span class="sxs-lookup"><span data-stu-id="fe72e-177">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="fe72e-178">Vedere [attributi e commenti di localizzazione](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="fe72e-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="fe72e-179">**Commenti**.</span><span class="sxs-lookup"><span data-stu-id="fe72e-179">**Comments**.</span></span> <span data-ttu-id="fe72e-180">Descrizione aggiuntiva del valore per determinarne la modalità di localizzazione.</span><span class="sxs-lookup"><span data-stu-id="fe72e-180">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="fe72e-181">Vedere [attributi e commenti di localizzazione](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="fe72e-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="fe72e-182">**Valore**.</span><span class="sxs-lookup"><span data-stu-id="fe72e-182">**Value**.</span></span> <span data-ttu-id="fe72e-183">Il valore di testo da convertire nelle impostazioni cultura desiderate.</span><span class="sxs-lookup"><span data-stu-id="fe72e-183">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="fe72e-184">La tabella seguente mostra come viene eseguito il mapping di questi campi ai valori delimitati del file CSV:</span><span class="sxs-lookup"><span data-stu-id="fe72e-184">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="fe72e-185">Nome BAML</span><span class="sxs-lookup"><span data-stu-id="fe72e-185">BAML name</span></span>|<span data-ttu-id="fe72e-186">Chiave di risorsa</span><span class="sxs-lookup"><span data-stu-id="fe72e-186">Resource key</span></span>|<span data-ttu-id="fe72e-187">Categoria</span><span class="sxs-lookup"><span data-stu-id="fe72e-187">Category</span></span>|<span data-ttu-id="fe72e-188">Leggibilità</span><span class="sxs-lookup"><span data-stu-id="fe72e-188">Readability</span></span>|<span data-ttu-id="fe72e-189">Modificabilità</span><span class="sxs-lookup"><span data-stu-id="fe72e-189">Modifiability</span></span>|<span data-ttu-id="fe72e-190">Commenti</span><span class="sxs-lookup"><span data-stu-id="fe72e-190">Comments</span></span>|<span data-ttu-id="fe72e-191">valore</span><span class="sxs-lookup"><span data-stu-id="fe72e-191">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="fe72e-192">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="fe72e-192">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="fe72e-193">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="fe72e-193">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="fe72e-194">Ignora</span><span class="sxs-lookup"><span data-stu-id="fe72e-194">Ignore</span></span>|<span data-ttu-id="fe72e-195">FALSE</span><span class="sxs-lookup"><span data-stu-id="fe72e-195">FALSE</span></span>|<span data-ttu-id="fe72e-196">FALSE</span><span class="sxs-lookup"><span data-stu-id="fe72e-196">FALSE</span></span>||<span data-ttu-id="fe72e-197">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="fe72e-197">#Text1;#Text2</span></span>|
   |<span data-ttu-id="fe72e-198">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="fe72e-198">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="fe72e-199">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="fe72e-199">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="fe72e-200">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fe72e-200">None</span></span>|<span data-ttu-id="fe72e-201">TRUE</span><span class="sxs-lookup"><span data-stu-id="fe72e-201">TRUE</span></span>|<span data-ttu-id="fe72e-202">TRUE</span><span class="sxs-lookup"><span data-stu-id="fe72e-202">TRUE</span></span>||<span data-ttu-id="fe72e-203">Hello World</span><span class="sxs-lookup"><span data-stu-id="fe72e-203">Hello World</span></span>|
   |<span data-ttu-id="fe72e-204">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="fe72e-204">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="fe72e-205">Text2:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="fe72e-205">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="fe72e-206">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fe72e-206">None</span></span>|<span data-ttu-id="fe72e-207">TRUE</span><span class="sxs-lookup"><span data-stu-id="fe72e-207">TRUE</span></span>|<span data-ttu-id="fe72e-208">TRUE</span><span class="sxs-lookup"><span data-stu-id="fe72e-208">TRUE</span></span>||<span data-ttu-id="fe72e-209">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="fe72e-209">Goodbye World</span></span>|
  
   <span data-ttu-id="fe72e-210">Si noti che tutti i valori per il campo **Commenti** non contengono valori. Se un campo non ha un valore, è vuoto.</span><span class="sxs-lookup"><span data-stu-id="fe72e-210">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="fe72e-211">Si noti inoltre che l'elemento nella prima riga non è leggibile né modificabile e ha "Ignora" come valore di **categoria** , il che indica che il valore non è localizzabile.</span><span class="sxs-lookup"><span data-stu-id="fe72e-211">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4. <span data-ttu-id="fe72e-212">Per facilitare l'individuazione degli elementi localizzabili nei file analizzati, in particolare nei file di grandi dimensioni, è possibile ordinare o filtrare gli elementi per **categoria**, **leggibilità**e **modificabilità**.</span><span class="sxs-lookup"><span data-stu-id="fe72e-212">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="fe72e-213">Ad esempio, è possibile escludere i valori non leggibili e non modificabili.</span><span class="sxs-lookup"><span data-stu-id="fe72e-213">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
## <a name="translate-the-localizable-content"></a><span data-ttu-id="fe72e-214">Tradurre il contenuto localizzabile</span><span class="sxs-lookup"><span data-stu-id="fe72e-214">Translate the localizable content</span></span>

<span data-ttu-id="fe72e-215">Usare gli strumenti disponibili per convertire il contenuto estratto.</span><span class="sxs-lookup"><span data-stu-id="fe72e-215">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="fe72e-216">Per eseguire questa operazione, è possibile scrivere le risorse in un file con estensione CSV e visualizzarle in Microsoft Excel, in modo da apportare modifiche alla conversione nell'ultima colonna (valore).</span><span class="sxs-lookup"><span data-stu-id="fe72e-216">A good way to do this is to write the resources to a .csv file and view them in Microsoft Excel, making translation changes to the last column (value).</span></span>  
  
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="fe72e-217">Usare LocBaml per generare un nuovo file con estensione resources. dll</span><span class="sxs-lookup"><span data-stu-id="fe72e-217">Use LocBaml to generate a new .resources.dll file</span></span>

<span data-ttu-id="fe72e-218">Il contenuto identificato analizzando HelloApp.resources.dll con LocBaml è stato convertito e deve essere reinserito nell'applicazione originale.</span><span class="sxs-lookup"><span data-stu-id="fe72e-218">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="fe72e-219">Utilizzare l' `generate` `-g` opzione o per generare un nuovo file con estensione resources. dll.</span><span class="sxs-lookup"><span data-stu-id="fe72e-219">Use the `generate` or `-g` option to generate a new .resources.dll file.</span></span>  
  
1. <span data-ttu-id="fe72e-220">Usare la sintassi seguente per generare un nuovo file HelloApp.resources.dll.</span><span class="sxs-lookup"><span data-stu-id="fe72e-220">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="fe72e-221">Contrassegnare le impostazioni cultura come en-US (/cul:en-US).</span><span class="sxs-lookup"><span data-stu-id="fe72e-221">Mark the culture as en-US (/cul:en-US).</span></span>  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US`  

   > [!NOTE]
   > <span data-ttu-id="fe72e-222">Se il file di input Hello.csv non è presente nella stessa directory del file eseguibile LocBaml.exe, spostare uno dei file in modo che entrambi siano nella stessa directory.</span><span class="sxs-lookup"><span data-stu-id="fe72e-222">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2. <span data-ttu-id="fe72e-223">Sostituire il file *HelloApp. resources. dll* precedente nella directory *C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll* con il file *HelloApp. resources. dll* appena creato.</span><span class="sxs-lookup"><span data-stu-id="fe72e-223">Replace the old *HelloApp.resources.dll* file in the *C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll* directory with your newly created *HelloApp.resources.dll* file.</span></span>  
  
3. <span data-ttu-id="fe72e-224">Ora "Hello World" e "Goodbye World" possono essere convertiti nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fe72e-224">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4. <span data-ttu-id="fe72e-225">Per eseguire la conversione in una lingua diversa, usare le impostazioni cultura della lingua in cui si sta eseguendo la conversione.</span><span class="sxs-lookup"><span data-stu-id="fe72e-225">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="fe72e-226">L'esempio seguente mostra come eseguire la conversione in lingua francese canadese:</span><span class="sxs-lookup"><span data-stu-id="fe72e-226">The following example shows how to translate to French-Canadian:</span></span>  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA`  
  
5. <span data-ttu-id="fe72e-227">Nello stesso assembly dell'assembly principale dell'applicazione, creare una nuova cartella specifica per le impostazioni cultura dove ospitare il nuovo assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="fe72e-227">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="fe72e-228">Per la lingua francese canadese, la cartella sarà fr-CA.</span><span class="sxs-lookup"><span data-stu-id="fe72e-228">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6. <span data-ttu-id="fe72e-229">Copiare l'assembly satellite generato nella nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="fe72e-229">Copy the generated satellite assembly to the new folder.</span></span>  
  
7. <span data-ttu-id="fe72e-230">Per testare il nuovo assembly satellite, è necessario modificare le impostazioni cultura con cui verrà eseguita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fe72e-230">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="fe72e-231">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="fe72e-231">You can do this in one of two ways:</span></span>  
  
   - <span data-ttu-id="fe72e-232">Modificare le impostazioni internazionali del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fe72e-232">Change your operating system's regional settings.</span></span>
  
   - <span data-ttu-id="fe72e-233">Aggiungere il codice seguente al file App.xaml.cs nell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="fe72e-233">In your application, add the following code to App.xaml.cs:</span></span>  
  
     [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
     [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
     [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
## <a name="tips-for-using-locbaml"></a><span data-ttu-id="fe72e-234">Suggerimenti per l'uso di LocBaml</span><span class="sxs-lookup"><span data-stu-id="fe72e-234">Tips for Using LocBaml</span></span>  
  
- <span data-ttu-id="fe72e-235">Tutti gli assembly dipendenti che definiscono i controlli personalizzati devono essere copiati nella directory locale di LocBaml o installati in Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="fe72e-235">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="fe72e-236">Questa operazione è necessaria perché l'API di localizzazione deve avere accesso agli assembly dipendenti quando legge il codice XAML binario (BAML).</span><span class="sxs-lookup"><span data-stu-id="fe72e-236">This is necessary because the localization API must have access to the dependent assemblies when it reads the binary XAML (BAML).</span></span>  
  
- <span data-ttu-id="fe72e-237">Se l'assembly principale è firmato, anche la DLL di risorse generata deve essere firmata per poter essere caricata.</span><span class="sxs-lookup"><span data-stu-id="fe72e-237">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
- <span data-ttu-id="fe72e-238">La versione della DLL di risorsa localizzata deve essere sincronizzata con l'assembly principale.</span><span class="sxs-lookup"><span data-stu-id="fe72e-238">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fe72e-239">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe72e-239">See also</span></span>

- [<span data-ttu-id="fe72e-240">Globalizzazione per WPF</span><span class="sxs-lookup"><span data-stu-id="fe72e-240">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="fe72e-241">Cenni preliminari sull'utilizzo del layout automatico</span><span class="sxs-lookup"><span data-stu-id="fe72e-241">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)

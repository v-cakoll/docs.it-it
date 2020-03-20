---
title: "Procedura: Localizzare un'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: f2e7e5e8879e89806cfd457a1af80f51b91871cb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174212"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="0bdc6-102">Procedura: Localizzare un'applicazione</span><span class="sxs-lookup"><span data-stu-id="0bdc6-102">How to: Localize an Application</span></span>
<span data-ttu-id="0bdc6-103">Questa esercitazione spiega come creare un'applicazione localizzata usando lo strumento LocBaml.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0bdc6-104">Lo strumento LocBaml non è un'applicazione di produzione.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="0bdc6-105">Viene presentato come esempio in cui vengono usate alcune delle API di localizzazione e illustra come scrivere uno strumento di localizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
<a name="Introduction"></a>
## <a name="overview"></a><span data-ttu-id="0bdc6-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="0bdc6-106">Overview</span></span>  
 <span data-ttu-id="0bdc6-107">Questo documento offre un approccio graduale alla localizzazione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-107">This discussion gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="0bdc6-108">Innanzitutto viene preparata l'applicazione in modo che sia possibile estrarre il testo da convertire.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-108">First, you will prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="0bdc6-109">Dopo la conversione del testo, il testo convertito verrà incluso in una nuova copia dell'applicazione originale.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-109">After the text is translated, you will merge the translated text into a new copy of the original application.</span></span>  
  
<a name="Requirements"></a>
## <a name="requirements"></a><span data-ttu-id="0bdc6-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0bdc6-110">Requirements</span></span>  
 <span data-ttu-id="0bdc6-111">Nel corso di questa discussione, si utilizzerà il motore di compilazione Microsoft (MSBuild), che è un compilatore che viene eseguito dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-111">Over the course of this discussion, you will use Microsoft build engine (MSBuild), which is a compiler that runs from the command line.</span></span>  
  
 <span data-ttu-id="0bdc6-112">Inoltre, verrà spiegato come usare un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-112">Also, you will be instructed to use a project file.</span></span> <span data-ttu-id="0bdc6-113">Per istruzioni su come utilizzare MSBuild e i file di progetto, vedere [Compilazione e distribuzione](../app-development/building-and-deploying-wpf-applications.md).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-113">For instructions on how to use MSBuild and project files, see [Build and Deploy](../app-development/building-and-deploying-wpf-applications.md).</span></span>  
  
 <span data-ttu-id="0bdc6-114">Tutti gli esempi di questa discussione usano en-US (inglese-Stati Uniti) come impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-114">All the examples in this discussion use en-US (English-US) as the culture.</span></span> <span data-ttu-id="0bdc6-115">In questo modo è possibile eseguire i passaggi degli esempi senza installare un'altra lingua.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-115">This enables you to work through the steps of the examples without installing a different language.</span></span>  
  
<a name="create_sample_app"></a>
## <a name="create-a-sample-application"></a><span data-ttu-id="0bdc6-116">Creare un'applicazione di esempio</span><span class="sxs-lookup"><span data-stu-id="0bdc6-116">Create a Sample Application</span></span>  
 <span data-ttu-id="0bdc6-117">In questo passaggio viene preparata l'applicazione per la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-117">In this step, you will prepare your application for localization.</span></span> <span data-ttu-id="0bdc6-118">Negli esempi di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] viene fornito un esempio HelloApp che verrà usato per gli esempi di codice in questa discussione.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-118">In the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="0bdc6-119">Se si desidera utilizzare questo esempio, scaricare i [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file dall'esempio di strumento [LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-119">If you would like to use this sample, download the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
1. <span data-ttu-id="0bdc6-120">Sviluppare l'applicazione fino al punto in cui si vuole iniziare la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-120">Develop your application to the point where you want to start localization.</span></span>  
  
2. <span data-ttu-id="0bdc6-121">Specificare il linguaggio di sviluppo nel file di progetto in modo che MSBuild generi un assembly principale e un assembly satellite (un file con estensione resources.dll) per contenere le risorse di lingua neutra.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-121">Specify the development language in the project file so that MSBuild generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="0bdc6-122">Il file di progetto nell'esempio HelloApp è HelloApp.csproj.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-122">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="0bdc6-123">In questo file la lingua di sviluppo viene identificata come segue:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-123">In that file, you will find the development language identified as follows:</span></span>  
  
     `<UICulture>en-US</UICulture>`  
  
3. <span data-ttu-id="0bdc6-124">Aggiungere gli UID ai file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bdc6-124">Add Uids to your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files.</span></span> <span data-ttu-id="0bdc6-125">Gli UID vengono usati per rilevare le modifiche apportate ai file e per identificare gli elementi da convertire.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-125">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="0bdc6-126">Per aggiungere Uids ai file, eseguire **updateuid** nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-126">To add Uids to your files, run **updateuid** on your project file:</span></span>  
  
     <span data-ttu-id="0bdc6-127">**msbuild -t:updateuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="0bdc6-127">**msbuild -t:updateuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="0bdc6-128">Per verificare che non siano presenti UID mancanti o duplicati, eseguire **checkuid**:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-128">To verify that you have no missing or duplicate Uids, run **checkuid**:</span></span>  
  
     <span data-ttu-id="0bdc6-129">**msbuild -t:checkuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="0bdc6-129">**msbuild -t:checkuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="0bdc6-130">Dopo aver eseguito **updateuid**, i file devono contenere Gli Uid.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-130">After running **updateuid**, your files should contain Uids.</span></span> <span data-ttu-id="0bdc6-131">Ad esempio, il file Pane1.xaml di HelloApp dovrebbe includere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-131">For example, in the Pane1.xaml file of HelloApp, you should find the following:</span></span>  
  
     `<StackPanel x:Uid="StackPanel_1">`  
  
     `<TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>`  
  
     `<TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>`  
  
     `</StackPanel>`  
  
<a name="create_dll"></a>
## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="0bdc6-132">Creare l'assembly satellite per le risorse della lingua di sistema</span><span class="sxs-lookup"><span data-stu-id="0bdc6-132">Create the Neutral Language Resources Satellite Assembly</span></span>  
 <span data-ttu-id="0bdc6-133">Dopo aver configurato l'applicazione per generare un assembly satellite per le risorse della lingua di sistema, è necessario compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-133">After the application is configured to generate a neutral language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="0bdc6-134">Viene generato l'assembly principale dell'applicazione, nonché l'assembly satellite per le risorse della lingua di sistema richiesto da LocBaml per la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-134">This generates the main application assembly, as well as the neutral language resources satellite assembly that is required by LocBaml for localization.</span></span> <span data-ttu-id="0bdc6-135">Per compilare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-135">To build the application:</span></span>  
  
1. <span data-ttu-id="0bdc6-136">Compilare HelloApp per creare una libreria a collegamento dinamico (DLL):Compile HelloApp to create a dynamic-link library (DLL):</span><span class="sxs-lookup"><span data-stu-id="0bdc6-136">Compile HelloApp to create a dynamic-link library (DLL):</span></span>  
  
     <span data-ttu-id="0bdc6-137">**msbuild helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="0bdc6-137">**msbuild helloapp.csproj**</span></span>  
  
2. <span data-ttu-id="0bdc6-138">L'assembly principale dell'applicazione appena creato, HelloApp.exe, viene inserito nella cartella seguente:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-138">The newly created main application assembly, HelloApp.exe, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\`  
  
3. <span data-ttu-id="0bdc6-139">L'assembly satellite per le risorse della lingua di sistema appena creato, HelloApp.resources.dll, viene inserito nella cartella seguente:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-139">The newly created neutral language resources satellite assembly, HelloApp.resources.dll, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\en-US\`  
  
<a name="build_locbaml"></a>
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="0bdc6-140">Compilare lo strumento LocBaml</span><span class="sxs-lookup"><span data-stu-id="0bdc6-140">Build the LocBaml Tool</span></span>  
  
1. <span data-ttu-id="0bdc6-141">Tutti i file necessari per compilare LocBaml si trovano negli esempi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bdc6-141">All the files necessary to build LocBaml are located in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] samples.</span></span> <span data-ttu-id="0bdc6-142">Scaricare i file di C, dall'esempio di [strumento LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-142">Download the C# files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
2. <span data-ttu-id="0bdc6-143">Eseguire il file di progetto (LocBaml.csproj) per compilare lo strumento dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-143">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  
  
     <span data-ttu-id="0bdc6-144">**msbuild locbaml.csproj**</span><span class="sxs-lookup"><span data-stu-id="0bdc6-144">**msbuild locbaml.csproj**</span></span>  
  
3. <span data-ttu-id="0bdc6-145">Passare alla directory Bin\Release per trovare il file eseguibile appena creato (locbaml.exe).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-145">Go to the Bin\Release directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="0bdc6-146">Esempio: C:\LocBaml\Bin\Release\locbaml.exe</span><span class="sxs-lookup"><span data-stu-id="0bdc6-146">Example:C:\LocBaml\Bin\Release\locbaml.exe.</span></span>  
  
4. <span data-ttu-id="0bdc6-147">Le opzioni che è possibile specificare quando si esegue LocBaml sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-147">The options that you can specify when you run LocBaml are as follows:</span></span>  
  
    - <span data-ttu-id="0bdc6-148">**parse** o **-p:** analizza Baml, risorse o file DLL per generare un file CSV o txt.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-148">**parse** or **-p:** Parses Baml, resources, or DLL files to generate a .csv or .txt file.</span></span>  
  
    - <span data-ttu-id="0bdc6-149">**generate** or **-g:** genera un file binario localizzato utilizzando un file tradotto.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-149">**generate** or **-g:** Generates a localized binary file by using a translated file.</span></span>  
  
    - <span data-ttu-id="0bdc6-150">**out** o **-o** -*filedirectory*] : nome del file **di** output.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-150">**out** or **-o** {*filedirectory*] **:** Output file name.</span></span>  
  
    - <span data-ttu-id="0bdc6-151">**culture** o **-cul** -*culture*] **:** Impostazioni locali degli assembly di output.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-151">**culture** or **-cul** {*culture*] **:** Locale of output assemblies.</span></span>  
  
    - <span data-ttu-id="0bdc6-152">**translation** o **-trans** -*translation.csv*] **:** File tradotto o localizzato.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-152">**translation** or **-trans** {*translation.csv*] **:** Translated or localized file.</span></span>  
  
    - <span data-ttu-id="0bdc6-153">**asmpath** o **-asmpath:** : **:** *se* [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] il codice contiene controlli personalizzati, è necessario fornire **l'asmpath** all'assembly del controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-153">**asmpath** or **-asmpath:** {*filedirectory*] **:** If your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code contains custom controls, you must supply the **asmpath** to the custom control assembly.</span></span>  
  
    - <span data-ttu-id="0bdc6-154">**nologo:** non visualizza loghi o informazioni sul copyright.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-154">**nologo:** Displays no logo or copyright information.</span></span>  
  
    - <span data-ttu-id="0bdc6-155">**verbose:** visualizza le informazioni sulla modalità dettagliata.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-155">**verbose:** Displays verbose mode information.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0bdc6-156">Se è necessario un elenco delle opzioni quando si esegue lo strumento, digitare **LocBaml.exe** e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-156">If you need a list of the options when you are running the tool, type     **LocBaml.exe** and press ENTER.</span></span>  
  
<a name="parse_dll"></a>
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="0bdc6-157">Usare LocBaml per analizzare un file</span><span class="sxs-lookup"><span data-stu-id="0bdc6-157">Use LocBaml to Parse a File</span></span>  
 <span data-ttu-id="0bdc6-158">Ora che è stato creato lo strumento LocBaml, è possibile usarlo per analizzare HelloApp.resources.dll ed estrarre il contenuto testuale che verrà localizzato.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-158">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1. <span data-ttu-id="0bdc6-159">Copiare LocBaml.exe nella cartella bin\debug dell'applicazione in cui è stato creato l'assembly principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-159">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2. <span data-ttu-id="0bdc6-160">Per analizzare il file dell'assembly satellite e archiviare l'output come file CSV, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-160">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
     <span data-ttu-id="0bdc6-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span><span class="sxs-lookup"><span data-stu-id="0bdc6-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0bdc6-162">Se il file di input, HelloApp.resources.dll, non è nella stessa directory di LocBaml.exe, spostare uno dei file in modo che entrambi siano nella stessa directory.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-162">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3. <span data-ttu-id="0bdc6-163">Quando si esegue LocBaml per analizzare i file, l'output è costituito da sette campi delimitati da virgole (file CSV) o da tabulazioni (file TXT).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-163">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="0bdc6-164">Di seguito viene visualizzato il file CSV analizzato per HelloApp.resources.dll:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-164">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="0bdc6-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="0bdc6-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="0bdc6-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span><span class="sxs-lookup"><span data-stu-id="0bdc6-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="0bdc6-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span><span class="sxs-lookup"><span data-stu-id="0bdc6-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="0bdc6-168">I campi di sette sono:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-168">The seven fields are:</span></span>  
  
   1. <span data-ttu-id="0bdc6-169">**Nome BAML**.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-169">**BAML Name**.</span></span> <span data-ttu-id="0bdc6-170">Il nome della risorsa BAML rispetto all'assembly satellite per la lingua di origine.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-170">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   2. <span data-ttu-id="0bdc6-171">**Chiave risorsa**.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-171">**Resource Key**.</span></span> <span data-ttu-id="0bdc6-172">L'identificatore della risorsa localizzata.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-172">The localized resource identifier.</span></span>  
  
   3. <span data-ttu-id="0bdc6-173">**Categoria**.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-173">**Category**.</span></span> <span data-ttu-id="0bdc6-174">Tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-174">The value type.</span></span> <span data-ttu-id="0bdc6-175">Vedere Attributi e commenti di [localizzazione](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   4. <span data-ttu-id="0bdc6-176">**Leggibilità**.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-176">**Readability**.</span></span> <span data-ttu-id="0bdc6-177">Se il valore può essere letto da un localizzatore.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-177">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="0bdc6-178">Vedere Attributi e commenti di [localizzazione](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   5. <span data-ttu-id="0bdc6-179">**Modificabilità**.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-179">**Modifiability**.</span></span> <span data-ttu-id="0bdc6-180">Se il valore può essere modificato da un localizzatore.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-180">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="0bdc6-181">Vedere Attributi e commenti di [localizzazione](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   6. <span data-ttu-id="0bdc6-182">**Commenti**.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-182">**Comments**.</span></span> <span data-ttu-id="0bdc6-183">Descrizione aggiuntiva del valore per determinarne la modalità di localizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-183">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="0bdc6-184">Vedere Attributi e commenti di [localizzazione](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-184">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   7. <span data-ttu-id="0bdc6-185">**Valore**.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-185">**Value**.</span></span> <span data-ttu-id="0bdc6-186">Il valore di testo da convertire nelle impostazioni cultura desiderate.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-186">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="0bdc6-187">La tabella seguente mostra come viene eseguito il mapping di questi campi ai valori delimitati del file CSV:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-187">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="0bdc6-188">Nome BAML</span><span class="sxs-lookup"><span data-stu-id="0bdc6-188">BAML name</span></span>|<span data-ttu-id="0bdc6-189">Chiave di risorsa</span><span class="sxs-lookup"><span data-stu-id="0bdc6-189">Resource key</span></span>|<span data-ttu-id="0bdc6-190">Category</span><span class="sxs-lookup"><span data-stu-id="0bdc6-190">Category</span></span>|<span data-ttu-id="0bdc6-191">Leggibilità</span><span class="sxs-lookup"><span data-stu-id="0bdc6-191">Readability</span></span>|<span data-ttu-id="0bdc6-192">Modificabilità</span><span class="sxs-lookup"><span data-stu-id="0bdc6-192">Modifiability</span></span>|<span data-ttu-id="0bdc6-193">Commenti</span><span class="sxs-lookup"><span data-stu-id="0bdc6-193">Comments</span></span>|<span data-ttu-id="0bdc6-194">valore</span><span class="sxs-lookup"><span data-stu-id="0bdc6-194">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="0bdc6-195">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="0bdc6-195">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="0bdc6-196">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="0bdc6-196">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="0bdc6-197">Ignora</span><span class="sxs-lookup"><span data-stu-id="0bdc6-197">Ignore</span></span>|<span data-ttu-id="0bdc6-198">FALSE</span><span class="sxs-lookup"><span data-stu-id="0bdc6-198">FALSE</span></span>|<span data-ttu-id="0bdc6-199">FALSE</span><span class="sxs-lookup"><span data-stu-id="0bdc6-199">FALSE</span></span>||<span data-ttu-id="0bdc6-200">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="0bdc6-200">#Text1;#Text2</span></span>|
   |<span data-ttu-id="0bdc6-201">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="0bdc6-201">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="0bdc6-202">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="0bdc6-202">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="0bdc6-203">nessuno</span><span class="sxs-lookup"><span data-stu-id="0bdc6-203">None</span></span>|<span data-ttu-id="0bdc6-204">TRUE</span><span class="sxs-lookup"><span data-stu-id="0bdc6-204">TRUE</span></span>|<span data-ttu-id="0bdc6-205">TRUE</span><span class="sxs-lookup"><span data-stu-id="0bdc6-205">TRUE</span></span>||<span data-ttu-id="0bdc6-206">Hello World</span><span class="sxs-lookup"><span data-stu-id="0bdc6-206">Hello World</span></span>|
   |<span data-ttu-id="0bdc6-207">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="0bdc6-207">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="0bdc6-208">Text2:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="0bdc6-208">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="0bdc6-209">nessuno</span><span class="sxs-lookup"><span data-stu-id="0bdc6-209">None</span></span>|<span data-ttu-id="0bdc6-210">TRUE</span><span class="sxs-lookup"><span data-stu-id="0bdc6-210">TRUE</span></span>|<span data-ttu-id="0bdc6-211">TRUE</span><span class="sxs-lookup"><span data-stu-id="0bdc6-211">TRUE</span></span>||<span data-ttu-id="0bdc6-212">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="0bdc6-212">Goodbye World</span></span>|
  
   <span data-ttu-id="0bdc6-213">Si noti che tutti i valori per il campo **Commenti** non contengono valori; se un campo non ha un valore, è vuoto.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-213">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="0bdc6-214">Si noti inoltre che l'elemento nella prima riga non è né leggibile né modificabile e ha "Ignora" come valore di **categoria,** il che indica che il valore non è localizzabile.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-214">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4. <span data-ttu-id="0bdc6-215">Per facilitare l'individuazione di elementi localizzabili nei file analizzati, in particolare nei file di grandi dimensioni, è possibile ordinare o filtrare gli elementi per **Categoria**, **Leggibilità**e **Modificabilità**.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-215">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="0bdc6-216">Ad esempio, è possibile escludere i valori non leggibili e non modificabili.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-216">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
<a name="translate_loc_content"></a>
## <a name="translate-the-localizable-content"></a><span data-ttu-id="0bdc6-217">Convertire il contenuto localizzabile</span><span class="sxs-lookup"><span data-stu-id="0bdc6-217">Translate the Localizable Content</span></span>  
 <span data-ttu-id="0bdc6-218">Usare gli strumenti disponibili per convertire il contenuto estratto.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-218">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="0bdc6-219">Un buon modo per eseguire questa operazione consiste nello scrivere le risorse in un file CSV e visualizzarle in Microsoft Excel, apportando modifiche di conversione all'ultima colonna (valore).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-219">A good way to do this is to write the resources to a .csv file and view them in Microsoft Excel, making translation changes to the last column (value).</span></span>  
  
<a name="merge_translations"></a>
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="0bdc6-220">Usare LocBaml per generare un nuovo file resources.dll</span><span class="sxs-lookup"><span data-stu-id="0bdc6-220">Use LocBaml to Generate a New .resources.dll File</span></span>  
 <span data-ttu-id="0bdc6-221">Il contenuto identificato analizzando HelloApp.resources.dll con LocBaml è stato convertito e deve essere reinserito nell'applicazione originale.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-221">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="0bdc6-222">Utilizzare l'opzione **generate** o **-g** per generare un nuovo file .resources.dll.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-222">Use the **generate** or **-g** option to generate a new .resources.dll file.</span></span>  
  
1. <span data-ttu-id="0bdc6-223">Usare la sintassi seguente per generare un nuovo file HelloApp.resources.dll.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-223">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="0bdc6-224">Contrassegnare le impostazioni cultura come en-US (/cul:en-US).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-224">Mark the culture as en-US (/cul:en-US).</span></span>  
  
     <span data-ttu-id="0bdc6-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span><span class="sxs-lookup"><span data-stu-id="0bdc6-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0bdc6-226">Se il file di input Hello.csv non è presente nella stessa directory del file eseguibile LocBaml.exe, spostare uno dei file in modo che entrambi siano nella stessa directory.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-226">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2. <span data-ttu-id="0bdc6-227">Sostituire il file HelloApp.resources.dll precedente nella directory C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll con il file HelloApp.resources.dll appena creato.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-227">Replace the old HelloApp.resources.dll file in the C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll directory with your newly created HelloApp.resources.dll file.</span></span>  
  
3. <span data-ttu-id="0bdc6-228">Ora "Hello World" e "Goodbye World" possono essere convertiti nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-228">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4. <span data-ttu-id="0bdc6-229">Per eseguire la conversione in una lingua diversa, usare le impostazioni cultura della lingua in cui si sta eseguendo la conversione.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-229">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="0bdc6-230">L'esempio seguente mostra come eseguire la conversione in lingua francese canadese:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-230">The following example shows how to translate to French-Canadian:</span></span>  
  
     <span data-ttu-id="0bdc6-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c://cul:fr-CA**</span><span class="sxs-lookup"><span data-stu-id="0bdc6-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span></span>  
  
5. <span data-ttu-id="0bdc6-232">Nello stesso assembly dell'assembly principale dell'applicazione, creare una nuova cartella specifica per le impostazioni cultura dove ospitare il nuovo assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-232">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="0bdc6-233">Per la lingua francese canadese, la cartella sarà fr-CA.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-233">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6. <span data-ttu-id="0bdc6-234">Copiare l'assembly satellite generato nella nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-234">Copy the generated satellite assembly to the new folder.</span></span>  
  
7. <span data-ttu-id="0bdc6-235">Per testare il nuovo assembly satellite, è necessario modificare le impostazioni cultura con cui verrà eseguita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-235">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="0bdc6-236">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-236">You can do this in one of two ways:</span></span>  
  
    - <span data-ttu-id="0bdc6-237">Modificare le impostazioni internazionali del sistema operativo (**Avvio** &#124; **Pannello di controllo** &#124; Opzioni internazionali e della **lingua**).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-237">Change your operating system's regional settings (**Start** &#124; **Control Panel** &#124; **Regional and Language Options**).</span></span>  
  
    - <span data-ttu-id="0bdc6-238">Aggiungere il codice seguente al file App.xaml.cs nell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="0bdc6-238">In your application, add the following code to App.xaml.cs:</span></span>  
  
   [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
   [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
   [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
<a name="Some_Tips_for_Using_LocBaml"></a>
## <a name="some-tips-for-using-locbaml"></a><span data-ttu-id="0bdc6-239">Alcuni suggerimenti per l'uso di LocBaml</span><span class="sxs-lookup"><span data-stu-id="0bdc6-239">Some Tips for Using LocBaml</span></span>  
  
- <span data-ttu-id="0bdc6-240">Tutti gli assembly dipendenti che definiscono i controlli personalizzati devono essere copiati nella directory locale di LocBaml o installati in Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-240">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="0bdc6-241">Ciò è necessario perché l'API di localizzazione deve avere accesso agli assembly dipendenti quando legge il codice XAML binario (BAML).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-241">This is necessary because the localization API must have access to the dependent assemblies when it reads the binary XAML (BAML).</span></span>  
  
- <span data-ttu-id="0bdc6-242">Se l'assembly principale è firmato, anche la DLL di risorse generata deve essere firmata per poter essere caricata.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-242">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
- <span data-ttu-id="0bdc6-243">La versione della DLL di risorsa localizzata deve essere sincronizzata con l'assembly principale.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-243">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>  
  
<a name="Whats_Next"></a>
## <a name="whats-next"></a><span data-ttu-id="0bdc6-244">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0bdc6-244">What's Next</span></span>  
 <span data-ttu-id="0bdc6-245">A questo punto dovrebbero essere state acquisite le conoscenze di base sull'uso dello strumento LocBaml.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-245">You should now have a basic understanding of how to use the LocBaml tool.</span></span>  <span data-ttu-id="0bdc6-246">Si dovrebbe essere in grado di creare un file che contiene UID.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-246">You should be able to make a file that contains Uids.</span></span> <span data-ttu-id="0bdc6-247">Usando lo strumento LocBaml, si dovrebbe essere in grado di analizzare un file per estrarre il contenuto localizzabile e, dopo la conversione del contenuto, generare un file resources.dll che inserisce il contenuto convertito.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-247">By using the LocBaml tool, you should be able to parse a file to extract the localizable content, and after the content is translated, you should be able to generate a .resources.dll file that merges the translated content.</span></span> <span data-ttu-id="0bdc6-248">Questo argomento non include tutti i dettagli, ma offre le informazioni necessarie per usare LocBaml per la localizzazione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-248">This topic does not include every possible detail, but you now have the knowledge necessary to use LocBaml for localizing your applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bdc6-249">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bdc6-249">See also</span></span>

- [<span data-ttu-id="0bdc6-250">Globalizzazione per WPF</span><span class="sxs-lookup"><span data-stu-id="0bdc6-250">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="0bdc6-251">Cenni preliminari sull'utilizzo del layout automatico</span><span class="sxs-lookup"><span data-stu-id="0bdc6-251">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)

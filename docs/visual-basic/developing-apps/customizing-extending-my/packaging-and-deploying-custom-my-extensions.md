---
title: Creazione del pacchetto e distribuzione delle estensioni My personalizzate
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: a2e2a6705fb3d8d4424d46d96bbf49b41e1414af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330253"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a><span data-ttu-id="f09d0-102">Pacchetto e distribuzione delle estensioni My personalizzate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f09d0-102">Package and deploy custom My extensions (Visual Basic)</span></span>

<span data-ttu-id="f09d0-103">Visual Basic fornisce un modo semplice per distribuire le estensioni dello spazio `My` dei nomi personalizzate utilizzando i modelli di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f09d0-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="f09d0-104">Se si sta creando un modello di progetto per il `My` quale le estensioni sono parte integrante del nuovo tipo di progetto, è possibile includere il `My` codice di estensione personalizzato con il progetto quando si esporta il modello.</span><span class="sxs-lookup"><span data-stu-id="f09d0-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="f09d0-105">Per altre informazioni sull'esportazione di modelli di progetto, vedere [procedura: creare modelli di progetto](/visualstudio/ide/how-to-create-project-templates).</span><span class="sxs-lookup"><span data-stu-id="f09d0-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>

<span data-ttu-id="f09d0-106">Se l'estensione `My` personalizzata si trova in un unico file di codice, è possibile esportare il file come modello di elemento che gli utenti possono aggiungere a qualsiasi tipo di Visual Basic progetto.</span><span class="sxs-lookup"><span data-stu-id="f09d0-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="f09d0-107">È quindi possibile personalizzare il modello di elemento per abilitare funzionalità e comportamenti aggiuntivi per l' `My` estensione personalizzata in un progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f09d0-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="f09d0-108">Di seguito sono riportate alcune funzionalità:</span><span class="sxs-lookup"><span data-stu-id="f09d0-108">Those capabilities include the following:</span></span>

- <span data-ttu-id="f09d0-109">Consentire agli utenti di gestire l' `My` estensione personalizzata dalla pagina **estensioni My** di progettazione progetti Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f09d0-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>

- <span data-ttu-id="f09d0-110">Aggiunta automatica dell'estensione `My` personalizzata quando un riferimento a un assembly specificato viene aggiunto a un progetto.</span><span class="sxs-lookup"><span data-stu-id="f09d0-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>

- <span data-ttu-id="f09d0-111">Nascondere il `My` modello di elemento di estensione nella finestra di dialogo **Aggiungi elemento** in modo che non sia incluso nell'elenco di elementi del progetto.</span><span class="sxs-lookup"><span data-stu-id="f09d0-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>

<span data-ttu-id="f09d0-112">In questo argomento viene illustrato come creare un `My` pacchetto di un'estensione personalizzata come modello di elemento nascosto che può essere gestito dalla pagina **estensioni My** della finestra di progettazione del progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f09d0-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="f09d0-113">L'estensione `My` personalizzata può inoltre essere aggiunta automaticamente quando un riferimento a un assembly specificato viene aggiunto a un progetto.</span><span class="sxs-lookup"><span data-stu-id="f09d0-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>

## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="f09d0-114">Creare un'estensione per lo spazio dei nomi My</span><span class="sxs-lookup"><span data-stu-id="f09d0-114">Create a My namespace extension</span></span>

<span data-ttu-id="f09d0-115">Il primo passaggio nella creazione di un pacchetto di distribuzione per `My` un'estensione personalizzata consiste nel creare l'estensione come singolo file di codice.</span><span class="sxs-lookup"><span data-stu-id="f09d0-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="f09d0-116">Per informazioni dettagliate e istruzioni su come creare un'estensione `My` personalizzata, vedere [estensione dello spazio dei nomi My in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="f09d0-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>

## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="f09d0-117">Esportare un'estensione dello spazio dei nomi My come modello di elemento</span><span class="sxs-lookup"><span data-stu-id="f09d0-117">Export a My namespace extension as an item template</span></span>

<span data-ttu-id="f09d0-118">Quando si dispone di un file di codice che `My` include l'estensione dello spazio dei nomi, è possibile esportare il file di codice come modello di elemento di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f09d0-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="f09d0-119">Per istruzioni su come esportare un file come modello di elemento di Visual Studio, vedere [procedura: creare modelli di elementi](/visualstudio/ide/how-to-create-item-templates).</span><span class="sxs-lookup"><span data-stu-id="f09d0-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>

> [!NOTE]
> <span data-ttu-id="f09d0-120">Se l' `My` estensione dello spazio dei nomi ha una dipendenza da un assembly specifico, è possibile personalizzare il modello di elemento `My` per installare automaticamente l'estensione dello spazio dei nomi quando viene aggiunto un riferimento a tale assembly.</span><span class="sxs-lookup"><span data-stu-id="f09d0-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="f09d0-121">Sarà quindi necessario escludere il riferimento all'assembly quando si esporta il file di codice come modello di elemento di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f09d0-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>

## <a name="customize-the-item-template"></a><span data-ttu-id="f09d0-122">Personalizzare il modello di elemento</span><span class="sxs-lookup"><span data-stu-id="f09d0-122">Customize the item template</span></span>

<span data-ttu-id="f09d0-123">È possibile abilitare il modello di elemento per la gestione dalla pagina **estensioni My** della finestra di progettazione del progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f09d0-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="f09d0-124">È anche possibile abilitare l'aggiunta automatica del modello di elemento quando un riferimento a un assembly specificato viene aggiunto a un progetto.</span><span class="sxs-lookup"><span data-stu-id="f09d0-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="f09d0-125">Per abilitare queste personalizzazioni, si aggiungerà un nuovo file, denominato file CustomData, al modello e quindi si aggiungerà un nuovo elemento al file XML nel file con estensione vstemplate.</span><span class="sxs-lookup"><span data-stu-id="f09d0-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>

### <a name="add-the-customdata-file"></a><span data-ttu-id="f09d0-126">Aggiungere il file CustomData</span><span class="sxs-lookup"><span data-stu-id="f09d0-126">Add the CustomData file</span></span>

<span data-ttu-id="f09d0-127">Il file CustomData è un file di testo con estensione del nome di file. CustomData (il nome del file può essere impostato su qualsiasi valore significativo per il modello) e che contiene XML.</span><span class="sxs-lookup"><span data-stu-id="f09d0-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="f09d0-128">Il codice XML nel file CustomData indica Visual Basic di includere l' `My` estensione quando gli utenti usano la pagina **estensioni My** della finestra di progettazione del progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f09d0-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="f09d0-129">Facoltativamente, è possibile aggiungere l' `AssemblyFullName>` attributo <al file XML del file CustomData.</span><span class="sxs-lookup"><span data-stu-id="f09d0-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="f09d0-130">In questo modo si indica Visual Basic di installare automaticamente `My` l'estensione personalizzata quando un riferimento a un assembly specifico viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="f09d0-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="f09d0-131">È possibile usare qualsiasi editor di testo o editor XML per creare il file CustomData e quindi aggiungerlo alla cartella compressa del modello di elemento (file zip).</span><span class="sxs-lookup"><span data-stu-id="f09d0-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>

<span data-ttu-id="f09d0-132">Il codice XML seguente, ad esempio, Mostra il contenuto di un file CustomData che aggiungerà l'elemento del modello alla cartella My Extensions di un progetto Visual Basic quando un riferimento all'assembly Microsoft. VisualBasic. PowerPacks. vs. dll viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="f09d0-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

<span data-ttu-id="f09d0-133">Il file CustomData contiene un elemento `VBMyExtensionTemplate>` <con attributi elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f09d0-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>

|<span data-ttu-id="f09d0-134">Attributo</span><span class="sxs-lookup"><span data-stu-id="f09d0-134">Attribute</span></span>|<span data-ttu-id="f09d0-135">Description</span><span class="sxs-lookup"><span data-stu-id="f09d0-135">Description</span></span>|
|---|---|
|`ID`|<span data-ttu-id="f09d0-136">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f09d0-136">Required.</span></span> <span data-ttu-id="f09d0-137">Identificatore univoco per l'estensione.</span><span class="sxs-lookup"><span data-stu-id="f09d0-137">A unique identifier for the extension.</span></span> <span data-ttu-id="f09d0-138">Se l'estensione con questo ID è già stata aggiunta al progetto, all'utente non verrà richiesto di aggiungerla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="f09d0-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|
|`Version`|<span data-ttu-id="f09d0-139">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f09d0-139">Required.</span></span> <span data-ttu-id="f09d0-140">Numero di versione per il modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="f09d0-140">A version number for the item template.</span></span>|
|`AssemblyFullName`|<span data-ttu-id="f09d0-141">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f09d0-141">Optional.</span></span> <span data-ttu-id="f09d0-142">Nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f09d0-142">An assembly name.</span></span> <span data-ttu-id="f09d0-143">Quando un riferimento a questo assembly viene aggiunto al progetto, all'utente viene richiesto di aggiungere l' `My` estensione da questo modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="f09d0-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="f09d0-144">Aggiungere l' \<elemento CustomDataSignature> al file con estensione vstemplate</span><span class="sxs-lookup"><span data-stu-id="f09d0-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>

<span data-ttu-id="f09d0-145">Per identificare il modello di elemento di Visual Studio `My` come estensione dello spazio dei nomi, è necessario modificare anche il file vstemplate per il modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="f09d0-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="f09d0-146">È necessario aggiungere un `<CustomDataSignature>` elemento all' `<TemplateData>` elemento.</span><span class="sxs-lookup"><span data-stu-id="f09d0-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="f09d0-147">L' `<CustomDataSignature>` elemento deve contenere il testo `Microsoft.VisualBasic.MyExtension`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f09d0-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

<span data-ttu-id="f09d0-148">Non è possibile modificare direttamente i file in una cartella compressa (file con estensione zip).</span><span class="sxs-lookup"><span data-stu-id="f09d0-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="f09d0-149">È necessario copiare il file con estensione vstemplate dalla cartella compressa, modificarlo e quindi sostituire il file con estensione vstemplate nella cartella compressa con la copia aggiornata.</span><span class="sxs-lookup"><span data-stu-id="f09d0-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>

<span data-ttu-id="f09d0-150">Nell'esempio seguente viene illustrato il contenuto di un file con estensione vstemplate per `<CustomDataSignature>` il quale è stato aggiunto l'elemento.</span><span class="sxs-lookup"><span data-stu-id="f09d0-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>

```xml
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">
  <TemplateData>
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>
    <Name>MyPrinterInfo</Name>
    <Description>Custom My Extensions Item Template</Description>
    <ProjectType>VisualBasic</ProjectType>
    <SortOrder>10</SortOrder>
    <Icon>__TemplateIcon.ico</Icon>
    <CustomDataSignature      >Microsoft.VisualBasic.MyExtension</CustomDataSignature>
  </TemplateData>
  <TemplateContent>
    <References />
    <ProjectItem SubType="Code"
                 TargetFileName="$fileinputname$.vb"
                 ReplaceParameters="true"
     >MyCustomExtensionModule.vb</ProjectItem>
  </TemplateContent>
</VSTemplate>
```

## <a name="install-the-template"></a><span data-ttu-id="f09d0-151">Installare il modello</span><span class="sxs-lookup"><span data-stu-id="f09d0-151">Install the template</span></span>

<span data-ttu-id="f09d0-152">Per installare il modello, è possibile copiare la cartella compressa (file*zip* ) nella cartella dei modelli di elemento Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f09d0-152">To install the template, you can copy the compressed folder (*.zip* file) to the Visual Basic item templates folder.</span></span> <span data-ttu-id="f09d0-153">Per impostazione predefinita, i modelli di elemento utente si trovano in *%USERPROFILE%\Documents\Visual Studio \<\>versione \Templates\ItemTemplates\Visual di base*.</span><span class="sxs-lookup"><span data-stu-id="f09d0-153">By default, user item templates are located in *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span></span> <span data-ttu-id="f09d0-154">In alternativa, è possibile pubblicare il modello come file di Programma di installazione di Visual Studio (*VSI*).</span><span class="sxs-lookup"><span data-stu-id="f09d0-154">Alternatively, you can publish the template as a Visual Studio Installer (*.vsi*) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="f09d0-155">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f09d0-155">See also</span></span>

- [<span data-ttu-id="f09d0-156">Estensione dello spazio dei nomi My in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f09d0-156">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [<span data-ttu-id="f09d0-157">Estensione del modello di applicazione Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f09d0-157">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [<span data-ttu-id="f09d0-158">Personalizzazione degli oggetti disponibili in My</span><span class="sxs-lookup"><span data-stu-id="f09d0-158">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [<span data-ttu-id="f09d0-159">Pagina Estensioni My, Creazione progetti</span><span class="sxs-lookup"><span data-stu-id="f09d0-159">My Extensions Page, Project Designer</span></span>](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)

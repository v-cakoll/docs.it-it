---
title: Assemblaggio e distribuzione delle estensioni My (Visual Basic) personalizzate
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 4212f58c39f63be6ba20c3b79e5d9c98d0615c5e
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2018
ms.locfileid: "45649933"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a><span data-ttu-id="5fe32-102">Il pacchetto e distribuire personalizzata delle estensioni My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5fe32-102">Package and deploy custom My extensions (Visual Basic)</span></span>

<span data-ttu-id="5fe32-103">Visual Basic fornisce un modo semplice la distribuzione personalizzata `My` estensioni spazio dei nomi con i modelli di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5fe32-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="5fe32-104">Se si sta creando un modello di progetto per il quale il `My` le estensioni sono parte integrante del nuovo tipo di progetto, è possibile includere solo personalizzata `My` codice dell'estensione per il progetto quando si esporta il modello.</span><span class="sxs-lookup"><span data-stu-id="5fe32-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="5fe32-105">Per altre informazioni sull'esportazione di modelli di progetto, vedere [procedura: creare modelli di progetto](/visualstudio/ide/how-to-create-project-templates).</span><span class="sxs-lookup"><span data-stu-id="5fe32-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>

<span data-ttu-id="5fe32-106">Se personalizzata `My` estensione è in un singolo file di codice, è possibile esportare il file come modello di elemento che possono essere aggiunte a qualsiasi tipo di progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5fe32-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="5fe32-107">È quindi possibile personalizzare il modello di elemento per abilitare funzionalità aggiuntive e il comportamento per personalizzata `My` estensione in un progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5fe32-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="5fe32-108">Tali funzionalità includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5fe32-108">Those capabilities include the following:</span></span>

- <span data-ttu-id="5fe32-109">Consentire agli utenti di gestire personalizzata `My` estensione dal **estensioni My** pagina della finestra di progettazione di progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5fe32-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>

- <span data-ttu-id="5fe32-110">Aggiunta automatica personalizzati `My` estensione quando un riferimento a un assembly specificato viene aggiunto a un progetto.</span><span class="sxs-lookup"><span data-stu-id="5fe32-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>

- <span data-ttu-id="5fe32-111">Nascondendo il `My` modello di elemento di estensione nel **Aggiungi elemento** finestra di dialogo in modo che non è incluso nell'elenco di elementi di progetto.</span><span class="sxs-lookup"><span data-stu-id="5fe32-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>

<span data-ttu-id="5fe32-112">Questo argomento viene illustrato come creare un pacchetto personalizzato `My` estensione come un modello di elemento nascosti che può essere gestito dal **estensioni My** pagina della finestra di progettazione di progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5fe32-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="5fe32-113">L'oggetto personalizzato `My` estensione può inoltre aggiunti automaticamente quando viene aggiunto a un progetto un riferimento a un assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="5fe32-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>

## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="5fe32-114">Creare una My extension dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="5fe32-114">Create a My namespace extension</span></span>

<span data-ttu-id="5fe32-115">Il primo passaggio nella creazione di un pacchetto di distribuzione per un oggetto personalizzato `My` estensione consiste nel creare l'estensione come un singolo file di codice.</span><span class="sxs-lookup"><span data-stu-id="5fe32-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="5fe32-116">Per informazioni dettagliate e informazioni aggiuntive su come creare una classe personalizzata `My` estensione, vedere [estendendo il Namespace My in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="5fe32-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>

## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="5fe32-117">Esportare una My extension dello spazio dei nomi come un modello di elemento</span><span class="sxs-lookup"><span data-stu-id="5fe32-117">Export a My namespace extension as an item template</span></span>

<span data-ttu-id="5fe32-118">Dopo aver creato un file di codice che include il `My` estensione dello spazio dei nomi, è possibile esportare il file di codice come un modello di elemento di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5fe32-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="5fe32-119">Per istruzioni su come esportare un file come un modello di elemento di Visual Studio, vedere [procedura: creare modelli di elementi](/visualstudio/ide/how-to-create-item-templates).</span><span class="sxs-lookup"><span data-stu-id="5fe32-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>

> [!NOTE]
> <span data-ttu-id="5fe32-120">Se il `My` estensione dello spazio dei nomi presenta una dipendenza da un particolare assembly, è possibile personalizzare il modello di elemento per installare automaticamente il `My` estensione dello spazio dei nomi quando viene aggiunto un riferimento a tale assembly.</span><span class="sxs-lookup"><span data-stu-id="5fe32-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="5fe32-121">Di conseguenza, è consigliabile escludere tale riferimento all'assembly quando si esporta il file di codice come un modello di elemento di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5fe32-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>

## <a name="customize-the-item-template"></a><span data-ttu-id="5fe32-122">Personalizzare il modello di elemento</span><span class="sxs-lookup"><span data-stu-id="5fe32-122">Customize the item template</span></span>

<span data-ttu-id="5fe32-123">È possibile abilitare il modello di elemento essere gestiti dal **estensioni My** pagina della finestra di progettazione di progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5fe32-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="5fe32-124">È anche possibile abilitare il modello di elemento che verrà aggiunta automaticamente quando viene aggiunto a un progetto un riferimento a un assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="5fe32-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="5fe32-125">Per abilitare queste personalizzazioni, si verrà aggiungere un nuovo file, chiamato CustomData, al modello e quindi aggiungere un nuovo elemento al codice XML nel file con estensione vstemplate.</span><span class="sxs-lookup"><span data-stu-id="5fe32-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>

### <a name="add-the-customdata-file"></a><span data-ttu-id="5fe32-126">Aggiungere il file. CustomData</span><span class="sxs-lookup"><span data-stu-id="5fe32-126">Add the CustomData file</span></span>

<span data-ttu-id="5fe32-127">Il file CustomData è un file di testo con un'estensione di. CustomData (il nome del file può essere impostato su un valore significativo al modello) e che contiene XML.</span><span class="sxs-lookup"><span data-stu-id="5fe32-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="5fe32-128">Il codice XML nel file di CustomData indica a Visual Basic per includere il `My` estensione quando gli utenti usano i **estensioni My** pagina della finestra di progettazione di progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5fe32-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="5fe32-129">È possibile aggiungere facoltativamente il <`AssemblyFullName>` dell'attributo XML del file CustomData.</span><span class="sxs-lookup"><span data-stu-id="5fe32-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="5fe32-130">Indica a Visual Basic per l'installazione automatica personalizzato `My` estensione quando un riferimento a un determinato assembly viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="5fe32-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="5fe32-131">È possibile usare qualsiasi editor di testo o editor XML per creare il file CustomData e quindi aggiungerlo alla cartella compressa del modello di elemento (file con estensione zip).</span><span class="sxs-lookup"><span data-stu-id="5fe32-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>

<span data-ttu-id="5fe32-132">Ad esempio, il codice XML seguente mostra il contenuto di un file di CustomData che verrà aggiunto l'elemento di modello nella cartella estensioni personali di un progetto di Visual Basic quando un riferimento all'assembly Microsoft.VisualBasic.PowerPacks.Vs.dll viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="5fe32-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

<span data-ttu-id="5fe32-133">Il file di CustomData contiene una <`VBMyExtensionTemplate>` elemento che ha gli attributi elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5fe32-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>

|<span data-ttu-id="5fe32-134">Attributo</span><span class="sxs-lookup"><span data-stu-id="5fe32-134">Attribute</span></span>|<span data-ttu-id="5fe32-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5fe32-135">Description</span></span>|
|---|---|
|`ID`|<span data-ttu-id="5fe32-136">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5fe32-136">Required.</span></span> <span data-ttu-id="5fe32-137">Identificatore univoco per l'estensione.</span><span class="sxs-lookup"><span data-stu-id="5fe32-137">A unique identifier for the extension.</span></span> <span data-ttu-id="5fe32-138">Se l'estensione con questo ID è già stato aggiunto al progetto, l'utente non richiederà aggiungerlo nuovamente.</span><span class="sxs-lookup"><span data-stu-id="5fe32-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|
|`Version`|<span data-ttu-id="5fe32-139">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5fe32-139">Required.</span></span> <span data-ttu-id="5fe32-140">Un numero di versione per il modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="5fe32-140">A version number for the item template.</span></span>|
|`AssemblyFullName`|<span data-ttu-id="5fe32-141">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5fe32-141">Optional.</span></span> <span data-ttu-id="5fe32-142">Nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="5fe32-142">An assembly name.</span></span> <span data-ttu-id="5fe32-143">Quando un riferimento a questo assembly viene aggiunto al progetto, l'utente verrà richiesto di aggiungere il `My` estensione da questo modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="5fe32-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="5fe32-144">Aggiungere il \<CustomDataSignature > elemento del file con estensione vstemplate</span><span class="sxs-lookup"><span data-stu-id="5fe32-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>

<span data-ttu-id="5fe32-145">Per identificare il modello di elemento di Visual Studio come un `My` estensione dello spazio dei nomi, è anche necessario modificare il file con estensione vstemplate per il modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="5fe32-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="5fe32-146">È necessario aggiungere un `<CustomDataSignature>` elemento per il `<TemplateData>` elemento.</span><span class="sxs-lookup"><span data-stu-id="5fe32-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="5fe32-147">Il `<CustomDataSignature>` elemento deve contenere il testo `Microsoft.VisualBasic.MyExtension`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5fe32-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

<span data-ttu-id="5fe32-148">Non è possibile modificare direttamente i file in una cartella compressa (zip).</span><span class="sxs-lookup"><span data-stu-id="5fe32-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="5fe32-149">È necessario copiare il file con estensione vstemplate dalla cartella compressa, modificarlo e quindi sostituire il file con estensione vstemplate nella cartella compressa con la copia aggiornata.</span><span class="sxs-lookup"><span data-stu-id="5fe32-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>

<span data-ttu-id="5fe32-150">L'esempio seguente mostra il contenuto di un file con estensione vstemplate che contiene il `<CustomDataSignature>` elemento aggiunto.</span><span class="sxs-lookup"><span data-stu-id="5fe32-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>

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

## <a name="install-the-template"></a><span data-ttu-id="5fe32-151">Installare il modello</span><span class="sxs-lookup"><span data-stu-id="5fe32-151">Install the template</span></span>

<span data-ttu-id="5fe32-152">Per installare il modello, è possibile copiare la cartella compressa (*zip* file) nella cartella dei modelli di elemento Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5fe32-152">To install the template, you can copy the compressed folder (*.zip* file) to the Visual Basic item templates folder.</span></span> <span data-ttu-id="5fe32-153">Per impostazione predefinita, i modelli di elemento utente si trovano *%USERPROFILE%\Documents\Visual Studio \<versione\>\Templates\ItemTemplates\Visual Basic*.</span><span class="sxs-lookup"><span data-stu-id="5fe32-153">By default, user item templates are located in *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span></span> <span data-ttu-id="5fe32-154">In alternativa, è possibile pubblicare il modello come un programma di installazione di Visual Studio (*vsi*) file.</span><span class="sxs-lookup"><span data-stu-id="5fe32-154">Alternatively, you can publish the template as a Visual Studio Installer (*.vsi*) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fe32-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fe32-155">See also</span></span>

- [<span data-ttu-id="5fe32-156">Estensione dello spazio dei nomi My in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5fe32-156">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [<span data-ttu-id="5fe32-157">Estensione del modello di applicazione Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5fe32-157">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [<span data-ttu-id="5fe32-158">Personalizzazione degli oggetti disponibili in My</span><span class="sxs-lookup"><span data-stu-id="5fe32-158">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [<span data-ttu-id="5fe32-159">Pagina Estensioni My, Creazione progetti</span><span class="sxs-lookup"><span data-stu-id="5fe32-159">My Extensions Page, Project Designer</span></span>](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)

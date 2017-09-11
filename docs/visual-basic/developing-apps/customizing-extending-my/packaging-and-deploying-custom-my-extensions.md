---
title: Assemblaggio e distribuzione personalizzate estensioni My (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My namespace, customizing
- My namespace
- My namespace, extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 81483722227873d1b145219ae5c4326d841ff876
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="packaging-and-deploying-custom-my-extensions-visual-basic"></a><span data-ttu-id="e7930-102">Assemblaggio e distribuzione personalizzate estensioni My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7930-102">Packaging and deploying custom My extensions (Visual Basic)</span></span>
<span data-ttu-id="e7930-103">Visual Basic fornisce un modo semplice per la distribuzione personalizzata `My` estensioni dello spazio dei nomi utilizzando modelli di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e7930-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="e7930-104">Se si sta creando un modello di progetto per il quale il `My` le estensioni sono parte integrante del nuovo tipo di progetto, è possibile includere personalizzato `My` codice di estensione con il progetto quando si esporta il modello.</span><span class="sxs-lookup"><span data-stu-id="e7930-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="e7930-105">Per ulteriori informazioni sull'esportazione di modelli di progetto, vedere [procedura: creare modelli di progetto](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398).</span><span class="sxs-lookup"><span data-stu-id="e7930-105">For more information about exporting project templates, see [How to: Create Project Templates](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398).</span></span>  
  
 <span data-ttu-id="e7930-106">Se personalizzato `My` estensione è in un singolo file di codice, è possibile esportare il file come modello di elemento che possono essere aggiunte a qualsiasi tipo di progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e7930-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="e7930-107">È quindi possibile personalizzare il modello di elemento per abilitare funzionalità aggiuntive e il comportamento per personalizzato `My` estensione in un progetto di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e7930-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="e7930-108">Tali funzionalità includono:</span><span class="sxs-lookup"><span data-stu-id="e7930-108">Those capabilities include the following:</span></span>  
  
-   <span data-ttu-id="e7930-109">Consentendo agli utenti di gestire personalizzato `My` dall'estensione di **estensioni My** pagina della finestra di progettazione di progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e7930-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>  
  
-   <span data-ttu-id="e7930-110">Aggiunta automatica personalizzati `My` estensione quando un riferimento a un assembly specificato viene aggiunto a un progetto.</span><span class="sxs-lookup"><span data-stu-id="e7930-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>  
  
-   <span data-ttu-id="e7930-111">Nascondere il `My` modello di elemento di estensione nel **Aggiungi elemento** nella finestra di dialogo in modo che non è incluso nell'elenco di elementi di progetto.</span><span class="sxs-lookup"><span data-stu-id="e7930-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>  
  
 <span data-ttu-id="e7930-112">In questo argomento viene illustrato come creare un pacchetto personalizzato `My` estensione come un modello di elemento nascosto che può essere gestito dal **estensioni My** pagina della finestra di progettazione di progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e7930-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="e7930-113">Personalizzata `My` estensione può anche essere aggiunta automaticamente quando un riferimento a un assembly specificato viene aggiunto a un progetto.</span><span class="sxs-lookup"><span data-stu-id="e7930-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>  
  
## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="e7930-114">Creare un'estensione dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="e7930-114">Create a My namespace extension</span></span>  
 <span data-ttu-id="e7930-115">Il primo passaggio nella creazione di un pacchetto di distribuzione per un oggetto personalizzato `My` estensione consiste nel creare l'estensione come un singolo file di codice.</span><span class="sxs-lookup"><span data-stu-id="e7930-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="e7930-116">Per informazioni dettagliate e istruzioni su come creare un oggetto personalizzato `My` estensione, vedere [estensione di My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="e7930-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>  
  
## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="e7930-117">Esportare un'estensione dello spazio dei nomi come un modello di elemento</span><span class="sxs-lookup"><span data-stu-id="e7930-117">Export a My namespace extension as an item template</span></span>  
 <span data-ttu-id="e7930-118">Dopo aver creato un file di codice che include il `My` estensione dello spazio dei nomi, è possibile esportare il file di codice come modello di elemento Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e7930-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="e7930-119">Per istruzioni su come esportare un file come modello di elemento Visual Studio, vedere [procedura: creare modelli di elemento](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5).</span><span class="sxs-lookup"><span data-stu-id="e7930-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7930-120">Se il `My` estensione dello spazio dei nomi ha una dipendenza su un particolare assembly, è possibile personalizzare il modello di elemento per installare automaticamente il `My` estensione dello spazio dei nomi quando viene aggiunto un riferimento a tale assembly.</span><span class="sxs-lookup"><span data-stu-id="e7930-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="e7930-121">Verrà di conseguenza, si desidera escludere tale riferimento all'assembly quando si esporta il file di codice come un modello di elemento Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e7930-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>  
  
## <a name="customize-the-item-template"></a><span data-ttu-id="e7930-122">Personalizzare il modello di elemento</span><span class="sxs-lookup"><span data-stu-id="e7930-122">Customize the item template</span></span>  
 <span data-ttu-id="e7930-123">È possibile attivare il modello di elemento dal **estensioni My** pagina della finestra di progettazione di progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e7930-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="e7930-124">È inoltre possibile abilitare il modello di elemento da aggiungere automaticamente quando un riferimento a un assembly specificato viene aggiunto a un progetto.</span><span class="sxs-lookup"><span data-stu-id="e7930-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="e7930-125">Per abilitare queste personalizzazioni, si verrà aggiungere un nuovo file, chiamato CustomData, per il modello e quindi aggiungere un nuovo elemento al codice XML nel file. vstemplate.</span><span class="sxs-lookup"><span data-stu-id="e7930-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>  
  
### <a name="add-the-customdata-file"></a><span data-ttu-id="e7930-126">Aggiungere il file CustomData</span><span class="sxs-lookup"><span data-stu-id="e7930-126">Add the CustomData file</span></span>  
 <span data-ttu-id="e7930-127">Il file CustomData è un file di testo con un'estensione di. CustomData (il nome del file può essere impostato su qualsiasi valore significativo per il modello) e che contiene il codice XML.</span><span class="sxs-lookup"><span data-stu-id="e7930-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="e7930-128">Il codice XML nel file CustomData indica di includere il `My` estensione quando gli utenti utilizzeranno il **estensioni My** pagina della finestra di progettazione di progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e7930-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="e7930-129">È possibile aggiungere facoltativamente il `AssemblyFullName>` attributo XML del file CustomData.</span><span class="sxs-lookup"><span data-stu-id="e7930-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="e7930-130">Ciò indica a Visual Basic per installare automaticamente personalizzato `My` estensione quando un riferimento a un particolare assembly viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="e7930-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="e7930-131">È possibile utilizzare qualsiasi editor di testo o editor XML per creare il file CustomData e quindi aggiungerlo alla cartella compressa del modello di elemento (file con estensione zip).</span><span class="sxs-lookup"><span data-stu-id="e7930-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>  
  
 <span data-ttu-id="e7930-132">Ad esempio, il codice XML seguente viene illustrato il contenuto di un file CustomData che consentiranno di aggiungere l'elemento del modello nella cartella Estensioni My di un progetto di Visual Basic quando un riferimento all'assembly Microsoft.VisualBasic.PowerPacks.Vs.dll viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="e7930-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>  
  
```  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 <span data-ttu-id="e7930-133">Il file CustomData contiene un `VBMyExtensionTemplate>` elemento con attributi, come indicato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e7930-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>  
  
|<span data-ttu-id="e7930-134">Attributo</span><span class="sxs-lookup"><span data-stu-id="e7930-134">Attribute</span></span>|<span data-ttu-id="e7930-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7930-135">Description</span></span>|  
|---|---|  
|`ID`|<span data-ttu-id="e7930-136">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e7930-136">Required.</span></span> <span data-ttu-id="e7930-137">Identificatore univoco per l'estensione.</span><span class="sxs-lookup"><span data-stu-id="e7930-137">A unique identifier for the extension.</span></span> <span data-ttu-id="e7930-138">Se l'estensione con questo ID è già stato aggiunto al progetto, l'utente non necessario aggiungerlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="e7930-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|  
|`Version`|<span data-ttu-id="e7930-139">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e7930-139">Required.</span></span> <span data-ttu-id="e7930-140">Numero di versione per il modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="e7930-140">A version number for the item template.</span></span>|  
|`AssemblyFullName`|<span data-ttu-id="e7930-141">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e7930-141">Optional.</span></span> <span data-ttu-id="e7930-142">Nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e7930-142">An assembly name.</span></span> <span data-ttu-id="e7930-143">Quando un riferimento a questo assembly viene aggiunto al progetto, l'utente verrà richiesto di aggiungere il `My` estensione da questo modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="e7930-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|  
  
### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="e7930-144">Aggiungere il \<CustomDataSignature > elemento del file. vstemplate</span><span class="sxs-lookup"><span data-stu-id="e7930-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>  
 <span data-ttu-id="e7930-145">Per identificare il modello di elemento Visual Studio come un `My` estensione dello spazio dei nomi, è necessario modificare anche il file. vstemplate del modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="e7930-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="e7930-146">È necessario aggiungere un `<CustomDataSignature>` elemento per il `<TemplateData>` elemento.</span><span class="sxs-lookup"><span data-stu-id="e7930-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="e7930-147">Il `<CustomDataSignature>` elemento deve contenere il testo `Microsoft.VisualBasic.MyExtension`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e7930-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>  
  
```  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 <span data-ttu-id="e7930-148">È possibile modificare direttamente i file in una cartella compressa (zip).</span><span class="sxs-lookup"><span data-stu-id="e7930-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="e7930-149">È necessario copiare il file. vstemplate dalla cartella compressa, modificarlo e quindi sostituire il file. vstemplate nella cartella compressa con la copia aggiornata.</span><span class="sxs-lookup"><span data-stu-id="e7930-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>  
  
 <span data-ttu-id="e7930-150">Nell'esempio seguente viene illustrato il contenuto di un file. vstemplate con il `<CustomDataSignature>` elemento aggiunto.</span><span class="sxs-lookup"><span data-stu-id="e7930-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>  
  
```  
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
  
## <a name="install-the-template"></a><span data-ttu-id="e7930-151">Installare il modello</span><span class="sxs-lookup"><span data-stu-id="e7930-151">Install the template</span></span>  
 <span data-ttu-id="e7930-152">Per installare il modello, è possibile copiare la cartella compressa (zip) nella cartella dei modelli di elemento Visual Basic (ad esempio, Documenti\Visual Studio 2008\Templates\Item elementi\Visual base).</span><span class="sxs-lookup"><span data-stu-id="e7930-152">To install the template, you can copy the compressed folder (.zip file) to the Visual Basic item templates folder (for example, My Documents\Visual Studio 2008\Templates\Item Templates\Visual Basic).</span></span> <span data-ttu-id="e7930-153">In alternativa, è possibile pubblicare il modello come un file di Visual Studio Installer (vsi).</span><span class="sxs-lookup"><span data-stu-id="e7930-153">Alternatively, you can publish the template as a Visual Studio Installer (.vsi) file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7930-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7930-154">See also</span></span>  
 <span data-ttu-id="e7930-155">[Estensione dello spazio dei nomi My in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="e7930-155">[Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md) </span></span>  
<span data-ttu-id="e7930-156"> [Estensione del modello di applicazione Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md) </span><span class="sxs-lookup"><span data-stu-id="e7930-156"> [Extending the Visual Basic Application Model](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md) </span></span>  
<span data-ttu-id="e7930-157"> [Personalizzazione degli oggetti sono disponibili in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md) </span><span class="sxs-lookup"><span data-stu-id="e7930-157"> [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md) </span></span>  
<span data-ttu-id="e7930-158"> [Pagina Estensioni My, Progettazione progetti](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="e7930-158"> [My Extensions Page, Project Designer](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span></span>

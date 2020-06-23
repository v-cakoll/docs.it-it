---
title: Abilitare o disabilitare i reindirizzamenti di binding generati automaticamente
description: Vedere come abilitare o disabilitare il reindirizzamento di associazione automatico. Questa funzionalità influiscono sulle app desktop e sulle app Web destinate a .NET 4.5.1 o versione successiva.
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
ms.openlocfilehash: edee95f6c3b2c2d74c4f1b68e0a65e5cb0e85f54
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105385"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="55155-104">Procedura: Abilitare e disabilitare il reindirizzamento di associazione automatico</span><span class="sxs-lookup"><span data-stu-id="55155-104">How to: Enable and Disable Automatic Binding Redirection</span></span>

<span data-ttu-id="55155-105">Quando si compilano app in Visual Studio destinate a .NET Framework 4.5.1 e versioni successive, i reindirizzamenti di associazione possono essere aggiunti automaticamente al file di configurazione dell'app per eseguire l'override dell'unificazione degli assembly.</span><span class="sxs-lookup"><span data-stu-id="55155-105">When you compile apps in Visual Studio that target the .NET Framework 4.5.1 and later versions, binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="55155-106">I reindirizzamenti di associazione vengono aggiunti se l'app o i relativi componenti fanno riferimento a più di una versione dello stesso assembly, anche se è possibile specificare manualmente i reindirizzamenti di associazione nel file di configurazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="55155-106">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="55155-107">La funzionalità di reindirizzamento automatico dell'associazione influiscono sulle app desktop e sulle app Web destinate a .NET Framework 4.5.1 o versione successiva, anche se il comportamento è leggermente diverso per un'app Web.</span><span class="sxs-lookup"><span data-stu-id="55155-107">The automatic binding redirection feature affects desktop apps and web apps that target the .NET Framework 4.5.1 or a later version, although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="55155-108">È possibile abilitare il reindirizzamento di associazione automatico se sono presenti app destinate a versioni precedenti del .NET Framework. in alternativa, è possibile disabilitare questa funzionalità se si desidera creare manualmente i reindirizzamenti di binding.</span><span class="sxs-lookup"><span data-stu-id="55155-108">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to manually author binding redirects.</span></span>

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="55155-109">Disabilitare i reindirizzamenti di binding automatici nelle app desktop</span><span class="sxs-lookup"><span data-stu-id="55155-109">Disable automatic binding redirects in desktop apps</span></span>

<span data-ttu-id="55155-110">I reindirizzamenti di binding automatici sono abilitati per impostazione predefinita per le app desktop di Windows destinate a .NET Framework 4.5.1 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="55155-110">Automatic binding redirects are enabled by default for Windows desktop apps that target the .NET Framework 4.5.1 and later versions.</span></span> <span data-ttu-id="55155-111">I reindirizzamenti di binding vengono aggiunti al file di configurazione di output (**app.config**) quando l'app viene compilata ed esegue l'override dell'unificazione di assembly che altrimenti potrebbe essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="55155-111">The binding redirects are added to the output configuration (**app.config**) file when the app is compiled and override the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="55155-112">Il file di **app.config** di origine non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="55155-112">The source **app.config** file is not modified.</span></span> <span data-ttu-id="55155-113">È possibile disabilitare questa funzionalità modificando il file di progetto per l'app o deselezionando una casella di controllo nelle proprietà del progetto in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="55155-113">You can disable this feature by modifying the project file for the app or by deselecting a checkbox in the project's properties in Visual Studio.</span></span>

### <a name="disable-through-project-properties"></a><span data-ttu-id="55155-114">Disabilitare tramite le proprietà del progetto</span><span class="sxs-lookup"><span data-stu-id="55155-114">Disable through project properties</span></span>

<span data-ttu-id="55155-115">Se si dispone di Visual Studio 2017 versione 15,7 o successiva, è possibile disabilitare facilmente i reindirizzamenti di binding generati automaticamente nelle pagine delle proprietà del progetto.</span><span class="sxs-lookup"><span data-stu-id="55155-115">If you have Visual Studio 2017 version 15.7 or later, you can easily disable autogenerated binding redirects in the project's property pages.</span></span>

1. <span data-ttu-id="55155-116">Fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="55155-116">Right-click the project in **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="55155-117">Nella pagina dell' **applicazione** deselezionare l'opzione per la **generazione automatica dei reindirizzamenti di binding** .</span><span class="sxs-lookup"><span data-stu-id="55155-117">On the **Application** page, uncheck the **Auto-generate binding redirects** option.</span></span>

3. <span data-ttu-id="55155-118">Premere **CTRL** + **S** per salvare la modifica.</span><span class="sxs-lookup"><span data-stu-id="55155-118">Press **Ctrl**+**S** to save the change.</span></span>

### <a name="disable-manually-in-the-project-file"></a><span data-ttu-id="55155-119">Disabilitare manualmente nel file di progetto</span><span class="sxs-lookup"><span data-stu-id="55155-119">Disable manually in the project file</span></span>

1. <span data-ttu-id="55155-120">Aprire il file di progetto per la modifica utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="55155-120">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="55155-121">In Visual Studio selezionare il progetto in **Esplora soluzioni**, quindi scegliere **Apri cartella in Esplora file** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="55155-121">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="55155-122">In Esplora file trovare il file di progetto (con estensione csproj o vbproj) e aprirlo nel blocco note.</span><span class="sxs-lookup"><span data-stu-id="55155-122">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="55155-123">In Visual Studio, in **Esplora soluzioni**, fare clic con il pulsante destro del mouse sul progetto e scegliere **Scarica progetto**.</span><span class="sxs-lookup"><span data-stu-id="55155-123">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="55155-124">Fare di nuovo clic con il pulsante destro del mouse sul progetto scaricato, quindi scegliere **modifica [NomeProgetto. csproj]**.</span><span class="sxs-lookup"><span data-stu-id="55155-124">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="55155-125">Nel file di progetto trovare la voce di proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="55155-125">In the project file, find the following property entry:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. <span data-ttu-id="55155-126">Modificare `true` in `false`:</span><span class="sxs-lookup"><span data-stu-id="55155-126">Change `true` to `false`:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a><span data-ttu-id="55155-127">Abilita manualmente i reindirizzamenti di binding automatici</span><span class="sxs-lookup"><span data-stu-id="55155-127">Enable automatic binding redirects manually</span></span>

<span data-ttu-id="55155-128">È possibile abilitare reindirizzamenti di binding automatici nelle app esistenti destinate a versioni precedenti del .NET Framework o nei casi in cui non viene automaticamente richiesto di aggiungere un reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="55155-128">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you're not automatically prompted to add a redirect.</span></span> <span data-ttu-id="55155-129">Se la destinazione è una versione più recente del Framework, ma non viene automaticamente richiesto di aggiungere un reindirizzamento, probabilmente si otterrà un output di compilazione che suggerisce di modificare il mapping degli assembly.</span><span class="sxs-lookup"><span data-stu-id="55155-129">If you're targeting a newer version of the framework but do not get automatically prompted to add a redirect, you'll likely get build output that suggests you remap assemblies.</span></span>

1. <span data-ttu-id="55155-130">Aprire il file di progetto per la modifica utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="55155-130">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="55155-131">In Visual Studio selezionare il progetto in **Esplora soluzioni**, quindi scegliere **Apri cartella in Esplora file** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="55155-131">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="55155-132">In Esplora file trovare il file di progetto (con estensione csproj o vbproj) e aprirlo nel blocco note.</span><span class="sxs-lookup"><span data-stu-id="55155-132">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="55155-133">In Visual Studio, in **Esplora soluzioni**, fare clic con il pulsante destro del mouse sul progetto e scegliere **Scarica progetto**.</span><span class="sxs-lookup"><span data-stu-id="55155-133">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="55155-134">Fare di nuovo clic con il pulsante destro del mouse sul progetto scaricato, quindi scegliere **modifica [NomeProgetto. csproj]**.</span><span class="sxs-lookup"><span data-stu-id="55155-134">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="55155-135">Aggiungere l'elemento seguente al primo gruppo di proprietà di configurazione (sotto il \<PropertyGroup> tag):</span><span class="sxs-lookup"><span data-stu-id="55155-135">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   <span data-ttu-id="55155-136">Di seguito è riportato un esempio di file di progetto con l'elemento inserito:</span><span class="sxs-lookup"><span data-stu-id="55155-136">The following shows an example project file with the element inserted:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
     <PropertyGroup>
       <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
       <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
       <ProjectGuid>{123334}</ProjectGuid>
       ...
       <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
     </PropertyGroup>
     ...
   </Project>
   ```

3. <span data-ttu-id="55155-137">Compilare l'app.</span><span class="sxs-lookup"><span data-stu-id="55155-137">Compile your app.</span></span>

## <a name="enable-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="55155-138">Abilitare i reindirizzamenti di binding automatici nelle app Web</span><span class="sxs-lookup"><span data-stu-id="55155-138">Enable automatic binding redirects in web apps</span></span>

<span data-ttu-id="55155-139">I reindirizzamenti di associazione automatici vengono implementati in modo diverso per le app Web.</span><span class="sxs-lookup"><span data-stu-id="55155-139">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="55155-140">Poiché è necessario modificare il file di configurazione di origine (**web.config**) per le app Web, i reindirizzamenti di binding non vengono aggiunti automaticamente al file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="55155-140">Because the source configuration (**web.config**) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="55155-141">Visual Studio notifica, tuttavia, eventuali conflitti di associazione ed è possibile aggiungere reindirizzamenti di associazione per risolverli.</span><span class="sxs-lookup"><span data-stu-id="55155-141">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="55155-142">Poiché viene sempre richiesto di aggiungere reindirizzamenti di binding, non è necessario disabilitare in modo esplicito questa funzionalità per un'app Web.</span><span class="sxs-lookup"><span data-stu-id="55155-142">Because you're always prompted to add binding redirects, you don't need to explicitly disable this feature for a web app.</span></span>

<span data-ttu-id="55155-143">Per aggiungere reindirizzamenti di binding a un file di **web.config** :</span><span class="sxs-lookup"><span data-stu-id="55155-143">To add binding redirects to a **web.config** file:</span></span>

1. <span data-ttu-id="55155-144">In Visual Studio compilare l'app e cercare eventuali avvisi di compilazione.</span><span class="sxs-lookup"><span data-stu-id="55155-144">In Visual Studio, compile the app, and check for build warnings.</span></span>

   <span data-ttu-id="55155-145">![Avviso di compilazione per conflitti di riferimenti all'assembly](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="55155-145">![Build warning for assembly reference conflicts](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>

2. <span data-ttu-id="55155-146">In caso di conflitti di associazione a livello di assembly, viene visualizzato un avviso.</span><span class="sxs-lookup"><span data-stu-id="55155-146">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="55155-147">Fare doppio clic sull'avviso oppure selezionare l'avviso e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="55155-147">Double-click the warning, or select the warning and press **Enter**.</span></span>

   <span data-ttu-id="55155-148">Viene visualizzata una finestra di dialogo che consente di aggiungere automaticamente i reindirizzamenti di binding necessari al file di **web.config** di origine.</span><span class="sxs-lookup"><span data-stu-id="55155-148">A dialog box that enables you to automatically add the necessary binding redirects to the source **web.config** file appears.</span></span>

   <span data-ttu-id="55155-149">![Finestra di dialogo dell'autorizzazione reindirizzamento associazione](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="55155-149">![Binding redirect permission dialog](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>

## <a name="see-also"></a><span data-ttu-id="55155-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55155-150">See also</span></span>

- [<span data-ttu-id="55155-151">\<bindingRedirect>Elemento</span><span class="sxs-lookup"><span data-stu-id="55155-151">\<bindingRedirect> Element</span></span>](./file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="55155-152">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="55155-152">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)

---
title: 'Procedura: abilitare e disabilitare il reindirizzamento di associazione automatico'
ms.date: 09/12/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9b9c9cbdb89ccf67942dcccee37ea410c6fa39a5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47079543"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="7a904-102">Procedura: abilitare e disabilitare il reindirizzamento di associazione automatico</span><span class="sxs-lookup"><span data-stu-id="7a904-102">How to: Enable and Disable Automatic Binding Redirection</span></span>

<span data-ttu-id="7a904-103">Quando si esegue la compilazione di App in Visual Studio che hanno come destinazione il [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] e versioni successive, i reindirizzamenti di associazione possono essere aggiunte automaticamente al file di configurazione dell'app per eseguire l'override di unificazione degli assembly.</span><span class="sxs-lookup"><span data-stu-id="7a904-103">When you compile apps in Visual Studio that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions, binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="7a904-104">I reindirizzamenti di associazione vengono aggiunti se l'app o i relativi componenti fanno riferimento a più di una versione dello stesso assembly, anche se è possibile specificare manualmente i reindirizzamenti di associazione nel file di configurazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="7a904-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="7a904-105">La funzionalità di reindirizzamento di associazione automatico influisce sulle App web e App desktop tradizionali destinate le [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] o versione successiva, anche se il comportamento è leggermente diverso per un'app web.</span><span class="sxs-lookup"><span data-stu-id="7a904-105">The automatic binding redirection feature affects traditional desktop apps and web apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] or a later version, although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="7a904-106">È possibile abilitare il reindirizzamento di associazione automatico se sono presenti app destinate alle versioni precedenti di .NET Framework o per mantenere i reindirizzamenti di associazione creati manualmente.</span><span class="sxs-lookup"><span data-stu-id="7a904-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to keep manually authored binding redirects.</span></span>

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="7a904-107">Disabilitare i reindirizzamenti di associazione automatici nelle App desktop</span><span class="sxs-lookup"><span data-stu-id="7a904-107">Disable automatic binding redirects in desktop apps</span></span>

<span data-ttu-id="7a904-108">I reindirizzamenti di associazione automatici sono abilitati per impostazione predefinita per le app desktop tradizionali destinate a [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="7a904-108">Automatic binding redirects are enabled by default for traditional desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions.</span></span> <span data-ttu-id="7a904-109">I reindirizzamenti di associazione vengono aggiunti al file di configurazione di output (app.config) quando l'applicazione viene compilata ed eseguire l'override dell'unificazione degli assembly che in caso contrario potrebbe essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="7a904-109">The binding redirects are added to the output configuration (app.config) file when the app is compiled and overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="7a904-110">Il file app.config di origine non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="7a904-110">The source app.config file is not modified.</span></span> <span data-ttu-id="7a904-111">È possibile disabilitare questa funzionalità modificando il file di progetto per l'app.</span><span class="sxs-lookup"><span data-stu-id="7a904-111">You can disable this feature by modifying the project file for the app.</span></span>

1. <span data-ttu-id="7a904-112">Aprire il file di progetto per la modifica mediante uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a904-112">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="7a904-113">In Visual Studio, selezionare il progetto in **Esplora soluzioni**, quindi scegliere **Apri cartella in Esplora File** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="7a904-113">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="7a904-114">In Esplora File, trovare il file di progetto (con estensione csproj o vbproj) e aprirlo con blocco note.</span><span class="sxs-lookup"><span data-stu-id="7a904-114">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="7a904-115">In Visual Studio, in **Esplora soluzioni**, fare clic sul progetto e scegliere **Scarica progetto**.</span><span class="sxs-lookup"><span data-stu-id="7a904-115">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="7a904-116">Fare clic nuovamente sul progetto scaricato e quindi scegliere **modifica [NomeProgetto]**.</span><span class="sxs-lookup"><span data-stu-id="7a904-116">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="7a904-117">Nel file di progetto trovare la voce di proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="7a904-117">In the project file, find the following property entry:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. <span data-ttu-id="7a904-118">Modificare `true` in `false`:</span><span class="sxs-lookup"><span data-stu-id="7a904-118">Change `true` to `false`:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a><span data-ttu-id="7a904-119">Abilitare manualmente reindirizzamenti di associazione automatici</span><span class="sxs-lookup"><span data-stu-id="7a904-119">Enable automatic binding redirects manually</span></span>

<span data-ttu-id="7a904-120">È possibile abilitare reindirizzamenti di associazione automatici nelle App esistenti che destinate alle versioni precedenti di .NET Framework o nei casi in cui viene automaticamente richiesto di aggiungere un reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="7a904-120">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you're not automatically prompted to add a redirect.</span></span> <span data-ttu-id="7a904-121">Se si ha come destinazione una versione più recente del framework, ma non automaticamente richiesto di aggiungere un reindirizzamento, probabilmente si otterrà output di compilazione che viene suggerito di che rimappare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="7a904-121">If you're targeting a newer version of the framework but do not get automatically prompted to add a redirect, you'll likely get build output that suggests you remap assemblies.</span></span>

1. <span data-ttu-id="7a904-122">Aprire il file di progetto per la modifica mediante uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a904-122">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="7a904-123">In Visual Studio, selezionare il progetto in **Esplora soluzioni**, quindi scegliere **Apri cartella in Esplora File** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="7a904-123">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="7a904-124">In Esplora File, trovare il file di progetto (con estensione csproj o vbproj) e aprirlo con blocco note.</span><span class="sxs-lookup"><span data-stu-id="7a904-124">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="7a904-125">In Visual Studio, in **Esplora soluzioni**, fare clic sul progetto e scegliere **Scarica progetto**.</span><span class="sxs-lookup"><span data-stu-id="7a904-125">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="7a904-126">Fare clic nuovamente sul progetto scaricato e quindi scegliere **modifica [NomeProgetto]**.</span><span class="sxs-lookup"><span data-stu-id="7a904-126">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="7a904-127">Aggiungere l'elemento seguente al primo gruppo di proprietà di configurazione (sotto il \<PropertyGroup > tag):</span><span class="sxs-lookup"><span data-stu-id="7a904-127">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   <span data-ttu-id="7a904-128">Di seguito viene illustrato un esempio di file di progetto con l'elemento inserito:</span><span class="sxs-lookup"><span data-stu-id="7a904-128">The following shows an example project file with the element inserted:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
       <PropertyGroup>
         <Configuration Condition=" '$(Configuration)' == ''     ">Debug</Configuration>
         <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
         <ProjectGuid>{123334}</ProjectGuid>
         ...
         <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
       </PropertyGroup>
     ...
   </Project>
   ```

3. <span data-ttu-id="7a904-129">Compilare l'app.</span><span class="sxs-lookup"><span data-stu-id="7a904-129">Compile your app.</span></span>

## <a name="enable-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="7a904-130">Abilita reindirizzamenti di associazione automatici nelle App web</span><span class="sxs-lookup"><span data-stu-id="7a904-130">Enable automatic binding redirects in web apps</span></span>

<span data-ttu-id="7a904-131">I reindirizzamenti di associazione automatici vengono implementati in modo diverso per le app Web.</span><span class="sxs-lookup"><span data-stu-id="7a904-131">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="7a904-132">Poiché il file di configurazione di origine (web.config) deve essere modificato per le app Web, i reindirizzamenti di associazione non vengono aggiunti automaticamente al file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7a904-132">Because the source configuration (web.config) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="7a904-133">Visual Studio notifica, tuttavia, eventuali conflitti di associazione ed è possibile aggiungere reindirizzamenti di associazione per risolverli.</span><span class="sxs-lookup"><span data-stu-id="7a904-133">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="7a904-134">Poiché viene sempre chiesto aggiungere reindirizzamenti di associazione, non è necessario disabilitare in modo esplicito questa funzionalità per un'app web.</span><span class="sxs-lookup"><span data-stu-id="7a904-134">Because you're always prompted to add binding redirects, you don't need to explicitly disable this feature for a web app.</span></span>

<span data-ttu-id="7a904-135">Per aggiungere reindirizzamenti di associazione in un file Web. config:</span><span class="sxs-lookup"><span data-stu-id="7a904-135">To add binding redirects to a web.config file:</span></span>

1. <span data-ttu-id="7a904-136">In Visual Studio compilare l'app e cercare eventuali avvisi di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7a904-136">In Visual Studio, compile the app, and check for build warnings.</span></span>

   <span data-ttu-id="7a904-137">![Avviso di compilazione per conflitti di riferimenti all'assembly](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="7a904-137">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>

2. <span data-ttu-id="7a904-138">In caso di conflitti di associazione a livello di assembly, viene visualizzato un avviso.</span><span class="sxs-lookup"><span data-stu-id="7a904-138">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="7a904-139">Fare doppio clic su avviso oppure selezionare l'avviso e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="7a904-139">Double-click the warning, or select the warning and press **Enter**.</span></span>

   <span data-ttu-id="7a904-140">Verrà visualizzata una finestra di dialogo che consente di aggiungere automaticamente i reindirizzamenti di associazione necessari al file web.config di origine.</span><span class="sxs-lookup"><span data-stu-id="7a904-140">A dialog box that enables you to automatically add the necessary binding redirects to the source web.config file appears.</span></span>

   <span data-ttu-id="7a904-141">![Finestra di dialogo dell'autorizzazione reindirizzamento associazione](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="7a904-141">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>

## <a name="see-also"></a><span data-ttu-id="7a904-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a904-142">See also</span></span>

- [<span data-ttu-id="7a904-143">\<bindingRedirect > elemento</span><span class="sxs-lookup"><span data-stu-id="7a904-143">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="7a904-144">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="7a904-144">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)

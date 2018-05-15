---
title: 'Procedura: abilitare e disabilitare il reindirizzamento di associazione automatico'
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2d71da1b48938f9f98221d86f0f9badee3a17919
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="ad2ca-102">Procedura: abilitare e disabilitare il reindirizzamento di associazione automatico</span><span class="sxs-lookup"><span data-stu-id="ad2ca-102">How to: Enable and Disable Automatic Binding Redirection</span></span>
<span data-ttu-id="ad2ca-103">A partire da [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], quando si compilano app destinate a [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], i reindirizzamenti di associazione possono essere aggiunti automaticamente al file di configurazione dell'app per eseguire l'override dell'unificazione degli assembly.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-103">Starting with [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], when you compile apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="ad2ca-104">I reindirizzamenti di associazione vengono aggiunti se l'app o i relativi componenti fanno riferimento a più di una versione dello stesso assembly, anche se è possibile specificare manualmente i reindirizzamenti di associazione nel file di configurazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="ad2ca-105">La funzionalità di reindirizzamento di associazione automatica interessa le app desktop e Web tradizionali destinate a [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], anche se il comportamento è leggermente diverso per un'app Web.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-105">The automatic binding redirection feature affects traditional desktop apps and web apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="ad2ca-106">È possibile abilitare il reindirizzamento di associazione automatico se sono presenti app destinate alle versioni precedenti di .NET Framework o per mantenere i reindirizzamenti di associazione creati manualmente.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to keep manually authored binding redirects.</span></span>  
  
## <a name="disabling-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="ad2ca-107">Disabilitazione dei reindirizzamenti di associazione automatici nelle app desktop</span><span class="sxs-lookup"><span data-stu-id="ad2ca-107">Disabling automatic binding redirects in desktop apps</span></span>  
 <span data-ttu-id="ad2ca-108">I reindirizzamenti di associazione automatici sono abilitati per impostazione predefinita per le app desktop tradizionali destinate a [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-108">Automatic binding redirects are enabled by default for traditional desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions.</span></span> <span data-ttu-id="ad2ca-109">I reindirizzamenti di associazione vengono aggiunti al file di configurazione di output (app.config) quando l'applicazione viene compilata ed eseguire l'override dell'unificazione degli assembly che in caso contrario potrebbe essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-109">The binding redirects are added to the output configuration (app.config) file when the app is compiled and overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="ad2ca-110">Il file app.config di origine non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-110">The source app.config file is not modified.</span></span> <span data-ttu-id="ad2ca-111">È possibile disabilitare questa funzionalità modificando il file di progetto per l'app.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-111">You can disable this feature by modifying the project file for the app.</span></span>  
  
#### <a name="to-disable-automatic-binding-redirects"></a><span data-ttu-id="ad2ca-112">Per disabilitare i reindirizzamenti di associazione automatici</span><span class="sxs-lookup"><span data-stu-id="ad2ca-112">To disable automatic binding redirects</span></span>  
  
1.  <span data-ttu-id="ad2ca-113">In Visual Studio, selezionare il progetto in **Esplora**, quindi scegliere **Apri cartella in Esplora File** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-113">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="ad2ca-114">In Esplora file trovare il file di progetto (con estensione CSPROJ o VBPROJ) e aprirlo in Blocco note.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-114">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="ad2ca-115">Nel file di progetto trovare la voce di proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="ad2ca-115">In the project file, find the following property entry:</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
4.  <span data-ttu-id="ad2ca-116">Modificare `true` in `false`:</span><span class="sxs-lookup"><span data-stu-id="ad2ca-116">Change `true` to `false`:</span></span>  
  
     `<AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>`  
  
## <a name="enabling-automatic-binding-redirects-manually"></a><span data-ttu-id="ad2ca-117">Abilitazione dei reindirizzamenti di associazione manuali</span><span class="sxs-lookup"><span data-stu-id="ad2ca-117">Enabling automatic binding redirects manually</span></span>  
 <span data-ttu-id="ad2ca-118">È possibile abilitare reindirizzamenti di associazione automatici nelle app esistenti destinate alle versioni precedenti di .NET Framework o nei casi in cui non viene automaticamente richiesto di aggiungere un reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-118">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you are not automatically prompted to add a redirect.</span></span> <span data-ttu-id="ad2ca-119">Se si usa una versione più recente di .NET Framework ma non viene automaticamente richiesto di aggiungere un reindirizzamento, verrà visualizzato un output della compilazione in cui viene suggerito di rimappare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-119">If you are targeting a newer version of the framework but do not get automatically prompted to add a redirect, you will likely get   build output that suggests you remap assemblies.</span></span>  
  
#### <a name="to-manually-add-an-automatic-binding-redirect-property"></a><span data-ttu-id="ad2ca-120">Per aggiungere manualmente una proprietà di reindirizzamento di associazione automatico</span><span class="sxs-lookup"><span data-stu-id="ad2ca-120">To manually add an automatic binding redirect property</span></span>  
  
1.  <span data-ttu-id="ad2ca-121">In Visual Studio, selezionare il progetto in **Esplora**, quindi scegliere **Apri cartella in Esplora File** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-121">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="ad2ca-122">In Esplora file trovare il file di progetto (con estensione CSPROJ o VBPROJ) e aprirlo in Blocco note.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-122">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="ad2ca-123">Aggiungere l'elemento seguente al primo gruppo di proprietà di configurazione (sotto il \<PropertyGroup > tag):</span><span class="sxs-lookup"><span data-stu-id="ad2ca-123">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
     <span data-ttu-id="ad2ca-124">Di seguito è illustrato un file di progetto di esempio con l'elemento inserito.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-124">The following shows an example project file with the element inserted.</span></span>  
  
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
  
4.  <span data-ttu-id="ad2ca-125">Compilare l'app.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-125">Compile your app.</span></span>  
  
## <a name="enabling-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="ad2ca-126">Abilitazione dei reindirizzamenti di associazione automatici nelle app Web</span><span class="sxs-lookup"><span data-stu-id="ad2ca-126">Enabling automatic binding redirects in web apps</span></span>  
 <span data-ttu-id="ad2ca-127">I reindirizzamenti di associazione automatici vengono implementati in modo diverso per le app Web.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-127">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="ad2ca-128">Poiché il file di configurazione di origine (web.config) deve essere modificato per le app Web, i reindirizzamenti di associazione non vengono aggiunti automaticamente al file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-128">Because the source configuration (web.config) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="ad2ca-129">Visual Studio notifica, tuttavia, eventuali conflitti di associazione ed è possibile aggiungere reindirizzamenti di associazione per risolverli.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-129">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="ad2ca-130">Poiché viene sempre richiesto di aggiungere reindirizzamenti di associazione, non è necessario disabilitare in modo esplicito questa funzionalità per un'app Web.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-130">Because you are always prompted to add binding redirects, you do not need to explicitly disable this feature for a web app.</span></span>  
  
#### <a name="to-add-binding-redirects-to-a-webconfig-file"></a><span data-ttu-id="ad2ca-131">Per aggiungere reindirizzamenti di associazione a un file web.config</span><span class="sxs-lookup"><span data-stu-id="ad2ca-131">To add binding redirects to a web.config file</span></span>  
  
1.  <span data-ttu-id="ad2ca-132">In Visual Studio compilare l'app e cercare eventuali avvisi di compilazione.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-132">In Visual Studio, compile the app, and check for build warnings.</span></span>  
  
     <span data-ttu-id="ad2ca-133">![Avviso di compilazione per conflitti di riferimenti all'assembly](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="ad2ca-133">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>  
  
2.  <span data-ttu-id="ad2ca-134">In caso di conflitti di associazione a livello di assembly, viene visualizzato un avviso.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-134">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="ad2ca-135">Fare doppio clic sull'avviso.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-135">Double-click the warning.</span></span> <span data-ttu-id="ad2ca-136">(Tastiera: selezionare l'avviso e premere **invio**.)</span><span class="sxs-lookup"><span data-stu-id="ad2ca-136">(Keyboard: Select the warning and press **Enter**.)</span></span>  
  
     <span data-ttu-id="ad2ca-137">Verrà visualizzata una finestra di dialogo che consente di aggiungere automaticamente i reindirizzamenti di associazione necessari al file web.config di origine.</span><span class="sxs-lookup"><span data-stu-id="ad2ca-137">A dialog box that enables you to automatically add the necessary binding redirects to the source web.config file appears.</span></span>  
  
     <span data-ttu-id="ad2ca-138">![Finestra di dialogo dell'autorizzazione reindirizzamento associazione](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="ad2ca-138">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad2ca-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad2ca-139">See Also</span></span>  
 [<span data-ttu-id="ad2ca-140">\<bindingRedirect > elemento</span><span class="sxs-lookup"><span data-stu-id="ad2ca-140">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)  
 [<span data-ttu-id="ad2ca-141">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="ad2ca-141">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)

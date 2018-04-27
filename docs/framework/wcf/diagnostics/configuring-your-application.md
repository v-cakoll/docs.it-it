---
title: Configurazione dell'applicazione
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 922b9c5c53e04719f3ed48d0ff6386f21bf83e99
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="configuring-your-application"></a><span data-ttu-id="aa484-102">Configurazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="aa484-102">Configuring Your Application</span></span>
<span data-ttu-id="aa484-103">In [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] viene utilizzato il sistema di configurazione .NET ed è possibile configurare i servizi sia nell'ambito del computer che nell'ambito dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="aa484-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="aa484-104">Le impostazioni di configurazione definite da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] si trovano nel gruppo di sezioni `<system.serviceModel>`.</span><span class="sxs-lookup"><span data-stu-id="aa484-104">Configuration settings defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are located in the `<system.serviceModel>` section group.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="aa484-105"> come configurare un servizio di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa484-105"> how to configure a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, see the following topics:</span></span>  
  
-   [<span data-ttu-id="aa484-106">Configurazione dei servizi</span><span class="sxs-lookup"><span data-stu-id="aa484-106">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [<span data-ttu-id="aa484-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="aa484-107">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="aa484-108">Le impostazioni delle configurazioni definite dall'applicazione sono definite nel gruppo di sezioni `<appSettings>`.</span><span class="sxs-lookup"><span data-stu-id="aa484-108">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="aa484-109"> le impostazioni dell'applicazione nei file di configurazione .NET, vedere [ \<appSettings >](http://go.microsoft.com/fwlink/?LinkId=95159).</span><span class="sxs-lookup"><span data-stu-id="aa484-109"> application settings in .NET configuration files, see [\<appSettings>](http://go.microsoft.com/fwlink/?LinkId=95159).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="aa484-110">Utilizzo dell’Editor di configurazione</span><span class="sxs-lookup"><span data-stu-id="aa484-110">Using the Configuration Editor</span></span>  
 <span data-ttu-id="aa484-111">Il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) consente ad amministratori e sviluppatori di creare e modificare le impostazioni di configurazione per [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizi mediante un'interfaccia utente grafica.</span><span class="sxs-lookup"><span data-stu-id="aa484-111">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)][Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services using a graphical user interface.</span></span> <span data-ttu-id="aa484-112">Con questo strumento è possibile gestire le impostazioni di associazioni, comportamenti, servizi e diagnostica di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] senza la necessità di modificare direttamente i file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="aa484-112">With this tool, you can manage settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="aa484-113">Modifica dei file di configurazione in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aa484-113">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="aa484-114">Per modificare il file di configurazione di un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizio progetto in Visual Studio, farvi clic nel **Esplora soluzioni** e scegliere il **modifica Config WCF** menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="aa484-114">To edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service project in Visual Studio, right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="aa484-115">Verrà avviata la [strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="aa484-115">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa484-116">Se si modifica il file di configurazione di un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] progetto servizio Web in Visual Studio facendo clic su esso in **Esplora soluzioni**, si noti che il **modifica Config WCF** menu di scelta rapida è mancante.</span><span class="sxs-lookup"><span data-stu-id="aa484-116">If you edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web Service project in Visual Studio by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="aa484-117">Per risolvere questo problema, fare clic su di **strumenti** menu, scegliere **Editor di configurazione del servizio WCF**.</span><span class="sxs-lookup"><span data-stu-id="aa484-117">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="aa484-118">Successivamente, è possibile fare doppio clic su un file di configurazione e usare il **modifica Config WCF** menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="aa484-118">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa484-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa484-119">See Also</span></span>  
 [<span data-ttu-id="aa484-120">Strumento Editor di configurazione (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="aa484-120">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [<span data-ttu-id="aa484-121">Configurazione dei servizi</span><span class="sxs-lookup"><span data-stu-id="aa484-121">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
 [<span data-ttu-id="aa484-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="aa484-122">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)

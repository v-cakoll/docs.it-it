---
title: 'Procedura: Installare e disinstallare i servizi Windows'
ms.date: 02/05/2019
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, apps, Windows services
- installation, Windows services
- uninstalling Windows services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
ms.openlocfilehash: 0119fee443aafd1d4215260d2cf42cec9f7eba74
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59308471"
---
# <a name="how-to-install-and-uninstall-windows-services"></a><span data-ttu-id="b6687-102">Procedura: Installare e disinstallare i servizi Windows</span><span class="sxs-lookup"><span data-stu-id="b6687-102">How to: Install and uninstall Windows services</span></span>
<span data-ttu-id="b6687-103">Se si sta sviluppando un servizio Windows con .NET Framework, è possibile installare rapidamente l'app del servizio usando l'utilità della riga di comando [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md).</span><span class="sxs-lookup"><span data-stu-id="b6687-103">If you’re developing a Windows service with the .NET Framework, you can quickly install your service app by using the [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) command-line utility.</span></span> <span data-ttu-id="b6687-104">Gli sviluppatori che vogliono rilasciare un servizio Windows che gli utenti possono installare e disinstallare devono usare InstallShield.</span><span class="sxs-lookup"><span data-stu-id="b6687-104">Developers who want to release a Windows service that users can install and uninstall should use InstallShield.</span></span> <span data-ttu-id="b6687-105">Per altre informazioni, vedere [Creare un pacchetto di installazione (client Windows)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).</span><span class="sxs-lookup"><span data-stu-id="b6687-105">For more information, see [Create an installer package (Windows client)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).</span></span>
  
> [!WARNING]
>  <span data-ttu-id="b6687-106">Se si vuole disinstallare un servizio dal computer, non seguire i passaggi di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b6687-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="b6687-107">Individuare invece il programma o il pacchetto software che ha installato il servizio e quindi scegliere **App** in Impostazioni per disinstallare tale programma.</span><span class="sxs-lookup"><span data-stu-id="b6687-107">Instead, find out which program or software package installed the service, and then choose **Apps** in Settings to uninstall that program.</span></span> <span data-ttu-id="b6687-108">Si noti che molti servizi sono parte integrante di Windows. Se vengono rimossi, il sistema potrebbe diventare instabile.</span><span class="sxs-lookup"><span data-stu-id="b6687-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>  
  
 <span data-ttu-id="b6687-109">Per usare i passaggi descritti in questo articolo, è necessario prima aggiungere un programma di installazione del servizio al servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="b6687-109">To use the steps in this article, you first need to add a service installer to your Windows service.</span></span> <span data-ttu-id="b6687-110">Per altre informazioni, vedere [Procedura dettagliata: Creare un'app di servizio di Windows](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="b6687-110">For more information, see [Walkthrough: Creating a Windows service app](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
 <span data-ttu-id="b6687-111">Non è possibile eseguire i progetti del servizio Windows direttamente dall'ambiente di sviluppo di Visual Studio premendo F5.</span><span class="sxs-lookup"><span data-stu-id="b6687-111">You can't run Windows service projects directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="b6687-112">Prima di eseguire il progetto, è necessario installare il servizio nel progetto.</span><span class="sxs-lookup"><span data-stu-id="b6687-112">Before you can run the project, you must install the service in the project.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="b6687-113">È possibile usare **Esplora server** e verificare se il servizio è stato installato o disinstallato.</span><span class="sxs-lookup"><span data-stu-id="b6687-113">You can use **Server Explorer** to verify that you've installed or uninstalled your service.</span></span> <span data-ttu-id="b6687-114">Per altre informazioni, vedere [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio) (Come usare Esplora server in Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="b6687-114">For more information, see [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span></span>
  
### <a name="install-your-service-manually"></a><span data-ttu-id="b6687-115">Installare il servizio manualmente</span><span class="sxs-lookup"><span data-stu-id="b6687-115">Install your service manually</span></span>  
  
1. <span data-ttu-id="b6687-116">Dal menu **Start** selezionare la directory **Visual Studio \<*versione*>**, quindi selezionare **Prompt dei comandi per gli sviluppatori per VS \<*versione*>**.</span><span class="sxs-lookup"><span data-stu-id="b6687-116">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>
  
     <span data-ttu-id="b6687-117">Viene visualizzato il prompt dei comandi per gli sviluppatori per Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6687-117">The Developer Command Prompt for Visual Studio appears.</span></span> 
  
2. <span data-ttu-id="b6687-118">Accedere alla directory in cui si trova il file eseguibile compilato del progetto.</span><span class="sxs-lookup"><span data-stu-id="b6687-118">Access the directory where your project's compiled executable file is located.</span></span>  
  
3. <span data-ttu-id="b6687-119">Eseguire *InstallUtil.exe* dal prompt dei comandi con l'eseguibile del progetto come parametro:</span><span class="sxs-lookup"><span data-stu-id="b6687-119">Run *InstallUtil.exe* from the command prompt with your project's executable as a parameter:</span></span>  
  
    ```console
    installutil <yourproject>.exe  
    ```  

     <span data-ttu-id="b6687-120">Se si usa il prompt dei comandi per gli sviluppatori di Visual Studio, *InstallUtil.exe* sarà nel percorso di sistema.</span><span class="sxs-lookup"><span data-stu-id="b6687-120">If you’re using the Developer Command Prompt for Visual Studio, *InstallUtil.exe* should be on the system path.</span></span> <span data-ttu-id="b6687-121">In caso contrario, è possibile aggiungerlo al percorso o usare il percorso completo per richiamarlo.</span><span class="sxs-lookup"><span data-stu-id="b6687-121">Otherwise, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="b6687-122">Questo strumento viene installato con .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<versione framework>*.</span><span class="sxs-lookup"><span data-stu-id="b6687-122">This tool is installed with the .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version>*.</span></span>
     
     <span data-ttu-id="b6687-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b6687-123">For example:</span></span>
     - <span data-ttu-id="b6687-124">Per la versione a 32 bit di .NET Framework 4 o 4.5 e versioni successive, se è la directory di installazione di Windows è *C:\Windows*, il percorso predefinito è *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="b6687-124">For the 32-bit version of the .NET Framework 4 or 4.5 and later, if your Windows installation directory is *C:\Windows*, the default path is *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>
     - <span data-ttu-id="b6687-125">Per la versione a 64 bit di .NET Framework 4 o 4.5 e versioni successive, il percorso predefinito è *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="b6687-125">For the 64-bit version of the .NET Framework 4 or 4.5 and later, the default path is *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>
  
### <a name="uninstall-your-service-manually"></a><span data-ttu-id="b6687-126">Disinstallare il servizio manualmente</span><span class="sxs-lookup"><span data-stu-id="b6687-126">Uninstall your service manually</span></span>  
  
1. <span data-ttu-id="b6687-127">Dal menu **Start** selezionare la directory **Visual Studio \<*versione*>**, quindi selezionare **Prompt dei comandi per gli sviluppatori per VS \<*versione*>**.</span><span class="sxs-lookup"><span data-stu-id="b6687-127">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>
  
     <span data-ttu-id="b6687-128">Viene visualizzato il prompt dei comandi per gli sviluppatori per Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6687-128">The Developer Command Prompt for Visual Studio appears.</span></span>  
  
2. <span data-ttu-id="b6687-129">Eseguire *InstallUtil.exe* dal prompt dei comandi con l'output del progetto come parametro:</span><span class="sxs-lookup"><span data-stu-id="b6687-129">Run *InstallUtil.exe* from the command prompt with your project's output as a parameter:</span></span>  
  
    ```console  
    installutil /u <yourproject>.exe  
    ```  
  
3. <span data-ttu-id="b6687-130">Dopo avere eliminato il file eseguibile di un servizio, è possibile che il servizio sia ancora presente nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="b6687-130">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="b6687-131">In questo caso usare il comando [sc delete](/windows-server/administration/windows-commands/sc-delete) per rimuovere la voce per il servizio dal Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="b6687-131">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6687-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6687-132">See also</span></span>

- [<span data-ttu-id="b6687-133">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="b6687-133">Introduction to Windows service applications</span></span>](../windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="b6687-134">Procedura: Creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="b6687-134">How to: Create Windows services</span></span>](../windows-services/how-to-create-windows-services.md)
- [<span data-ttu-id="b6687-135">Procedura: Aggiungere programmi di installazione all'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="b6687-135">How to: Add installers to your service application</span></span>](../windows-services/how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="b6687-136">Installutil.exe (Strumento Programma di installazione)</span><span class="sxs-lookup"><span data-stu-id="b6687-136">Installutil.exe (Installer tool)</span></span>](../tools/installutil-exe-installer-tool.md)

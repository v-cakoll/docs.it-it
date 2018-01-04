---
title: 'Procedura: installare e disinstallare servizi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, Windows Services
- installation, Windows Services
- uninstalling Windows Services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
caps.latest.revision: "19"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: bf767813f965b2c52a5061f74bbf2fab4572791b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-install-and-uninstall-services"></a><span data-ttu-id="1f27a-102">Procedura: installare e disinstallare servizi</span><span class="sxs-lookup"><span data-stu-id="1f27a-102">How to: Install and Uninstall Services</span></span>
<span data-ttu-id="1f27a-103">Se si sta sviluppando un servizio Windows con .NET Framework, è possibile installare rapidamente l'applicazione di servizio tramite un'utilità della riga di comando denominata InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="1f27a-103">If you’re developing a Windows Service by using the .NET Framework, you can quickly install your service application by using a command-line utility called InstallUtil.exe.</span></span> <span data-ttu-id="1f27a-104">Se uno sviluppatore vuole rilasciare un servizio Windows che gli utenti possono installare e disinstallare, può usare InstallShield.</span><span class="sxs-lookup"><span data-stu-id="1f27a-104">If you’re a developer who wants to release a Windows Service that users can install and uninstall  you should use InstallShield.</span></span> <span data-ttu-id="1f27a-105">Vedere [la distribuzione di Windows Installer](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0).</span><span class="sxs-lookup"><span data-stu-id="1f27a-105">See [Windows Installer Deployment](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="1f27a-106">Se si vuole disinstallare un servizio dal computer, non seguire i passaggi di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1f27a-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="1f27a-107">In alternativa, individuare il programma o il pacchetto software è installato il servizio e quindi scegliere **Aggiungi/Rimuovi programmi** nel Pannello di controllo per disinstallare tale programma.</span><span class="sxs-lookup"><span data-stu-id="1f27a-107">Instead, find out which program or software package installed the service, and then choose **Add/Remove Programs** in Control Panel to uninstall that program.</span></span> <span data-ttu-id="1f27a-108">Si noti che molti servizi sono parte integrante di Windows. Se vengono rimossi, il sistema potrebbe diventare instabile.</span><span class="sxs-lookup"><span data-stu-id="1f27a-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>  
  
 <span data-ttu-id="1f27a-109">Per usare i passaggi descritti in questo articolo, è necessario prima aggiungere un programma di installazione del servizio al servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="1f27a-109">In order to use the steps in this article, you first need to add a service installer to your Windows Service.</span></span> <span data-ttu-id="1f27a-110">Vedere [procedura dettagliata: creazione di un'applicazione in Progettazione componenti del servizio](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="1f27a-110">See [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
 <span data-ttu-id="1f27a-111">I progetti del servizio Windows non possono essere eseguiti direttamente dall'ambiente di sviluppo di Visual Studio premendo F5,</span><span class="sxs-lookup"><span data-stu-id="1f27a-111">Windows Service projects cannot be run directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="1f27a-112">perché è necessario installare il servizio prima dell'esecuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1f27a-112">This is because the service in the project must be installed before you can run the project.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="1f27a-113">È possibile avviare **Esplora Server** e verificare che il servizio è stato installato o disinstallato.</span><span class="sxs-lookup"><span data-stu-id="1f27a-113">You can launch **Server Explorer** and verify that your service has been installed or uninstalled.</span></span> <span data-ttu-id="1f27a-114">Per ulteriori informazioni, vedere Procedura: accedere e inizializzare Esplora Server-Esplora Database.</span><span class="sxs-lookup"><span data-stu-id="1f27a-114">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
### <a name="to-install-your-service-manually"></a><span data-ttu-id="1f27a-115">Per installare il servizio manualmente</span><span class="sxs-lookup"><span data-stu-id="1f27a-115">To install your service manually</span></span>  
  
1.  <span data-ttu-id="1f27a-116">Di Windows **avviare** menu o **avviare** scegliere **Visual Studio** , **Visual Studio Tools**, **Developer Prompt dei comandi**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-116">On the Windows **Start** menu or **Start** screen, choose **Visual Studio** , **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="1f27a-117">Verrà visualizzato un prompt dei comandi di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1f27a-117">A Visual Studio command prompt appears.</span></span>  
  
2.  <span data-ttu-id="1f27a-118">Accedere alla directory in cui si trova il file eseguibile compilato del progetto.</span><span class="sxs-lookup"><span data-stu-id="1f27a-118">Access the directory where your project's compiled executable file is located.</span></span>  
  
3.  <span data-ttu-id="1f27a-119">Eseguire InstallUtil.exe dal prompt dei comandi con l'eseguibile del progetto come parametro:</span><span class="sxs-lookup"><span data-stu-id="1f27a-119">Run InstallUtil.exe from the command prompt with your project's executable as a parameter:</span></span>  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     <span data-ttu-id="1f27a-120">Se si usa il prompt dei comandi di Visual Studio, InstallUtil.exe sarà nel percorso di sistema.</span><span class="sxs-lookup"><span data-stu-id="1f27a-120">If you’re using the Visual Studio command prompt, InstallUtil.exe should be on the system path.</span></span> <span data-ttu-id="1f27a-121">In caso contrario, è possibile aggiungerlo al percorso o usare il percorso completo per richiamarlo.</span><span class="sxs-lookup"><span data-stu-id="1f27a-121">If not, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="1f27a-122">Questo strumento viene installato con .NET Framework e il percorso è `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`.</span><span class="sxs-lookup"><span data-stu-id="1f27a-122">This tool is installed with the .NET Framework, and its path is `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`.</span></span> <span data-ttu-id="1f27a-123">Ad esempio, per la versione a 32 bit di .NET Framework 4 o 4.5.*, se la directory di installazione di Windows è C:\Windows, il percorso è `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="1f27a-123">For example, for the 32-bit version of the .NET Framework 4 or 4.5.*, if your Windows installation directory is C:\Windows, the path is `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span></span> <span data-ttu-id="1f27a-124">Per la versione a 64 bit di .NET Framework 4 o 4.5. \*, il percorso predefinito è `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="1f27a-124">For the 64-bit version of the .NET Framework 4 or 4.5.\*, the default path is `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.</span></span>  
  
### <a name="to-uninstall-your-service-manually"></a><span data-ttu-id="1f27a-125">Per disinstallare il servizio manualmente</span><span class="sxs-lookup"><span data-stu-id="1f27a-125">To uninstall your service manually</span></span>  
  
1.  <span data-ttu-id="1f27a-126">Di Windows **avviare** menu o **avviare** scegliere **Visual Studio**, **Visual Studio Tools**, **Developer Prompt dei comandi**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-126">On the Windows **Start** menu or **Start** screen, choose **Visual Studio**, **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="1f27a-127">Verrà visualizzato un prompt dei comandi di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1f27a-127">A Visual Studio command prompt appears.</span></span>  
  
2.  <span data-ttu-id="1f27a-128">Eseguire InstallUtil.exe dal prompt dei comandi con l'output del progetto come parametro:</span><span class="sxs-lookup"><span data-stu-id="1f27a-128">Run InstallUtil.exe from the command prompt with your project's output as a parameter:</span></span>  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  <span data-ttu-id="1f27a-129">In alcuni casi, dopo avere eliminato il file eseguibile di un servizio, è possibile che il servizio sia ancora presente nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="1f27a-129">Sometimes, after the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="1f27a-130">In tal caso, utilizzare il comando [sc delete](http://technet.microsoft.com/library/cc742045.aspx) per rimuovere la voce per il servizio dal Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="1f27a-130">In that case, use the command [sc delete](http://technet.microsoft.com/library/cc742045.aspx) to remove the entry for the service from the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f27a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f27a-131">See Also</span></span>  
 [<span data-ttu-id="1f27a-132">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="1f27a-132">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="1f27a-133">Procedura: creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="1f27a-133">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="1f27a-134">Procedura: aggiungere programmi di installazione all'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="1f27a-134">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="1f27a-135">Installutil.exe (Strumento Programma di installazione)</span><span class="sxs-lookup"><span data-stu-id="1f27a-135">Installutil.exe (Installer Tool)</span></span>](../../../docs/framework/tools/installutil-exe-installer-tool.md)

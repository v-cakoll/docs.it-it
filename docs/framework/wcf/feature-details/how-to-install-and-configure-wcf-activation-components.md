---
title: 'Procedura: installare e configurare componenti di attivazione WCF'
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 0a7be97ec157638db3eb2d656fe263b37b8d676c
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837415"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="6c1d3-102">Procedura: installare e configurare componenti di attivazione WCF</span><span class="sxs-lookup"><span data-stu-id="6c1d3-102">How to: Install and Configure WCF Activation Components</span></span>

<span data-ttu-id="6c1d3-103">In questo argomento vengono descritti i passaggi necessari per configurare il servizio di attivazione dei processi di Windows (anche noto come WAS) in Windows Vista per ospitare i servizi di Windows Communication Foundation (WCF) che non comunicano tramite protocolli di rete HTTP.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on Windows Vista to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="6c1d3-104">Nelle sezioni seguenti vengono spiegati i passaggi relativi a tale configurazione:</span><span class="sxs-lookup"><span data-stu-id="6c1d3-104">The following sections outline the steps for this configuration:</span></span>

- <span data-ttu-id="6c1d3-105">Installare o confermare l'installazione dei componenti di attivazione WCF.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-105">Install (or confirm the installation of) the WCF activation components.</span></span>

- <span data-ttu-id="6c1d3-106">Configurare WAS per supportare un protocollo non HTTP.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-106">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="6c1d3-107">La procedura seguente consente di configurare Windows Vista per l'attivazione TCP.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-107">The following procedure configures Windows Vista for TCP activation.</span></span>

<span data-ttu-id="6c1d3-108">Dopo l'installazione e la configurazione di WAS, vedere [procedura: ospitare un servizio WCF in was](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) per le procedure per la creazione di un servizio WCF che espone un endpoint non http che utilizza was.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-108">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>

## <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="6c1d3-109">Per installare i componenti di attivazione WCF non HTTP</span><span class="sxs-lookup"><span data-stu-id="6c1d3-109">To install the WCF non-HTTP activation components</span></span>

1. <span data-ttu-id="6c1d3-110">Fare clic sul pulsante **Start** , quindi scegliere **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-110">Click the **Start** button, and then click **Control Panel**.</span></span>

2. <span data-ttu-id="6c1d3-111">Scegliere **Programmi** e quindi fare clic su **Programmi e funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-111">Click **Programs**, and then click **Programs and Features**.</span></span>

3. <span data-ttu-id="6c1d3-112">Nel menu **attività** fare clic **su attivazione o disattivazione delle funzionalità Windows**.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-112">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>

4. <span data-ttu-id="6c1d3-113">Trovare il nodo WinFX, selezionare e quindi espanderlo.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-113">Find the WinFX node, select and then expand it.</span></span>

5. <span data-ttu-id="6c1d3-114">Selezionare la casella **componenti di attivazione non HTTP WCF** e salvare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-114">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>

## <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="6c1d3-115">Per configurare WAS per supportare l'attivazione TCP</span><span class="sxs-lookup"><span data-stu-id="6c1d3-115">To configure the WAS to support TCP activation</span></span>

1. <span data-ttu-id="6c1d3-116">Per supportare l'attivazione net.tcp, è prima necessario associare il sito Web predefinito a una porta net.tcp.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-116">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="6c1d3-117">A tale scopo, è possibile utilizzare Appcmd. exe, installato con il set di strumenti di gestione di IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-117">You can do this by using Appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="6c1d3-118">In una finestra del prompt dei comandi a livello di amministratore, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-118">In an administrator-level Command Prompt window, run the following command.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="6c1d3-119">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-119">This command is a single line of text.</span></span> <span data-ttu-id="6c1d3-120">Il comando aggiunge un'associazione del sito net.tcp al sito Web predefinito in ascolto sulla porta TCP 808 con qualsiasi nome host.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-120">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>

2. <span data-ttu-id="6c1d3-121">Anche se tutte le applicazioni all'interno di un sito condividono un'associazione net.tcp comune, ognuna di esse può attivare il supporto net.tcp individualmente.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-121">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="6c1d3-122">Per attivare net.tcp per l'applicazione, eseguire il comando seguente da un prompt dei comandi a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-122">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp
    ```

    > [!NOTE]
    > <span data-ttu-id="6c1d3-123">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-123">This command is a single line of text.</span></span> <span data-ttu-id="6c1d3-124">Questo comando Abilita l'accesso all'applicazione > dell'applicazione *WCF*/\<usando sia `http://localhost/<WCF Application>` che `net.tcp://localhost/<WCF Application>`.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-124">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>

     <span data-ttu-id="6c1d3-125">Rimuovere l'associazione del sito net.tcp aggiunta per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-125">Remove the net.tcp site binding you added for this sample.</span></span>

     <span data-ttu-id="6c1d3-126">Per comodità, i due passaggi seguenti vengono implementati in un file batch chiamato RemoveNetTcpSiteBinding.cmd situato nella directory di esempio.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-126">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="6c1d3-127">Rimuovere net.tcp dall'elenco dei protocolli attivati tramite il comando seguente in una finestra del prompt dei comandi a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-127">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="6c1d3-128">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-128">This command is a single line of text.</span></span>

    2. <span data-ttu-id="6c1d3-129">Rimuovere l'associazione del sito net.tcp tramite il comando seguente in una finestra del prompt dei comandi con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="6c1d3-129">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > <span data-ttu-id="6c1d3-130">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-130">This command is a single line of text.</span></span>

## <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="6c1d3-131">Per rimuovere net.tcp dall'elenco dei protocolli attivati</span><span class="sxs-lookup"><span data-stu-id="6c1d3-131">To remove net.tcp from the list of enabled protocols</span></span>

1. <span data-ttu-id="6c1d3-132">Per rimuovere net.tcp dall'elenco dei protocolli attivati, eseguire il comando seguente in una finestra del prompt dei comandi a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-132">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
    ```

    > [!NOTE]
    > <span data-ttu-id="6c1d3-133">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-133">This command is a single line of text.</span></span>

## <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="6c1d3-134">Per rimuovere l'associazione del sito net.tcp</span><span class="sxs-lookup"><span data-stu-id="6c1d3-134">To remove the net.tcp site binding</span></span>

1. <span data-ttu-id="6c1d3-135">Per rimuovere l'associazione del sito net.tcp, eseguire il comando seguente in una finestra del prompt dei comandi a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-135">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
    -bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="6c1d3-136">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="6c1d3-136">This command is a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c1d3-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c1d3-137">See also</span></span>

- [<span data-ttu-id="6c1d3-138">Attivazione TCP</span><span class="sxs-lookup"><span data-stu-id="6c1d3-138">TCP Activation</span></span>](../../../../docs/framework/wcf/samples/tcp-activation.md)
- [<span data-ttu-id="6c1d3-139">Attivazione MSMQ</span><span class="sxs-lookup"><span data-stu-id="6c1d3-139">MSMQ Activation</span></span>](../../../../docs/framework/wcf/samples/msmq-activation.md)
- [<span data-ttu-id="6c1d3-140">Attivazione di NamedPipe</span><span class="sxs-lookup"><span data-stu-id="6c1d3-140">NamedPipe Activation</span></span>](../../../../docs/framework/wcf/samples/namedpipe-activation.md)
- [<span data-ttu-id="6c1d3-141">Funzionalità di hosting di Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="6c1d3-141">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)

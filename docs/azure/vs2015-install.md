---
title: Strumenti di Azure per Visual Studio 2015
description: È possibile ottenere gli strumenti per iniziare a usare le librerie .NET di Azure da Visual Studio 2015.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 72229ce0c0276912ddc5658e34f4572a7948a4e6
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174925"
---
# <a name="azure-tools-for-visual-studio-2015"></a><span data-ttu-id="5b617-103">Strumenti di Azure per Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="5b617-103">Azure tools for Visual Studio 2015</span></span>

<span data-ttu-id="5b617-104">Il modo più semplice e rapido per installare **Azure SDK per Visual Studio 2015** e **Service Fabric SDK e Strumenti per Visual Studio 2015** consiste nell'usare l'[Installazione guidata piattaforma Web](https://www.microsoft.com/web/downloads/platform.aspx).</span><span class="sxs-lookup"><span data-stu-id="5b617-104">The quickest and easiest way to install the **Azure SDK for Visual Studio 2015** and **Service Fabric SDK and Tools for Visual Studio 2015** is using the [Web Platform Installer](https://www.microsoft.com/web/downloads/platform.aspx).</span></span> <span data-ttu-id="5b617-105">Installazione guidata piattaforma Web Microsoft è uno strumento gratuito che semplifica il download, l'installazione e l'aggiornamento di alcuni componenti della piattaforma Web Microsoft, inclusi gli strumenti di Azure per Visual Studio 2015.</span><span class="sxs-lookup"><span data-stu-id="5b617-105">The Microsoft Web Platform Installer is a free tool that streamlines downloading, installing, and updating some of the components of the Microsoft Web Platform, including Azure tools for Visual Studio 2015.</span></span> <span data-ttu-id="5b617-106">Questi SDK possono essere scaricati e installati anche come singoli componenti dalla [pagina Download di Azure](https://azure.microsoft.com/downloads/).</span><span class="sxs-lookup"><span data-stu-id="5b617-106">These SDKs can also be downloaded and installed as individual components from the [Azure Downloads page](https://azure.microsoft.com/downloads/).</span></span>

## <a name="using-the-web-platform-installer"></a><span data-ttu-id="5b617-107">Uso dell'Installazione guidata piattaforma Web</span><span class="sxs-lookup"><span data-stu-id="5b617-107">Using the Web Platform Installer</span></span>

1. <span data-ttu-id="5b617-108">Scaricare ed eseguire questo [programma di avvio automatico per l'Installazione guidata piattaforma Web](https://www.microsoft.com/web/handlers/webpi.ashx?command=getinstallerredirect&appid=VWDOrVs2015AzurePack;MicrosoftAzure-ServiceFabric-VS2015).</span><span class="sxs-lookup"><span data-stu-id="5b617-108">Download and run this [Web Platform Installer bootstrapper](https://www.microsoft.com/web/handlers/webpi.ashx?command=getinstallerredirect&appid=VWDOrVs2015AzurePack;MicrosoftAzure-ServiceFabric-VS2015).</span></span>

2. <span data-ttu-id="5b617-109">Il programma di avvio automatico installerà l'Installazione guidata piattaforma Web (se necessario) e inserirà automaticamente le versioni più recenti di **Azure SDK per Visual Studio 2015** e **Service Fabric SDK e Strumenti per Visual Studio 2015** nell'elenco *Elementi da installare*.</span><span class="sxs-lookup"><span data-stu-id="5b617-109">The bootstrapper will install Web Platform Installer (if needed) and automatically put the latest versions of the  **Azure SDK for Visual Studio 2015** and **Service Fabric SDK and Tools for Visual Studio 2015** items in your *Items to be installed* list.</span></span> <span data-ttu-id="5b617-110">Fare clic su **Install** (Installa).</span><span class="sxs-lookup"><span data-stu-id="5b617-110">Click **Install**.</span></span>

    ![Installazione guidata piattaforma Web](media/vs2015-install/webpi.png)

3. <span data-ttu-id="5b617-112">Nella schermata successiva fare clic su **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="5b617-112">On the next screen, click **I Accept**.</span></span> <span data-ttu-id="5b617-113">Verrà avviato il download dell'Installazione guidata piattaforma Web e verranno installati i componenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="5b617-113">Web PI will begin downloading and installing the components you selected.</span></span>

4. <span data-ttu-id="5b617-114">Al termine dell'installazione verrà visualizzata una schermata di conferma.</span><span class="sxs-lookup"><span data-stu-id="5b617-114">After the installation is finished, it will display a confirmation screen.</span></span> <span data-ttu-id="5b617-115">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="5b617-115">Click **Finish**.</span></span> <span data-ttu-id="5b617-116">È ora possibile chiudere l'Installazione guidata piattaforma Web.</span><span class="sxs-lookup"><span data-stu-id="5b617-116">You can now close Web Platform Installer.</span></span>

## <a name="verifying-the-installation"></a><span data-ttu-id="5b617-117">Verifica dell'installazione</span><span class="sxs-lookup"><span data-stu-id="5b617-117">Verifying the installation</span></span>

1. <span data-ttu-id="5b617-118">In Visual Studio 2015 scegliere **Estensioni e aggiornamenti** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="5b617-118">In Visual Studio 2015, click the **Tools** menu, and then click **Extensions and Updates...**.</span></span>

2. <span data-ttu-id="5b617-119">L'elenco visualizzato includerà alcuni strumenti di Azure, ad esempio gli **Strumenti del servizio app di Microsoft Azure**, **Servizio connesso di Archiviazione di Microsoft Azure** e **Strumenti di Service Fabric**.</span><span class="sxs-lookup"><span data-stu-id="5b617-119">The displayed list will contain several Azure tools, such as **Microsoft Azure App Service Tools**, **Microsoft Azure Storage Connected Service**, and **Service Fabric Tools**.</span></span>

    ![Estensioni e aggiornamenti](media/vs2015-install/ext-tools.png)

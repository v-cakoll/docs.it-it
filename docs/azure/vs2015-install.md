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
# <a name="azure-tools-for-visual-studio-2015"></a>Strumenti di Azure per Visual Studio 2015

Il modo più semplice e rapido per installare **Azure SDK per Visual Studio 2015** e **Service Fabric SDK e Strumenti per Visual Studio 2015** consiste nell'usare l'[Installazione guidata piattaforma Web](https://www.microsoft.com/web/downloads/platform.aspx). Installazione guidata piattaforma Web Microsoft è uno strumento gratuito che semplifica il download, l'installazione e l'aggiornamento di alcuni componenti della piattaforma Web Microsoft, inclusi gli strumenti di Azure per Visual Studio 2015. Questi SDK possono essere scaricati e installati anche come singoli componenti dalla [pagina Download di Azure](https://azure.microsoft.com/downloads/).

## <a name="using-the-web-platform-installer"></a>Uso dell'Installazione guidata piattaforma Web

1. Scaricare ed eseguire questo [programma di avvio automatico per l'Installazione guidata piattaforma Web](https://www.microsoft.com/web/handlers/webpi.ashx?command=getinstallerredirect&appid=VWDOrVs2015AzurePack;MicrosoftAzure-ServiceFabric-VS2015).

2. Il programma di avvio automatico installerà l'Installazione guidata piattaforma Web (se necessario) e inserirà automaticamente le versioni più recenti di **Azure SDK per Visual Studio 2015** e **Service Fabric SDK e Strumenti per Visual Studio 2015** nell'elenco *Elementi da installare*. Fare clic su **Install** (Installa).

    ![Installazione guidata piattaforma Web](media/vs2015-install/webpi.png)

3. Nella schermata successiva fare clic su **Accetto**. Verrà avviato il download dell'Installazione guidata piattaforma Web e verranno installati i componenti selezionati.

4. Al termine dell'installazione verrà visualizzata una schermata di conferma. Fare clic su **Fine**. È ora possibile chiudere l'Installazione guidata piattaforma Web.

## <a name="verifying-the-installation"></a>Verifica dell'installazione

1. In Visual Studio 2015 scegliere **Estensioni e aggiornamenti** dal menu **Strumenti**.

2. L'elenco visualizzato includerà alcuni strumenti di Azure, ad esempio gli **Strumenti del servizio app di Microsoft Azure**, **Servizio connesso di Archiviazione di Microsoft Azure** e **Strumenti di Service Fabric**.

    ![Estensioni e aggiornamenti](media/vs2015-install/ext-tools.png)

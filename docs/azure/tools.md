---
title: Strumenti per gli sviluppatori .NET in Azure
description: Ottenere gli strumenti per iniziare a usare le librerie .NET di Azure da un ambiente Windows, Linux e Mac.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: fa645b152f15550b25a3542ba0cdbb43799536b9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174926"
---
# <a name="azure-tools-for-developing-with-net"></a>Strumenti di Azure per lo sviluppo con .NET

## <a name="sdk-downloads"></a>Download dell'SDK

Le librerie di Azure per .NET sono implementate come [pacchetti NuGet](https://www.nuget.org/packages?q=windowsazureofficial). Vedere le informazioni di [riferimento sulle API](/dotnet/api/overview/azure/?view=azure-dotnet) per la documentazione di riferimento organizzata dal servizio di Azure.

## <a name="development-tools"></a>Strumenti di sviluppo

Visual Studio include strumenti per molti servizi di Azure predefiniti. Per alcuni servizi di Azure sono disponibili strumenti o emulatori aggiuntivi, ad esempio [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/). Se necessario, vedere la documentazione relativa al servizio di Azure per eventuali altri strumenti.

Selezionare l'ambiente di sviluppo preferito.

## <a name="visual-studio-on-windows"></a>[Visual Studio su Windows](#tab/vs)

Visual Studio versione 2017 e successive includono il supporto integrato per lo sviluppo in Azure. I passaggi seguenti descrivono l'abilitazione del supporto per lo sviluppo di Azure in Visual Studio.

Per Visual Studio 2015 e versioni precedenti, <a href="vs2015-install.md">seguire queste istruzioni</a>.

### <a name="step-1-download-visual-studio-2019"></a>Passaggio 1: scaricare Visual Studio 2019

È possibile ignorare questo passaggio se si dispone già di Visual Studio 2019 installato.

> [!div class="nextstepaction"]
> [Scarica Visual Studio 2019](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a>Passaggio 2: Installare i due componenti per Azure

Nel programma di installazione di Visual Studio installare Visual Studio o modificare un'installazione esistente. Assicurarsi che i carichi di lavoro sviluppo di *Azure* e *ASP.NET e sviluppo Web* siano selezionati.

### <a name="step-3-develop-with-net-on-azure"></a>Passaggio 3: Sviluppare con .NET in Azure

Proseguire con [distribuire la prima app Web ASP.NET Core con servizio app di Azure](/azure/app-service-web/app-service-web-get-started-dotnet).

## <a name="visual-studio-code-cross-platform"></a>[Visual Studio Code (multipiattaforma)](#tab/vscode)

Visual Studio Code dispone di tutto il necessario per lo sviluppo di Azure multipiattaforma.

### <a name="step-1-download-the-net-core-sdk"></a>Passaggio 1: Scaricare .NET Core SDK

SDK e strumenti da riga di comando per le app .NET Core.

> [!div class="nextstepaction"]
> [Download di .NET Core SDK](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a>Passaggio 2: Visual Studio Code

Modificare ed eseguire il debug di app .NET Core in qualsiasi sistema operativo: Windows, Mac e Linux.

> [!div class="nextstepaction"]
> [Download di Visual Studio Code](https://code.visualstudio.com)

### <a name="step-3-azure-tools-extension"></a>Passaggio 3: estensione degli strumenti di Azure

Installare l'estensione strumenti di Azure in Visual Studio Code.

> [!div class="nextstepaction"]
> [Installare l'estensione degli strumenti di Azure](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)

### <a name="step-4-develop-with-net-on-azure"></a>Passaggio 4: sviluppare con .NET in Azure

Per iniziare, [distribuire la prima app Web di ASP.NET Core nel servizio app Azure in Linux](/azure/app-service/containers/quickstart-dotnetcore).

---

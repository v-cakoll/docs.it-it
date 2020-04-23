---
title: Azure per sviluppatori .NET e .NET Core di Azure
description: Ottenere gli strumenti per iniziare a usare le librerie .NET di Azure da un ambiente Windows, Linux e Mac.
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "82071941"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a>Azure per sviluppatori .NET e .NET Core di Azure

## <a name="sdk-downloads"></a>Download dell'SDK

Le librerie di Azure per .NET sono implementate come [pacchetti NuGet](https://www.nuget.org/packages?q=windowsazureofficial). Vedere le informazioni di [riferimento sulle API](/dotnet/api/overview/azure/?view=azure-dotnet) per le istruzioni di installazione organizzate dal servizio di Azure.

## <a name="development-tools"></a>Strumenti di sviluppo

Visual Studio include strumenti per molti servizi di Azure predefiniti. Per alcuni servizi di Azure sono disponibili strumenti o emulatori aggiuntivi, ad esempio [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/). Se necessario, vedere la documentazione relativa al servizio di Azure per eventuali altri strumenti.

Queste istruzioni installano l'ambiente di sviluppo consigliato per il sistema operativo in uso.

## <a name="windows"></a>[Windows](#tab/windows)

Visual Studio versione 2017 e successive includono il supporto integrato per lo sviluppo in Azure. I passaggi seguenti descrivono l'abilitazione del supporto per lo sviluppo di Azure in Visual Studio.

Per Visual Studio 2015 e versioni precedenti, <a href="vs2015-install.md">seguire queste istruzioni</a>.

### <a name="step-1-download-visual-studio-2019"></a>Passaggio 1: scaricare Visual Studio 2019

È possibile ignorare questo passaggio se si dispone già di Visual Studio 2019 installato.

> [!div class="nextstepaction"]
> [Scarica Visual Studio 2019](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a>Passaggio 2: Installare i due componenti per Azure

Nel programma di installazione di Visual Studio installare Visual Studio o modificare un'installazione esistente. Assicurarsi che i carichi di lavoro sviluppo di *Azure* e *ASP.NET e sviluppo Web* siano selezionati.

### <a name="step-3-develop-with-net-on-azure"></a>Passaggio 3: Sviluppare con .NET in Azure

Proseguire con [distribuire la prima app Web ASP.NET Core con servizio app di Azure](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).

## <a name="macos"></a>[macOS](#tab/macos)

Visual Studio per Mac include tutti gli elementi necessari per lo sviluppo in Azure.

### <a name="step-1-download-visual-studio-for-mac"></a>Passaggio 1: Scaricare Visual Studio per Mac

> [!div class="nextstepaction"]
> [Download di Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/)

Durante l'installazione, gli strumenti di Azure sono selezionati per impostazione predefinita.

## <a name="linux"></a>[Linux](#tab/linux)

Visual Studio Code include tutti gli elementi necessari per lo sviluppo di Azure in Linux.

### <a name="step-1-download-the-net-core-sdk"></a>Passaggio 1: Scaricare .NET Core SDK

SDK e strumenti da riga di comando per le app .NET Core.

> [!div class="nextstepaction"]
> [Download di .NET Core SDK](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a>Passaggio 2: Visual Studio Code

Modificare ed eseguire il debug di app .NET Core in qualsiasi sistema operativo: Windows, Mac e Linux.

> [!div class="nextstepaction"]
> [Download di Visual Studio Code](https://code.visualstudio.com)

---

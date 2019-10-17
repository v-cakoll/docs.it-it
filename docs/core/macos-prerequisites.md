---
title: Prerequisiti per .NET Core in Mac
description: Versioni macOS supportate e dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer macOS.
author: thraka
ms.author: adegeo
ms.custom: updateeachvsrelease
ms.date: 10/11/2019
ms.openlocfilehash: 2d4fc0b37be08988440325db8b507124c36bf053
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318312"
---
# <a name="prerequisites-for-net-core-on-macos"></a>Prerequisiti per .NET Core in macOS

Questo articolo illustra le versioni macOS supportate e le dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer macOS. Le versioni del sistema operativo e le dipendenze indicate di seguito sono valide per le tre modalità di sviluppo di app .NET Core in ambiente Mac: tramite la [riga di comando con l'editor preferito](tutorials/using-with-xplat-cli.md), con [Visual Studio Code](https://code.visualstudio.com/) e con [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).

## <a name="downloads-and-dependencies"></a>Download e dipendenze

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3,0 è supportato in **MacOS High Sierra (versione 10,13)** e versioni successive. È necessaria un'architettura della CPU **x64** .

Scaricare e installare il .NET Core SDK dalla pagina di [download di .NET Core 3,0](https://dotnet.microsoft.com/download/dotnet-core/3.0) . [.Net core 3,0 versioni del sistema operativo supportate](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) per l'elenco completo di sistemi operativi, distribuzioni e versioni di .net core 3,0 supportati, versioni del sistema operativo non supportate e collegamenti ai criteri del ciclo di vita.

Per un elenco dei problemi noti, vedere [problemi noti di .NET Core](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-known-issues.md).

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

.NET Core 2,2 è supportato in **MacOS Sierra (versione 10,12)** e versioni successive. È necessaria un'architettura della CPU **x64** .

Scaricare e installare il .NET Core SDK dalla pagina di [download di .NET Core 2,2](https://dotnet.microsoft.com/download/dotnet-core/2.2) . [.Net core 2,2 versioni del sistema operativo supportate](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) per l'elenco completo di sistemi operativi, distribuzioni e versioni di .net core 2,2 supportati, versioni del sistema operativo non supportate e collegamenti ai criteri del ciclo di vita.

Per un elenco dei problemi noti, vedere [problemi noti di .NET Core](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-known-issues.md).

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2,1 è supportato in **MacOS Sierra (versione 10,12)** e versioni successive. È necessaria un'architettura della CPU **x64** .

Scaricare e installare il .NET Core SDK dalla pagina di [download di .NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1) . [.Net core 2,1 versioni del sistema operativo supportate](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) per l'elenco completo di sistemi operativi, distribuzioni e versioni di .net core 2,1 supportati, versioni del sistema operativo non supportate e collegamenti ai criteri del ciclo di vita.

Per un elenco dei problemi noti, vedere [problemi noti di .NET Core](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-known-issues.md).

---

## <a name="libgdiplus"></a>libgdiplus

Le applicazioni .NET Core che usano l'assembly *System. Drawing. Common* richiedono l'installazione di libgdiplus.

Un modo semplice per ottenere libgdiplus consiste nell'usare la gestione pacchetti [homebrew ("Brew")](https://brew.sh/) per MacOS. Dopo l'installazione di *Brew*, installare libgdiplus eseguendo i comandi seguenti in un prompt dei comandi (Command) terminale:

```console
brew update
brew install libgdiplus
```

## <a name="visual-studio-for-mac"></a>Visual Studio per Mac

È possibile usare qualsiasi editor per sviluppare applicazioni .NET Core con .NET Core SDK. Se si vuole tuttavia sviluppare applicazioni .NET Core in Mac in un ambiente di sviluppo integrato, è possibile usare [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).

---
title: Prerequisiti per .NET Core in Mac
description: Versioni macOS supportate e dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer macOS.
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 07/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8feaee2cbfa55e23bd49c0ab76d995f15be343b4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="prerequisites-for-net-core-on-mac"></a>Prerequisiti per .NET Core in Mac

Questo articolo illustra le versioni macOS supportate e le dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer macOS. Le versioni del sistema operativo e le dipendenze indicate di seguito sono valide per le tre modalità di sviluppo di app .NET Core in ambiente Mac: tramite la [riga di comando con l'editor preferito](tutorials/using-with-xplat-cli.md), con [Visual Studio Code](https://code.visualstudio.com/) e con [Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/).

## <a name="supported-macos-versions"></a>Versioni macOS supportate

.NET Core è supportato nelle versioni di macOS seguenti:

* macOS 10.12 "Sierra"
* macOS 10.11 "El Capitan" (solo .NET Core 1.x)

Per l'elenco completo dei sistemi operativi supportati, vedere [Supported OS Versions](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions) (Versioni supportate dei sistemi operativi).

## <a name="net-core-dependencies"></a>Dipendenze .NET Core

**.NET Core 1.x**

Per l'esecuzione di .NET Core 1.x in macOS è necessario OpenSSL. È possibile ottenere facilmente OpenSSL tramite il sistema di gestione pacchetti [Homebrew ("brew")](https://brew.sh/) per macOS. Dopo aver installato *brew*, installare OpenSSL eseguendo i comandi seguenti da un prompt (dei comandi) Terminal:

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

Scaricare e installare .NET Core SDK da [.NET Downloads](https://www.microsoft.com/net/download/core) (Download di .NET). In caso di problemi con l'installazione in macOS, vedere gli argomenti [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) (Problemi noti della versione 1.0.0) e [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) (Problemi noti della versione 1.0.1).

**.NET Core 2.x**

Scaricare e installare .NET Core SDK da [.NET Downloads](https://www.microsoft.com/net/download/core) (Download di .NET). In caso di problemi con l'installazione in macOS, vedere l'argomento [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) (Problemi noti) per la versione installata.

## <a name="visual-studio-for-mac"></a>Visual Studio per Mac

È possibile usare qualsiasi editor per sviluppare applicazioni .NET Core con .NET Core SDK. Se si vuole tuttavia sviluppare applicazioni .NET Core in Mac in un ambiente di sviluppo integrato, è possibile usare [Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/). 

Per lo sviluppo di .NET Core in macOS con Visual Studio per Mac sono previsti i requisiti seguenti:

* Versione supportata del sistema operativo macOS
* OpenSSL (.NET Core 1.x solo ; .NET Core 2.x usa servizi di sicurezza disponibili in modo nativo in macOS)
* .NET core SDK per Mac
* [Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/)


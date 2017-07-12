---
title: Prerequisiti per .NET Core in Mac | Microsoft Docs
description: Versioni macOS supportate e dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer macOS.
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: Human Translation
ms.sourcegitcommit: 83200e452bccc20bfa82d94899514019e9d05a23
ms.openlocfilehash: 2aa685751fae9fa9771fa1cd86d211f742e06932
ms.contentlocale: it-it
ms.lasthandoff: 07/05/2017

---

<a id="prerequisites-for-net-core-on-mac" class="xliff"></a>

# Prerequisiti per .NET Core in Mac

Questo articolo illustra le versioni macOS supportate e le dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer macOS. Le versioni del sistema operativo e le dipendenze indicate di seguito sono valide per le tre modalità di sviluppo di app .NET Core in ambiente Mac: tramite la [riga di comando con l'editor preferito](tutorials/using-with-xplat-cli.md), con [Visual Studio Code](https://code.visualstudio.com/) e con [Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/).

<a id="supported-macos-versions" class="xliff"></a>

## Versioni macOS supportate

.NET Core è supportato dalle versioni di macOS seguenti:

* macOS 10.12 "Sierra"
* macOS 10.11 "El Capitan"

Per l'elenco completo dei sistemi operativi supportati, vedere le [note sulla versione di .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md).

<a id="net-core-dependencies" class="xliff"></a>

## Dipendenze .NET Core

**.NET Core 1.x**

Per l'esecuzione di .NET Core 1.x in macOS è necessario OpenSSL. È possibile ottenere facilmente OpenSSL tramite il sistema di gestione pacchetti [Homebrew ("brew")](https://brew.sh/) per macOS. Dopo aver installato *brew*, installare OpenSSL eseguendo i comandi seguenti da un prompt (dei comandi) Terminal:

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

Scaricare e installare .NET Core SDK da [.NET Downloads](https://www.microsoft.com/net/download/core) (Download di .NET). In caso di problemi con l'installazione in macOS, vedere l'argomento [Known issues & workarounds](https://github.com/dotnet/core/blob/master/cli/known-issues.md) (Problemi noti e soluzioni alternative).

**.NET Core 2.x**

Scaricare e installare .NET Core SDK da [.NET Downloads](https://www.microsoft.com/net/download/core) (Download di .NET). In caso di problemi con l'installazione in macOS, vedere l'argomento [Known issues & workarounds](https://github.com/dotnet/core/blob/master/cli/known-issues.md) (Problemi noti e soluzioni alternative).

<a id="visual-studio-for-mac" class="xliff"></a>

## Visual Studio per Mac

Per lo sviluppo di .NET Core in macOS con Visual Studio per Mac sono previsti i requisiti seguenti:

* Versione supportata del sistema operativo macOS
* OpenSSL (.NET Core 1.x solo ; .NET Core 2.x usa servizi di sicurezza disponibili in modo nativo in macOS)
* .NET core SDK per Mac
* [Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/)


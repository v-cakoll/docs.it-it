---
title: Prerequisiti per .NET Core in Mac
description: Versioni macOS supportate e dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer macOS.
author: guardrex
ms.author: mairaw
ms.date: 09/27/2017
ms.openlocfilehash: b1f4d3b49be7ba5349197187d6576b78db58798c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33219079"
---
# <a name="prerequisites-for-net-core-on-macos"></a>Prerequisiti per .NET Core in macOS

Questo articolo illustra le versioni macOS supportate e le dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer macOS. Le versioni del sistema operativo e le dipendenze indicate di seguito sono valide per le tre modalità di sviluppo di app .NET Core in ambiente Mac: tramite la [riga di comando con l'editor preferito](tutorials/using-with-xplat-cli.md), con [Visual Studio Code](https://code.visualstudio.com/) e con [Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/).

## <a name="supported-macos-versions"></a>Versioni macOS supportate

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.x è supportato nelle versioni di macOS seguenti:

* macOS 10.12 "Sierra" e versioni successive

Per l'elenco completo di sistemi operativi supportati da .NET Core 2.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

.NET Core 1.x è supportato nelle versioni di macOS seguenti:

* macOS 10.12 "Sierra"
* macOS 10.11 "El Capitan"

Per l'elenco completo di sistemi operativi, supportati da .NET Core 1.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 1.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).

---

## <a name="net-core-dependencies"></a>Dipendenze .NET Core

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Scaricare e installare .NET Core SDK da [.NET Downloads](https://www.microsoft.com/net/download/core) (Download di .NET). In caso di problemi con l'installazione in macOS, vedere l'argomento [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) (Problemi noti) per la versione installata.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

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

---

## <a name="increase-the-maximum-open-file-limit-net-core-versions-before-net-core-sdk-202"></a>Aumentare il limite massimo di file aperti (versioni di .NET Core prima di .NET Core SDK 2.0.2) 

Nelle versioni precedenti di .NET Core (prima di .NET Core SDK 2.0.2) il limite di file aperti predefinito per macOS potrebbe non essere sufficiente per alcuni carichi di lavoro di .NET Core, ad esempio il ripristino di progetti o l'esecuzione di unit test.

È possibile aumentare questo limite seguendo questa procedura:

1. Usare un editor di testo e creare un nuovo file _/Library/LaunchDaemons/limit.maxfiles.plist_, quindi salvare il file con il contenuto seguente:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
        "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
  <dict>
    <key>Label</key>
    <string>limit.maxfiles</string>
    <key>ProgramArguments</key>
    <array>
      <string>launchctl</string>
      <string>limit</string>
      <string>maxfiles</string>
      <string>2048</string>
      <string>4096</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
    <key>ServiceIPC</key>
    <false/>
  </dict>
</plist>
```

2. Eseguire il comando seguente in un finestra del terminale:

```console
echo 'ulimit -n 2048' | sudo tee -a /etc/profile
```

3. Riavviare il computer Mac per applicare queste impostazioni.

## <a name="visual-studio-for-mac"></a>Visual Studio per Mac

È possibile usare qualsiasi editor per sviluppare applicazioni .NET Core con .NET Core SDK. Se si vuole tuttavia sviluppare applicazioni .NET Core in Mac in un ambiente di sviluppo integrato, è possibile usare [Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/). 

Per lo sviluppo di .NET Core in macOS con Visual Studio per Mac sono previsti i requisiti seguenti:

* Versione supportata del sistema operativo macOS
* OpenSSL (.NET Core 1.x solo ; .NET Core 2.x usa servizi di sicurezza disponibili in modo nativo in macOS)
* .NET core SDK per Mac
* [Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/)

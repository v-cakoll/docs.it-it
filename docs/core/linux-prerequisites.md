---
title: Prerequisiti per .NET Core in Linux
description: Versioni Linux supportate e dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer Linux.
author: thraka
ms.author: adegeo
ms.date: 12/14/2018
ms.openlocfilehash: 0bd3287535ba2c398f6577890d1d39f42a806364
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612225"
---
# <a name="prerequisites-for-net-core-on-linux"></a>Prerequisiti per .NET Core in Linux

Questo articolo illustra le dipendenze necessarie per sviluppare applicazioni .NET Core in Linux. Le distribuzioni/versioni Linux supportate e le dipendenze seguenti si applicano alle due modalità di sviluppo di app .NET Core in Linux:

* [Riga di comando con l'editor preferito](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

> [!NOTE]
> Il pacchetto .NET Core SDK non è richiesto per ambienti/server di produzione. È necessario solo il pacchetto di runtime di .NET Core per le app distribuite in ambienti di produzione. Il runtime di .NET Core viene distribuito con le app nell'ambito di una distribuzione indipendente, ma deve essere distribuito separatamente per le app dipendenti dal framework. Per altre informazioni sui tipi di distribuzione indipendenti e dipendenti dal framework, vedere [Distribuzione di applicazioni .NET Core](./deploying/index.md). Per linee guida specifiche, vedere anche [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Applicazioni Linux indipendenti).

## <a name="supported-linux-versions"></a>Versioni di Linux supportate

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.x considera Linux come un singolo sistema operativo. Esiste una sola build di Linux (per l'architettura chip) per le distribuzioni di Linux supportate. 

Per i collegamenti per il download e altre informazioni, vedere [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) (Download di .NET Core 2.2) o [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1) (Download di .NET Core 2.1).

.NET Core 2.x è supportato nelle seguenti distribuzioni/versioni Linux:

* Red Hat Enterprise Linux 7, 6 a 64 bit (`x86_64` o `amd64`)
* CentOS 7 a 64 bit (`x86_64` o `amd64`) 
* Oracle Linux 7 a 64 bit (`x86_64` o `amd64`) 
* Fedora 28, 27 a 64-bit (`x86_64` o `amd64`) 
* Debian 9 (a 64 bit, `arm32`), 8.7 o versioni successive a 64 bit (`x86_64` o `amd64`)
* Ubuntu 18.04 (a 64 bit `arm32`), 16.04, 14.04 a 64 bit (`x86_64` o `amd64`)
* Linux Mint 18, 17 a 64 bit (`x86_64` o `amd64`)
* openSUSE 42.3 o versioni successive a 64 bit (`x86_64` o `amd64`)
* SUSE Enterprise Linux (SLES) 12 Service Pack 2 o versioni successive a 64 bit (`x86_64` o `amd64`)
* Alpine Linux 3.7 o versioni successive a 64 bit (`x86_64` o `amd64`)

Per l'elenco completo dei sistemi operativi, delle versioni e delle distribuzioni supportati da .NET Core 2.1 e .NET Core 2.2, nonché delle versioni di sistemi operativi non supportate e dei criteri relativi al ciclo di vita, vedere [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1 - Versioni di sistemi operativi supportate) e [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) (.NET Core 2.2 - Versioni di sistemi operativi supportate).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Per i collegamenti per il download e altre informazioni, vedere [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) (Download di .NET Core 1.1) o [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0) (Download di .NET Core 1.0).

NET Core 1.x è supportato nelle versioni/distribuzioni di Linux a 64 bit (`x86_64` o `amd64`) seguenti:

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 28 (.NET Core 1.1), 27
* Debian 8.2 o versioni successive
* Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04
* Linux Mint 17
* openSUSE 42.3 o versioni successive (.NET Core 1.1)

Per l'elenco completo di sistemi operativi, supportati da .NET Core 1.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 1.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).

# <a name="net-core-30-preview-1tabnetcore30"></a>[.NET Core 3.0 Preview 1](#tab/netcore30)

.NET core 3.0 Preview 1 considera Linux come un singolo sistema operativo. Esiste una sola build di Linux (per l'architettura chip) per le distribuzioni di Linux supportate. 

Per i collegamenti di download e altre informazioni, vedere [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0) (Download di .NET Core 3.0).

.NET Core 3.0 Preview 1 è supportato nelle seguenti distribuzioni/versioni di Linux. 

Sistema operativo                            | Versione               | Architetture  
------------------------------|-----------------------|----------------
Red Hat Enterprise Linux      | 6                     | X64
Red Hat Enterprise Linux<br>CentOS<br>Oracle Linux  | 7                     | X64
Fedora                        | 28                    | X64
Debian                        | 9                     | x64, ARM32\*, ARM64\*
Ubuntu                        | 16.04+, 18.04+        | x64, ARM32\*, ARM64\*
Linux Mint                    | 18                    | X64
openSUSE                      | 42.3+                 | X64
SUSE Enterprise Linux (SLES)  | 12 SP2+               | X64
Alpine Linux                  | 3.8+                  | x64, ARM64

\* Il supporto di ARM64 e ARM32 inizia con Debian 9 e Ubuntu 16.04. Le versioni precedenti di queste distribuzioni non sono supportate nei chip ARM.

Per l'elenco completo dei sistemi operativi, delle versioni e delle distribuzioni supportate da .NET Core 3.0, nonché delle versioni di sistemi operativi non supportate e dei criteri relativi al ciclo di vita, vedere [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) (.NET Core 3.0 - Versioni di sistemi operativi supportate).

Per altre informazioni su come installare .NET Core 3.0 su ARM64, vedere [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installazione di .NET Core 3.0 su Linux ARM64).

---

## <a name="linux-distribution-dependencies"></a>Dipendenze delle distribuzioni Linux

Quelli che seguono sono esempi. Le versioni e i nomi esatti possono variare leggermente nella distribuzione di Linux scelta.

### <a name="ubuntu"></a>Ubuntu

Le distribuzioni Ubuntu richiedono che siano installate le librerie seguenti:

* liblttng-ust0
* libcurl3 (per 14.x e 16.x)
* libcurl4 (per 18.x)
* libssl1.0.0
* libkrb5-3
* zlib1g
* libicu52 (per 14.X)
* libicu55 (per 16.X)
* libicu57 (per 17.X)
* libicu60 (per 18.x)

Per le versioni precedenti a .NET Core 2.1, sono richieste anche le dipendenze seguenti:

* libunwind8
* libuuid1

### <a name="centos-and-fedora"></a>CentOS e Fedora

Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:

* lttng-ust
* libcurl
* openssl-libs
* krb5-libs
* libicu
* zlib

Utenti Fedora: se la versione di openssl in uso è maggiore o uguale a 1.1, è necessario installare compat-openssl10.

Per le versioni precedenti a .NET Core 2.1, sono richieste anche le dipendenze seguenti:

* libunwind
* libuuid

Per altre informazioni sulle dipendenze, vedere [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Applicazioni Linux autonome).

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>Installazione delle dipendenze di .NET Core con i programmi di installazione nativi

Sono disponibili programmi di installazione .NET Core nativi per le distribuzioni/versioni di Linux supportate. I programmi di installazione richiedono l'accesso amministratore (sudo) al server. L'uso di un programma di installazione nativo offre il vantaggio di installare tutte le dipendenze native .NET Core. I programmi di installazione nativi installano.NET Core SDK a livello di sistema.

In Linux sono disponibili due opzioni relative al pacchetto di installazione:

* L'utilizzo di un sistema di gestione pacchetti basato su feed, ad esempio apt-get per Ubuntu o yum per CentOS/RHEL.
* L'utilizzo dei pacchetti stessi, DEB o RPM.

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Gli script vengono installati con lo script di installazione di .NET Core

Gli [script dotnet-install](./tools/dotnet-install-script.md) vengono usati per eseguire un'installazione senza privilegi di amministratore della toolchain dell'interfaccia della riga di comando e del runtime condiviso. È possibile scaricare lo script da <https://dot.net/v1/dotnet-install.sh>.

Lo script assume come impostazione predefinita l'installazione della versione "LTS" più recente, che è attualmente .NET Core 1.1. Per installare .NET Core 2.1, eseguire lo script con l'opzione seguente:

```console
./dotnet-install.sh -c Current
```

Lo script bash del programma di installazione viene usato negli scenari di automazione e nelle installazioni non di amministratore. Questo script legge anche le opzioni PowerShell, che possono quindi essere usate con lo script nei sistemi Linux/OS X.

## <a name="troubleshoot"></a>Risolvere i problemi

Se si verificano problemi in fase di installazione di .NET Core in una distribuzione/versione Linux supportata, vedere i seguenti argomenti per le distribuzioni/versioni installate in uso:

* [Problemi noti relativi a .NET Core 3.0](https://github.com/dotnet/core/tree/master/release-notes/3.0)
* [Problemi noti relativi a .NET Core 2.2](https://github.com/dotnet/core/tree/master/release-notes/2.2)
* [Problemi noti relativi a .NET Core 2.1](https://github.com/dotnet/core/tree/master/release-notes/2.1)
* [Problemi noti relativi a .NET Core 1.1](https://github.com/dotnet/core/blob/master/release-notes/1.1)
* [Problemi noti relativi a .NET Core 1.0](https://github.com/dotnet/core/blob/master/release-notes/1.0)

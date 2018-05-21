---
title: Prerequisiti per .NET Core in Linux
description: Versioni Linux supportate e dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer Linux.
author: jralexander
ms.author: johalex
ms.date: 05/08/2018
ms.openlocfilehash: 41656bf8f18c2b66c35f0a65e4af0949db4464f9
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
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

NET Core 2.x è supportato nelle versioni/distribuzioni di Linux a 64 bit (`x86_64` o `amd64`) seguenti:

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 27, 26
* Debian 9, 8.7 o versioni successive
* Ubuntu 18.04, 17.10, 16.04, 14.04
* Linux Mint 18, 17
* openSUSE 42.3 o versioni successive
* SUSE Enterprise Linux (SLES) 12 Service Pack 2 o versioni successive

Per l'elenco completo di sistemi operativi supportati da .NET Core 2.x, le versioni e le distribuzioni, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

NET Core 1.x è supportato nelle versioni/distribuzioni di Linux a 64 bit (`x86_64` o `amd64`) seguenti:

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 26
* Debian 8.2 o versioni successive
* Ubuntu 16.04, 14.04
* Linux Mint 18, 17
* openSUSE 42.3 o versioni successive (.NET Core 1.1)

Per l'elenco completo di sistemi operativi, supportati da .NET Core 1.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 1.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).

---

## <a name="linux-distribution-dependencies"></a>Dipendenze delle distribuzioni Linux

Quelli che seguono sono esempi. Le versioni e i nomi esatti possono variare leggermente nella distribuzione di Linux scelta.

### <a name="ubuntu"></a>Ubuntu

Le distribuzioni Ubuntu richiedono che siano installate le librerie seguenti:

* libunwind8
* liblttng-ust0
* libcurl3
* libssl1.0.0
* libuuid1
* libkrb5-3
* zlib1g
* libicu52 (per 14.X)
* libicu55 (per 16.X)
* libicu57 (per 17.X)

### <a name="centos"></a>CentOS

Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:

* libunwind
* lttng-ust
* libcurl
* openssl-libs
* libuuid
* krb5-libs
* libicu
* zlib

Per altre informazioni sulle dipendenze, vedere [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Applicazioni Linux autonome).

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>Installazione delle dipendenze di .NET Core con i programmi di installazione nativi

Sono disponibili programmi di installazione .NET Core nativi per le distribuzioni/versioni di Linux supportate. I programmi di installazione richiedono l'accesso amministratore (sudo) al server. L'uso di un programma di installazione nativo offre il vantaggio di installare tutte le dipendenze native .NET Core. I programmi di installazione nativi installano.NET Core SDK a livello di sistema.

In Linux sono disponibili due opzioni relative al pacchetto di installazione:

* L'utilizzo di un sistema di gestione pacchetti basato su feed, ad esempio apt-get per Ubuntu o yum per CentOS/RHEL.
* L'utilizzo dei pacchetti stessi, DEB o RPM.

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Gli script vengono installati con lo script di installazione di .NET Core

Gli [script dotnet-install](./tools/dotnet-install-script.md) vengono usati per eseguire un'installazione senza privilegi di amministratore della toolchain dell'interfaccia della riga di comando e del runtime condiviso. È possibile scaricare lo script da [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh).

Lo script bash del programma di installazione viene usato negli scenari di automazione e nelle installazioni non di amministratore. Questo script legge anche le opzioni PowerShell, che possono quindi essere usate con lo script nei sistemi Linux/OS X.

## <a name="install-net-core-for-supported-red-hat-enterprise-linux-rhel-versions"></a>Installare .NET Core per le versioni di Red Hat Enterprise Linux (RHEL) supportate

Per installare .NET Core nelle versioni RHEL supportate:

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Per verificare di disporre delle informazioni di installazione più recenti, seguire le [istruzioni del programma di installazione di Runtime e di .NET Core 2.x SDK](https://www.microsoft.com/net/download/linux-package-manager/rhel/sdk-current) per le versioni RHEL supportate.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**.NET Core 1.1**

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

2.  Per le informazioni più recenti sull'installazione di .NET Core 1.1 su Red Hat Enterprise Linux, vedere la [guida introduttiva a .NET Core 1.1](https://access.redhat.com/documentation/en-us/net_core/1.1/html/getting_started_guide/)
     
**.NET Core 1.0**

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

2.  Per le informazioni più recenti sull'installazione di .NET Core 1.0 su Red Hat Enterprise Linux, vedere la [guida introduttiva a .NET Core 1.0](https://access.redhat.com/documentation/en-us/net_core/1.0/html/getting_started_guide/)

Per informazioni sulla registrazione dell'accesso al canale Red Hat .NET, vedere [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) (Capitolo 1 dell'Introduzione a .NET Core 1.1) in Red Hat.

---

## <a name="install-net-core-for-supported-ubuntu-and-linux-mint-distributionsversions-64-bit"></a>Installare .NET Core per le versioni/distribuzioni di Ubuntu e Linux Mint supportate (64 bit)

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

2. Installare .NET Core 2.x sulle versioni/distribuzioni di Ubuntu e Linux Mint supportate (64 bit):

**.NET Core 2.0**

|Runtime/SDK          |Ubuntu 18.04    |Ubuntu 17.10    |Ubuntu 16.04/Linux Mint 18|Ubuntu 14.04/Linux Mint 17|
|-------------------------|----------------|----------------|----------------------------|----------------------------|
|Runtime di .NET Core 2.0.7  |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.7)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.7)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.7)          |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.7)            |
|Runtime di .NET Core 2.0.6  |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.6)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.6)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.6)          |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.6)            |
|Runtime di .NET Core 2.0.5  |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.5)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.5)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.5)          |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.5)            |
|.NET Core SDK 2.1.105    |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.105)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.105)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.105)            |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.105)            |
|.NET Core SDK 2.1.103    |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.103)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.103)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.103)            |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.103)            |
|.NET Core SDK 2.0.3      |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.0.3)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.3)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.3)          |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.3)            |
|.NET Core SDK 2.0.0      |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.0.0)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.0)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.0)          |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.0)            |

**.NET Core 2.1**

>[!IMPORTANT]
> Per usare .NET Core 2.1 con Visual Studio, è necessario [installare Visual Studio 2017 15.7 Preview 1 o versione successiva](https://www.visualstudio.com/vs/preview).

|Runtime/SDK                  |Ubuntu 18.04    |Ubuntu 17.10    |Ubuntu 16.04/Linux Mint 18|Ubuntu 14.04/Linux Mint 17|
|---------------------------------|----------------|----------------|----------------------------|----------------------------|
|Runtime di .NET Core 2.1.0-rc1      |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.0-rc1)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-rc1)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-rc1)            |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-rc1)            |
|Runtime di .NET Core 2.1.0-preview2 |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.0-preview2)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview2)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview2)            |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview2)            |
|Runtime di .NET Core 2.1.0-preview1 |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.0-preview1)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview1)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview1)            |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview1)            |
|.NET Core SDK 2.1.300-rc1  |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.300-rc1)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-rc1)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-rc1)            |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-rc1)            |
|.NET Core SDK 2.1.300-preview2   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.300-preview2)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview2)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview2)            |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview2)            |
|.NET Core SDK 2.1.300-preview1   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.300-preview1)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview1)|[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview1)            |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview1)            |


# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

2. Installare .NET Core 1.x sulle versioni/distribuzioni di Ubuntu e Linux Mint supportate (64 bit):

| Runtime/SDK         |Ubuntu 16.04/Linux Mint 18|Ubuntu 14.04/Linux Mint 17|
|-------------------------|----------------------------|----------------------------|
|Runtime di .NET Core 1.1.7  |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|Runtime di .NET Core 1.1.6  |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-16.04-x64-binaries)            |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-14.04-x64-binaries)            |
|Runtime di .NET Core 1.0.10 |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-16.04-x64-binaries)            |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-14.04-x64-binaries)            |
|Runtime di .NET Core 1.0.9  |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-16.04-x64-binaries)            |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.8      |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-16.04-x64-binaries)            |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.7      |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.0.4      |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-16.04-x64-binaries)            |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.0.1      |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-16.04-x64-binaries)            |[Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-14.04-x64-binaries)            |

---

## <a name="install-net-core-for-supported-debian-versions-64-bit"></a>Installare .NET Core per le versioni Debian supportate (64 bit)

Installare .NET Core nelle versioni Debian supportate (64 bit):

> [!NOTE]
> È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

2. Installare .NET Core 2.x nelle versioni Debian supportate (64 bit):

**.NET Core 2.0**

|Runtime/SDK          |Debian 9       |Debian 8       |
|-------------------------|---------------|---------------|
|Runtime di .NET Core 2.0.7  |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.7)   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.7)   |
|Runtime di .NET Core 2.0.6  |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.6)   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.6)   |
|Runtime di .NET Core 2.0.5  |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.5)   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.5)   |
|.NET Core SDK 2.1.105    |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.105)   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.105)   |
|.NET Core SDK 2.1.103    |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.103)   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.103)   |
|.NET Core SDK 2.0.3      |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.3)   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.3)   |
|.NET Core SDK 2.0.0      |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.0)   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.0)   |

**.NET Core 2.1**

>[!IMPORTANT]
> Per usare .NET Core 2.1 con Visual Studio, è necessario [installare Visual Studio 2017 15.7 Preview 1 o versione successiva](https://www.visualstudio.com/vs/preview).

|Runtime/SDK                  |Debian 9       |Debian 8       |
|---------------------------------|---------------|---------------|
|Runtime di .NET Core 2.1.0-rc1      |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-rc1)   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-rc1)   |
|Runtime di .NET Core 2.1.0-preview2 |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview2)   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview2)   |
|Runtime di .NET Core 2.1.0-preview1 |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview1)   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview1)   |
|.NET Core SDK 2.1.300-rc1        |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-rc1)   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-rc1)        |
|.NET Core SDK 2.1.300-preview2   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview2)   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview2)   |
|.NET Core SDK 2.1.300-preview1   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview1)   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview1)   |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

2. Installare .NET Core 1.x in Debian 9 o Debian 8:

* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-debian-x64-binaries) di Runtime di .NET Core 1.1.7
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-debian-x64-binaries) di Runtime di .NET Core 1.1.6
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-debian-x64-binaries) di Runtime di .NET Core 1.0.10
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-debian-x64-binaries) di Runtime di .NET Core 1.0.9
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-debian-x64-binaries) di .NET Core SDK 1.1.8
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-debian-x64-binaries) di .NET Core SDK 1.1.7
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-debian-x64-binaries) di .NET Core SDK 1.0.4
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries) di .NET Core SDK 1.0.1

---

## <a name="install-net-core-for-supported-fedora-versions-64-bit"></a>Installare .NET Core per le versioni Fedora supportate (64 bit)

Per installare .NET Core nelle versioni Fedora supportate:

> [!NOTE]
> È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

2. Installare .NET Core 2.x nelle versioni Fedora supportate (64 bit):

**.NET Core 2.0**

|Runtime/SDK          |Fedora 26 o versione successiva |Fedora 25 o versione precedente |
|-------------------------|-------------------|----------------------|
|Runtime di .NET Core 2.0.7  |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.7)       |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.7)           |
|Runtime di .NET Core 2.0.6  |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.6)       |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.6)           |
|Runtime di .NET Core 2.0.5  |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.5)       |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.5)           |
|.NET Core SDK 2.1.105    |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.105)       |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.105)           |
|.NET Core SDK 2.1.103    |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.103)       |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.103)           |
|.NET Core SDK 2.0.3      |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.0.3)       |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.0.3)           |

**.NET Core 2.1**

>[!IMPORTANT]
> Per usare .NET Core 2.1 con Visual Studio, è necessario [installare Visual Studio 2017 15.7 Preview 1 o versione successiva](https://www.visualstudio.com/vs/preview).

|Runtime/SDK                  |Fedora 27          |Fedora 26             |
|---------------------------------|-------------------|----------------------|
|Runtime di .NET Core 2.1.0-rc1      |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.0-rc1)       |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-rc1)           |
|Runtime di .NET Core 2.1.0-preview2 |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.0-preview2)       |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview2)           |
|Runtime di .NET Core 2.1.0-preview1 |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.0-preview1)       |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview1)           |
|.NET Core SDK 2.1.300-rc1        |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.300-rc1)       |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-rc1)           |
|.NET Core SDK 2.1.300-preview2   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.300-preview2)       |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-preview2)           |
|.NET Core SDK 2.1.300-preview1   |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.0-preview1)       |[Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview1)           |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

2. Installare .NET Core 1.x nelle versioni Fedora supportate (64 bit):

**Fedora 24**

* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-fedora-24-x64-binaries) di Runtime di .NET Core 1.1.7
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-fedora-24-x64-binaries) di Runtime di .NET Core 1.1.6
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-fedora-24-x64-binaries) di .NET Core SDK 1.1.8
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-fedora-24-x64-binaries) di .NET Core SDK 1.1.7
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries) di .NET Core SDK 1.0.1

**Fedora 23**

* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-fedora-23-x64-binaries) di Runtime di .NET Core 1.0.9
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-fedora-23-x64-binaries) di .NET Core SDK 1.0.4
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-fedora-23-x64-binaries) di .NET Core SDK 1.0.1

---

## <a name="install-net-core-for-supported-centos-and-oracle-linux-distributionsversions-64-bit"></a>Installare .NET Core per le distribuzioni/versioni di CentOS e Oracle Linux supportate (64 bit)

Per installare .NET Core per le distribuzioni/versioni di CentOS e Oracle Linux supportate (64 bit):

> [!NOTE]
> È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

2. Installare .NET Core 2.x nelle distribuzioni/versioni di CentOS e Oracle Linux supportate (64 bit):

**.NET Core 2.0**

* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6) di Runtime di .NET Core 2.0.7
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6) di Runtime di .NET Core 2.0.6
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.5) di Runtime di .NET Core 2.0.5
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.105) di .NET Core SDK 2.1.105
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.103) di .NET Core SDK 2.1.103
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.3) di .NET Core SDK 2.0.3
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.0) di .NET Core SDK 2.0.0
 
**.NET Core 2.1**

>[!IMPORTANT]
> Per usare .NET Core 2.1 con Visual Studio, è necessario [installare Visual Studio 2017 15.7 Preview 1 o versione successiva](https://www.visualstudio.com/vs/preview/).

* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-rc1) di Runtime di .NET Core 2.1.0-rc1
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview2) di Runtime di .NET Core 2.1.0-preview2
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview1) di Runtime di .NET Core 2.1.0-preview1
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-rc1) di Runtime di .NET Core SDK 2.1.300-rc1
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview2) di .NET Core SDK 2.1.300-preview2
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview1) di .NET Core SDK 2.1.300-preview1

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

2. Installare .NET Core 1.x nelle distribuzioni/versioni di CentOS e Oracle Linux supportate (64 bit):

* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-centos-x64-binaries) di Runtime di .NET Core 1.1.7
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-centos-x64-binaries) di Runtime di .NET Core 1.1.6
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-centos-x64-binaries) di Runtime di .NET Core 1.0.10
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-centos-x64-binaries) di Runtime di .NET Core 1.0.9
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-centos-x64-binaries) di .NET Core SDK 1.1.8
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-centos-x64-binaries) di .NET Core SDK 1.1.7
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-centos-x64-binaries) di .NET Core SDK 1.0.4
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-centos-x64-binaries) di .NET Core SDK 1.0.1

---

## <a name="install-net-core-for-supported-suse-linux-enterprise-server-and-opensuse-distributionsversions-64-bit"></a>Installare .NET Core per le distribuzioni/versioni di SUSE Linux Enterprise Server e OpenSUSE supportate (64 bit)

Per installare .NET Core 2.x per le distribuzioni/versioni di SUSE Linux Enterprise Server e OpenSUSE supportate (64 bit):

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

2. Installare .NET Core 2.x nelle distribuzioni/versioni di SUSE Linux Enterprise Server e OpenSUSE supportate (64 bit):

**.NET Core 2.0**

**SUSE Linux Enterprise Server**

* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.7) di Runtime di .NET Core 2.0.7
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.6) di Runtime di .NET Core 2.0.6
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.5) di Runtime di .NET Core 2.0.5
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.105) di .NET Core SDK 2.1.105
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.103) di .NET Core SDK 2.1.103
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.0.3) di .NET Core SDK 2.0.3
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.0.0) di .NET Core SDK 2.0.0

**openSUSE**

* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.7) di Runtime di .NET Core 2.0.7
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.6) di Runtime di .NET Core 2.0.6
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.5) di Runtime di .NET Core 2.0.5
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.105) di .NET Core SDK 2.1.105
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.103) di .NET Core SDK 2.1.103
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.3) di .NET Core SDK 2.0.3
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.0) di .NET Core SDK 2.0.0
 
**.NET Core 2.1**

>[!IMPORTANT]
> Per usare .NET Core 2.1 con Visual Studio, è necessario [installare Visual Studio 2017 15.7 Preview 1 o versione successiva](https://www.visualstudio.com/vs/preview).

**SUSE Linux Enterprise Server**

* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.0-rc1) di Runtime di .NET Core 2.1.0-rc1
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.0-preview2) di Runtime di .NET Core 2.1.0-preview2
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.0-preview1) di Runtime di .NET Core 2.1.0-preview1
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.300-rc1) di Runtime di .NET Core SDK 2.1.300-rc1
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.300-preview2) di .NET Core SDK 2.1.300-preview2
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.300-preview1) di .NET Core SDK 2.1.300-preview1

**openSUSE**

* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-rc1) di Runtime di .NET Core 2.1.0-rc1
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview2) di Runtime di .NET Core 2.1.0-preview2
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview1) di Runtime di .NET Core 2.1.0-preview1
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-rc1) di Runtime di .NET Core SDK 2.1.300-rc1
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview2) di .NET Core SDK 2.1.300-preview2
* [Collegamento di installazione](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview1) di .NET Core SDK 2.1.300-preview1

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

2. Installare .NET Core 1.x nelle distribuzioni/versioni di SUSE Linux Enterprise Server e OpenSUSE supportate (64 bit):

**SUSE Linux Enterprise Server 13.2**

* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-opensuse-13.2-x64-binaries) di Runtime di .NET Core 1.1.7
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-opensuse-13.2-x64-binaries) di Runtime di .NET Core 1.1.6
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-opensuse-13.2-x64-binaries) di .NET Core SDK 1.1.7

**openSUSE 24**

* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-opensuse-24-x64-binaries) di .NET Core SDK 1.0.4
* [Collegamento di installazione](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-opensuse-24-x64-binaries) di .NET Core SDK 1.0.1

---

> [!IMPORTANT]
> Se si verificano problemi in fase di installazione di .NET Core in una distribuzione/versione Linux supportata, vedere i seguenti argomenti per le distribuzioni/versioni installate in uso:
> * [Problemi noti relativi a .NET Core 2.1](https://github.com/dotnet/core/tree/master/release-notes/2.1)
> * [Problemi noti relativi a .NET Core 2.0](https://github.com/dotnet/core/tree/master/release-notes/2.0)
> * [Problemi noti relativi a .NET Core 1.1](https://github.com/dotnet/core/blob/master/release-notes/1.1)
> * [Problemi noti relativi a .NET Core 1.0](https://github.com/dotnet/core/blob/master/release-notes/1.0)
---
title: Prerequisiti per .NET Core in Linux
description: Versioni Linux supportate e dipendenze .NET Core necessarie per lo sviluppo, la distribuzione e l'esecuzione di applicazioni .NET Core su computer Linux.
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 1b0379156f44b0a3e765f8d832c7a1ca74ee3598
ms.openlocfilehash: d9da6ea27293e95e36ff8edc42ef8bafbc86c8ec
ms.contentlocale: it-it
ms.lasthandoff: 09/08/2017

---

# <a name="prerequisites-for-net-core-on-linux"></a>Prerequisiti per .NET Core in Linux

Questo articolo illustra le dipendenze necessarie per sviluppare applicazioni .NET Core in Linux. Le distribuzioni/versioni Linux supportate e le dipendenze seguenti si applicano alle due modalità di sviluppo di app .NET Core in Linux:

* [Riga di comando con l'editor preferito](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a>Versioni di Linux supportate

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET core 2.0 considera Linux un singolo sistema operativo. Esiste una sola build di Linux (per l'architettura chip) per le distribuzioni di Linux supportate.

NET Core 2.x è supportato nelle versioni/distribuzioni di Linux a 64 bit (`x86_64` o `amd64`) seguenti:

 * Red Hat Enterprise Linux 7
 * CentOS 7
 * Oracle Linux 7
 * Fedora 25, Fedora 26
 * Debian 8.7 o versioni successive 
 * Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04
 * Linux Mint 18, Linux Mint 17
 * openSUSE 42.2 o versioni successive
 * SUSE Enterprise Linux (SLES) 12 SP2 o versioni successive

Per l'elenco completo di sistemi operativi supportati da .NET Core 2.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

NET Core 1.x è supportato nelle versioni/distribuzioni di Linux a 64 bit (`x86_64` o `amd64`) seguenti:

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 24
* Debian 8.2 o versioni successive
* Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*
 * Ubuntu 16.10 è supportato dalla versione patch più recente di .NET Core 1.1
* Linux Mint 17
* openSUSE 42.1 o versioni successive (.NET Core 1.1)

Per l'elenco completo di sistemi operativi, supportati da .NET Core 1.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 1.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).

---

## <a name="linux-distribution-dependencies"></a>Dipendenze delle distribuzioni Linux

### <a name="ubuntu"></a>Ubuntu

Le distribuzioni Ubuntu richiedono che siano installate le librerie seguenti:

* libunwind8
* libunwind8-dev
* gettext
* libicu-dev
* liblttng-ust-dev
* libcurl4-openssl-dev
* libssl-dev
* uuid-dev
* unzip

### <a name="centos"></a>CentOS

Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:

* deltarpm
* epel-release
* unzip
* libunwind
* gettext
* libcurl-devel
* openssl-devel
* zlib
* libicu-devel

Per altre informazioni sulle dipendenze, vedere [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Applicazioni Linux autonome).

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>Installazione delle dipendenze di .NET Core con i programmi di installazione nativi

Sono disponibili programmi di installazione .NET Core nativi per le distribuzioni/versioni di Linux supportate. I programmi di installazione richiedono l'accesso amministratore (sudo) al server. L'uso di un programma di installazione nativo offre il vantaggio di installare tutte le dipendenze native .NET Core. I programmi di installazione nativi installano.NET Core SDK a livello di sistema.

In Linux sono disponibili due opzioni relative al pacchetto di installazione:

* L'utilizzo di un sistema di gestione pacchetti basato su feed, ad esempio apt-get per Ubuntu o yum per CentOS/RHEL.
* L'utilizzo dei pacchetti stessi, DEB o RPM.

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Gli script vengono installati con lo script di installazione di .NET Core

Gli script `dotnet-install` vengono usati per eseguire un'installazione senza privilegi di amministratore della toolchain dell'interfaccia della riga di comando e del runtime condiviso. È possibile scaricare gli script dal [repository di GitHub dell'interfaccia della riga di comando](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain).

Lo script bash del programma di installazione viene usato negli scenari di automazione e nelle installazioni non di amministratore. Questo script legge anche le opzioni PowerShell, che possono quindi essere usate con lo script nei sistemi Linux/OS X.

> [!IMPORTANT]
> Prima di eseguire lo script, installare le [dipendenze](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necessarie.

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a>Installare .NET Core per Red Hat Enterprise Linux (RHEL) 7

Per installare .NET Core in RHEL 7:

1. Abilitare il canale di Red Hat .NET, disponibile nella sottoscrizione di RHEL 7.
    * Per Red Hat Enterprise Server 7, usare:
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * Per Red Hat Enterprise 7 Workstation, usare:
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * Per il nodo di calcolo HPC di Red Hat Enterprise 7, usare:
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. Installare lo strumento scl.

    ```bash
    yum install scl-utils
    ```
    
3. Installare .NET Core

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Installare .NET Core 2.0 SDK e Runtime:

   ```bash
   yum install rh-dotnet20
   ```

Abilitare .NET Core 2.0 SDK/Runtime per l'ambiente:

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**.NET Core 1.1**

Installare .NET Core 1.1 SDK e Runtime:

   ```bash
   yum install rh-dotnetcore11
   ```

Abilitare .NET Core 1.1 SDK e Runtime per l'ambiente:

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

**.NET Core 1.0**

Installare .NET Core 1.0 SDK e Runtime:

   ```bash
   yum install rh-dotnetcore10
   ```

Abilitare .NET Core 1.0 SDK e Runtime per l'ambiente:

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.

     ```bash
     dotnet --version
     ```

Per informazioni sulla registrazione dell'accesso al canale Red Hat .NET, vedere [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) (Capitolo 1 dell'Introduzione a .NET Core 1.1) in Red Hat.

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a>Installare .NET Core per Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Registrare il codice Product Key Microsoft come attendibile.

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. Impostare il feed di pacchetti host della versione desiderata.

   **Ubuntu 17.04**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   **Ubuntu 16.04/Linux Mint 18**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   **Ubuntu 14.04/Linux Mint 17**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. Installare .NET Core.

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Impostare il feed di pacchetti host della versione desiderata.

   **Ubuntu 16.10**
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  **Ubuntu 16.04/Linux Mint 18**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   **Ubuntu 14.04/Linux Mint 17**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. Installare .NET Core 1.x in Ubuntu o Linux Mint:

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a>Installare .NET Core per Debian 8 o Debian 9 (64 bit)

Per installare .NET Core in Debian 8 o Debian 9 (64 bit):

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

> [!NOTE]
> È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Installare i componenti di sistema.

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. Registrare il codice Product Key Microsoft attendibile.

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. Registrare il feed per il prodotto Microsoft.

   **Debian 9 (Stretch)**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   **Debian 8 (Jessie)**
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. Installare .NET Core SDK.

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. Aggiungere dotnet al PERCORSO.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```
   
7. Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.

   ```bash
   dotnet --version
   ```   
  

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Ottenere i prerequisiti.

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. Scaricare i binari di .NET Core SDK (tarball).

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. Estrarre i binari di .NET Core SDK.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Aggiungere dotnet al PERCORSO.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

6. Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.

   ```bash
   dotnet --version
   ```

---

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a>Installare .NET Core per Fedora 24, Fedora 25 o Fedora 26 (64 bit)

Per installare .NET Core 2.x in Fedora 26 o Fedora 25 oppure .NET Core 1.x in Fedora 24:

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

> [!NOTE]
> È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**Fedora 26 o Fedora 25**

2. Registrare la chiave di firma Microsoft.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. Aggiungere il feed del prodotto dotnet.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. Installare .NET Core SDK.

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. Aggiungere dotnet al PERCORSO.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**Fedora 24**

2. Ottenere i prerequisiti.

   ```bash
   sudo dnf install libunwind libicu
   ```

3. Scaricare il binario di .NET Core SDK (tarball).

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. Estrarre i binari di .NET Core SDK.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Aggiungere dotnet al PERCORSO.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a>Installare .NET Core per CentOS 7.1 (64 bit) e Oracle Linux 7.1 (64 bit)

Per installare .NET Core per CentOS 7.1 (64 bit) e Oracle Linux 7.1 (64 bit):

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

> [!NOTE]
> È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Registrare la chiave di firma Microsoft.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. Aggiungere il feed del prodotto Microsoft.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. Installare .NET Core SDK.

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. Aggiungere dotnet a PATH

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Ottenere i prerequisiti.

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. Scaricare il binario di .NET Core SDK (tarball).

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. Estrarre i binari di .NET Core SDK.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Aggiungere dotnet al PERCORSO.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a>Installare .NET Core per SUSE Linux Enterprise Server (64 bit)

Per installare .NET Core 2.x per SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

2. Aggiungere il feed del prodotto dotnet.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. Installare .NET Core SDK.

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. Aggiungere dotnet al PERCORSO.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a>Installare .NET Core per openSUSE (64 bit)

Per installare .NET Core 2.x per openSUSE o .NET Core 1.x per openSUSE (64 bit):

1. Rimuovere eventuali versioni di **anteprima precedenti** di .NET Core dal sistema.

> [!NOTE]
> È necessaria una directory controllata dall'utente per le installazioni del sistema Linux da tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Registrare la chiave di firma Microsoft.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. Aggiungere il feed del prodotto dotnet.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. Installare .NET Core SDK.

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. Aggiungere dotnet al PERCORSO.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Ottenere i prerequisiti.

   ```bash
   sudo zypper install libunwind libicu
   ```

3. Scaricare il binario di .NET Core SDK (tarball).

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. Estrarre i binari di .NET Core SDK.
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Aggiungere dotnet al PERCORSO.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. Eseguire il comando `dotnet --version` per provare se l'installazione ha avuto esito positivo.

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> Se si verificano problemi in fase di installazione di .NET Core 2.x in una distribuzione/versione Linux supportata, vedere l'argomento [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) (Problemi noti della versione 2.0) per le distribuzioni/versioni installate in uso. 
>
> Se si verificano problemi in fase di installazione di .NET Core 1.x in una distribuzione/versione Linux supportata, vedere gli argomenti [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) (Problemi noti della versione 1.0.0) e [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) (Problemi noti della versione 1.0.1) per le distribuzioni/versioni installate in uso.


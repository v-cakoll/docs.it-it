---
title: Installare dipendenze ML.NET aggiuntiveInstall extra ML.NET dependencies
description: Informazioni su come installare le librerie native da cui ML.NET pacchetti dipendono ma non vengono installati con i pacchetti NuGet
ms.date: 04/02/2020
author: natke
ms.author: nakersha
ms.custom: how-to
ms.openlocfilehash: 0b870542706c065295d48205b7780e568e267ab6
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888302"
---
# <a name="install-extra-mlnet-dependencies"></a>Installare dipendenze ML.NET aggiuntiveInstall extra ML.NET dependencies

Nella maggior parte dei casi, in tutti i sistemi operativi, l'installazione di ML.NET è semplice come fare riferimento al pacchetto NuGet appropriato.

```bash
dotnet add package Microsoft.ML
```

In alcuni casi, tuttavia, esistono requisiti di installazione aggiuntivi, in particolare quando sono necessari componenti nativi. In questo documento vengono descritti i requisiti di installazione per tali casi. Le sezioni sono suddivise `Microsoft.ML.*` dal pacchetto NuGet specifico con la dipendenza aggiuntiva.

## <a name="microsoftmltimeseries-microsoftmlautoml"></a>Microsoft.ML.TimeSeries, Microsoft.ML.AutoML

Entrambi questi pacchetti hanno una `Microsoft.ML.MKL.Redist`dipendenza da , `libiomp`che ha una dipendenza da .

### <a name="windows"></a>Windows

Non sono necessarie procedure di installazione aggiuntive. La libreria viene installata quando il pacchetto NuGet viene aggiunto al progetto.

### <a name="linux"></a>Linux

1. Installare la chiave GPG per il repository

    ```bash
    sudo bash
    # <type your user password when prompted.  this will put you in a root shell>
    # cd to /tmp where this shell has write permission
    cd /tmp
    # now get the key:
    wget https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    # now install that key
    apt-key add GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    # now remove the public key file exit the root shell
    rm GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    exit
    ```

2. Aggiungere il repository APT per MKL

    ```bash
    sudo sh -c 'echo deb https://apt.repos.intel.com/mkl all main > /etc/apt/sources.list.d/intel-mkl.list'
    ```

3. Aggiornamento di pacchetti

    ```bash
    sudo apt-get update
    ```

4. Installare MKL

    ```bash
    sudo apt-get install <COMPONENT>-<VERSION>.<UPDATE>-<BUILD_NUMBER>
    ```

    Ad esempio:

    ```bash
    sudo apt-get install intel-mkl-64bit-2020.0-088
    ```

    Determinare la posizione`libiomp.so`

    ```bash
    find /opt -name "libiomp5.so"
    ```

    Ad esempio:

    ```output
    /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_lin/libiomp5.so
    ```

5. Aggiungere questo percorso al percorso della libreria di caricamento:Add this location to the load library path:

    ```bash
    sudo ldconfig /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_li
    ```

### <a name="mac"></a>Mac

1. Installare la libreria con`Homebrew`

    ```bash
    brew update && brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/f5b1ac99a7fba27c19cee0bc4f036775c889b359/Formula/libomp.rb && brew link libomp --force
    ```

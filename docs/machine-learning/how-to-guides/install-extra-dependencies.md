---
title: Installare dipendenze ML.NET aggiuntive
description: Informazioni su come installare le librerie native da cui dipendono i pacchetti ML.NET, ma che non vengono installate con i pacchetti NuGet
ms.date: 04/02/2020
author: natke
ms.author: nakersha
ms.custom: how-to
ms.openlocfilehash: c744b42b4b95681de7b0cbeaef338cc890708fd8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008430"
---
# <a name="install-extra-mlnet-dependencies"></a><span data-ttu-id="78eef-103">Installare dipendenze ML.NET aggiuntive</span><span class="sxs-lookup"><span data-stu-id="78eef-103">Install extra ML.NET dependencies</span></span>

<span data-ttu-id="78eef-104">Nella maggior parte dei casi, in tutti i sistemi operativi, l'installazione di ML.NET è semplice quanto il riferimento al pacchetto NuGet appropriato.</span><span class="sxs-lookup"><span data-stu-id="78eef-104">In most cases, on all operating systems, installing ML.NET is as simple as referencing the appropriate NuGet package.</span></span>

```dotnetcli
dotnet add package Microsoft.ML
```

<span data-ttu-id="78eef-105">In alcuni casi, tuttavia, sono previsti requisiti di installazione aggiuntivi, in particolare quando sono necessari componenti nativi.</span><span class="sxs-lookup"><span data-stu-id="78eef-105">In some cases though, there are additional installation requirements, particularly when native components are required.</span></span> <span data-ttu-id="78eef-106">Questo documento descrive i requisiti di installazione per questi casi.</span><span class="sxs-lookup"><span data-stu-id="78eef-106">This document describes the installation requirements for those cases.</span></span> <span data-ttu-id="78eef-107">Le sezioni sono suddivise in base al `Microsoft.ML.*` pacchetto NuGet specifico con la dipendenza aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="78eef-107">The sections are broken down by the specific `Microsoft.ML.*` NuGet package that has the additional dependency.</span></span>

## <a name="microsoftmltimeseries-microsoftmlautoml"></a><span data-ttu-id="78eef-108">Microsoft. ML. TimeSeries, Microsoft. ML. AutoML</span><span class="sxs-lookup"><span data-stu-id="78eef-108">Microsoft.ML.TimeSeries, Microsoft.ML.AutoML</span></span>

<span data-ttu-id="78eef-109">Entrambi i pacchetti hanno una dipendenza da `Microsoft.ML.MKL.Redist` , che ha una dipendenza da `libiomp` .</span><span class="sxs-lookup"><span data-stu-id="78eef-109">Both of these packages have a dependency on `Microsoft.ML.MKL.Redist`, which has a dependency on `libiomp`.</span></span>

### <a name="windows"></a><span data-ttu-id="78eef-110">Windows</span><span class="sxs-lookup"><span data-stu-id="78eef-110">Windows</span></span>

<span data-ttu-id="78eef-111">Non sono necessari passaggi aggiuntivi per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="78eef-111">No extra installation steps required.</span></span> <span data-ttu-id="78eef-112">La libreria viene installata quando il pacchetto NuGet viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="78eef-112">The library is installed when the NuGet package is added to the project.</span></span>

### <a name="linux"></a><span data-ttu-id="78eef-113">Linux</span><span class="sxs-lookup"><span data-stu-id="78eef-113">Linux</span></span>

1. <span data-ttu-id="78eef-114">Installare la chiave GPG per il repository</span><span class="sxs-lookup"><span data-stu-id="78eef-114">Install the GPG key for the repository</span></span>

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

2. <span data-ttu-id="78eef-115">Aggiungere il repository APT per MKL</span><span class="sxs-lookup"><span data-stu-id="78eef-115">Add the APT Repository for MKL</span></span>

    ```bash
    sudo sh -c 'echo deb https://apt.repos.intel.com/mkl all main > /etc/apt/sources.list.d/intel-mkl.list'
    ```

3. <span data-ttu-id="78eef-116">Aggiornamento di pacchetti</span><span class="sxs-lookup"><span data-stu-id="78eef-116">Update packages</span></span>

    ```bash
    sudo apt-get update
    ```

4. <span data-ttu-id="78eef-117">Installare MKL</span><span class="sxs-lookup"><span data-stu-id="78eef-117">Install MKL</span></span>

    ```bash
    sudo apt-get install <COMPONENT>-<VERSION>.<UPDATE>-<BUILD_NUMBER>
    ```

    <span data-ttu-id="78eef-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="78eef-118">For example:</span></span>

    ```bash
    sudo apt-get install intel-mkl-64bit-2020.0-088
    ```

    <span data-ttu-id="78eef-119">Determinare il percorso di`libiomp.so`</span><span class="sxs-lookup"><span data-stu-id="78eef-119">Determine the location of `libiomp.so`</span></span>

    ```bash
    find /opt -name "libiomp5.so"
    ```

    <span data-ttu-id="78eef-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="78eef-120">For example:</span></span>

    ```output
    /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_lin/libiomp5.so
    ```

5. <span data-ttu-id="78eef-121">Aggiungere questo percorso al percorso della libreria di caricamento:</span><span class="sxs-lookup"><span data-stu-id="78eef-121">Add this location to the load library path:</span></span>

    ```bash
    sudo ldconfig /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_lin
    ```

### <a name="mac"></a><span data-ttu-id="78eef-122">Mac</span><span class="sxs-lookup"><span data-stu-id="78eef-122">Mac</span></span>

1. <span data-ttu-id="78eef-123">Installare la libreria con`Homebrew`</span><span class="sxs-lookup"><span data-stu-id="78eef-123">Install the library with `Homebrew`</span></span>

    ```bash
    brew update && brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/f5b1ac99a7fba27c19cee0bc4f036775c889b359/Formula/libomp.rb && brew link libomp --force
    ```

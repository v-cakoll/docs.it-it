---
ms.openlocfilehash: 164d7a8277cf985735b959c73eb87391944e795b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602901"
---

### <a name="install-the-sdk"></a><span data-ttu-id="2d792-101">Installare l'SDK</span><span class="sxs-lookup"><span data-stu-id="2d792-101">Install the SDK</span></span>

<span data-ttu-id="2d792-102">.NET Core SDK consente di sviluppare app con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2d792-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="2d792-103">Se si installa .NET Core SDK, non è necessario installare il runtime corrispondente.</span><span class="sxs-lookup"><span data-stu-id="2d792-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="2d792-104">Per installare .NET Core SDK, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d792-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="2d792-105">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto dotnet-SDK-2,1**, vedere la sezione [risoluzione dei problemi di apt](#apt-troubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="2d792-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-2.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="2d792-106">Installare il runtime</span><span class="sxs-lookup"><span data-stu-id="2d792-106">Install the runtime</span></span>

<span data-ttu-id="2d792-107">Il runtime di .NET Core consente di eseguire app eseguite con .NET Core che non includevano il Runtime.</span><span class="sxs-lookup"><span data-stu-id="2d792-107">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="2d792-108">I comandi seguenti consentono di installare il runtime di ASP.NET Core, che è il runtime più compatibile per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2d792-108">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="2d792-109">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2d792-109">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="2d792-110">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto aspnetcore-Runtime-2,1**, vedere la sezione [risoluzione dei problemi di apt](#apt-troubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="2d792-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-2.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="2d792-111">In alternativa al runtime di ASP.NET Core, è possibile installare il runtime di .NET Core che non include il supporto ASP.NET Core: sostituire `aspnetcore-runtime-2.1` nel comando precedente con `dotnet-runtime-2.1` .</span><span class="sxs-lookup"><span data-stu-id="2d792-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the command above with `dotnet-runtime-2.1`.</span></span>

```bash
sudo apt-get install -y dotnet-runtime-2.1
```

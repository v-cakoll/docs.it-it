---
ms.openlocfilehash: db89539982c1afe0df374027d54826f3265f0fee
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84603013"
---

### <a name="install-the-sdk"></a><span data-ttu-id="175a4-101">Installare l'SDK</span><span class="sxs-lookup"><span data-stu-id="175a4-101">Install the SDK</span></span>

<span data-ttu-id="175a4-102">Il .NET Core SDK consente di sviluppare app con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="175a4-102">The .NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="175a4-103">Per installare il .NET Core SDK, eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="175a4-103">To install the .NET Core SDK, run the following commands.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

### <a name="install-the-runtime"></a><span data-ttu-id="175a4-104">Installare il runtime</span><span class="sxs-lookup"><span data-stu-id="175a4-104">Install the runtime</span></span>

<span data-ttu-id="175a4-105">Il runtime di .NET Core consente di eseguire app eseguite con .NET Core che non includevano il Runtime.</span><span class="sxs-lookup"><span data-stu-id="175a4-105">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="175a4-106">I comandi seguenti consentono di installare il runtime di ASP.NET Core, che è il runtime più compatibile per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="175a4-106">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="175a4-107">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="175a4-107">In your terminal, run the following commands.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

<span data-ttu-id="175a4-108">In alternativa al runtime di ASP.NET Core, è possibile installare il runtime di .NET Core che non include il supporto ASP.NET Core: sostituire `aspnetcore-runtime-2.1` nel comando precedente con `dotnet-runtime-3.1` .</span><span class="sxs-lookup"><span data-stu-id="175a4-108">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the command above with `dotnet-runtime-3.1`.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

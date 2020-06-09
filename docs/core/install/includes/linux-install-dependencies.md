---
ms.openlocfilehash: b371525c9f4e57c6a09e5bb9232884e5c5e707e0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84603006"
---

<span data-ttu-id="baa31-101">Quando si installa con una gestione pacchetti, queste librerie vengono installate.</span><span class="sxs-lookup"><span data-stu-id="baa31-101">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="baa31-102">Tuttavia, se si installa manualmente .NET Core o si pubblica un'app autonoma, è necessario assicurarsi che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="baa31-102">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="baa31-103">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="baa31-103">lttng-ust</span></span>
- <span data-ttu-id="baa31-104">libcurl</span><span class="sxs-lookup"><span data-stu-id="baa31-104">libcurl</span></span>
- <span data-ttu-id="baa31-105">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="baa31-105">openssl-libs</span></span>
- <span data-ttu-id="baa31-106">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="baa31-106">krb5-libs</span></span>
- <span data-ttu-id="baa31-107">libicu</span><span class="sxs-lookup"><span data-stu-id="baa31-107">libicu</span></span>
- <span data-ttu-id="baa31-108">zlib</span><span class="sxs-lookup"><span data-stu-id="baa31-108">zlib</span></span>
- <span data-ttu-id="baa31-109">libunwind</span><span class="sxs-lookup"><span data-stu-id="baa31-109">libunwind</span></span>
- <span data-ttu-id="baa31-110">libuuid</span><span class="sxs-lookup"><span data-stu-id="baa31-110">libuuid</span></span>

<span data-ttu-id="baa31-111">Se la versione OpenSSL dell'ambiente di runtime di destinazione è 1,1 o successiva, è necessario installare **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="baa31-111">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="baa31-112">Per altre informazioni sulle dipendenze, vedere [app Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)autosufficienti.</span><span class="sxs-lookup"><span data-stu-id="baa31-112">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="baa31-113">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="baa31-113">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="baa31-114">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="baa31-114">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="baa31-115">È possibile installare una versione recente di *libgdiplus* aggiungendo il repository mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="baa31-115">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="baa31-116">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="baa31-116">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

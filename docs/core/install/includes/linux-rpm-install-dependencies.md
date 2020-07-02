---
ms.openlocfilehash: 3d8179c5c0e84f8ff1197cce7790c80a5f5a4f6d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619449"
---

<span data-ttu-id="83abf-101">Quando si installa con una gestione pacchetti, queste librerie vengono installate.</span><span class="sxs-lookup"><span data-stu-id="83abf-101">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="83abf-102">Tuttavia, se si installa manualmente .NET Core o si pubblica un'app autonoma, è necessario assicurarsi che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="83abf-102">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="83abf-103">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="83abf-103">krb5-libs</span></span>
- <span data-ttu-id="83abf-104">libicu</span><span class="sxs-lookup"><span data-stu-id="83abf-104">libicu</span></span>
- <span data-ttu-id="83abf-105">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="83abf-105">openssl-libs</span></span>

<span data-ttu-id="83abf-106">Se la versione OpenSSL dell'ambiente di runtime di destinazione è 1,1 o successiva, è necessario installare **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="83abf-106">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="83abf-107">Per altre informazioni sulle dipendenze, vedere [app Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)autosufficienti.</span><span class="sxs-lookup"><span data-stu-id="83abf-107">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="83abf-108">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="83abf-108">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="83abf-109">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="83abf-109">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="83abf-110">È possibile installare una versione recente di *libgdiplus* aggiungendo il repository mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="83abf-110">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="83abf-111">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="83abf-111">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

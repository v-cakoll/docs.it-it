---
ms.openlocfilehash: 3eab49acd3eaa5b6d5802af5f4e6f0fe2699ee97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937046"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="48b58-101">Opzione di compatibilità UseLegacyImages non supportata</span><span class="sxs-lookup"><span data-stu-id="48b58-101">UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="48b58-102">L'opzione `Switch.System.Windows.Forms.UseLegacyImages` di compatibilità, introdotta in .NET Framework 4.8, non è supportata in Windows Form in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="48b58-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="48b58-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="48b58-103">Change description</span></span>

<span data-ttu-id="48b58-104">A partire da .NET Framework `Switch.System.Windows.Forms.UseLegacyImages` 4.8.</span><span class="sxs-lookup"><span data-stu-id="48b58-104">Starting with the .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="48b58-105">Se impostato `true`su , l'opzione consente all'utente di ripristinare il ridimensionamento delle immagini legacy su schermi DPI elevati la cui scala è impostata su un valore superiore al 100%.</span><span class="sxs-lookup"><span data-stu-id="48b58-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="48b58-106">Per altre informazioni, vedere Note sulla versione di .NET Framework 4.8 su GitHub.For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span><span class="sxs-lookup"><span data-stu-id="48b58-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="48b58-107">In .NET Core `Switch.System.Windows.Forms.UseLegacyImages` l'opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="48b58-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="48b58-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="48b58-108">Version introduced</span></span>

<span data-ttu-id="48b58-109">3.0 Anteprima 9</span><span class="sxs-lookup"><span data-stu-id="48b58-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="48b58-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="48b58-110">Recommended action</span></span>

<span data-ttu-id="48b58-111">Rimuovere l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="48b58-111">Remove the switch.</span></span> <span data-ttu-id="48b58-112">L'opzione non è supportata e non sono disponibili funzionalità alternative.</span><span class="sxs-lookup"><span data-stu-id="48b58-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="48b58-113">Category</span><span class="sxs-lookup"><span data-stu-id="48b58-113">Category</span></span>

<span data-ttu-id="48b58-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="48b58-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="48b58-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="48b58-115">Affected APIs</span></span>

- <span data-ttu-id="48b58-116">nessuno</span><span class="sxs-lookup"><span data-stu-id="48b58-116">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->

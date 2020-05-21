---
ms.openlocfilehash: c980b0c0be9f4d6a529baa0743dec9ac16ca0d7f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721721"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="b8e27-101">Opzione di compatibilità UseLegacyImages non supportata</span><span class="sxs-lookup"><span data-stu-id="b8e27-101">UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="b8e27-102">L' `Switch.System.Windows.Forms.UseLegacyImages` opzione di compatibilità, introdotta in .NET Framework 4,8, non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="b8e27-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b8e27-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="b8e27-103">Change description</span></span>

<span data-ttu-id="b8e27-104">A partire dalla .NET Framework 4,8, il `Switch.System.Windows.Forms.UseLegacyImages` cambio di compatibilità ha risolto i possibili problemi di scalabilità delle immagini negli scenari ClickOnce negli ambienti con valori DPI elevati.</span><span class="sxs-lookup"><span data-stu-id="b8e27-104">Starting with the .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="b8e27-105">Quando è impostato su `true` , l'opzione consente all'utente di ripristinare il ridimensionamento delle immagini legacy su schermi a DPI elevato la cui scala è impostata su un valore maggiore del 100%.</span><span class="sxs-lookup"><span data-stu-id="b8e27-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="b8e27-106">Per ulteriori informazioni, vedere le [Note sulla versione di .NET Framework 4,8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="b8e27-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="b8e27-107">In .NET Core l' `Switch.System.Windows.Forms.UseLegacyImages` opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="b8e27-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b8e27-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="b8e27-108">Version introduced</span></span>

<span data-ttu-id="b8e27-109">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="b8e27-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b8e27-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="b8e27-110">Recommended action</span></span>

<span data-ttu-id="b8e27-111">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="b8e27-111">Remove the switch.</span></span> <span data-ttu-id="b8e27-112">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="b8e27-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="b8e27-113">Category</span><span class="sxs-lookup"><span data-stu-id="b8e27-113">Category</span></span>

<span data-ttu-id="b8e27-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b8e27-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b8e27-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="b8e27-115">Affected APIs</span></span>

- <span data-ttu-id="b8e27-116">Nessuno</span><span class="sxs-lookup"><span data-stu-id="b8e27-116">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->

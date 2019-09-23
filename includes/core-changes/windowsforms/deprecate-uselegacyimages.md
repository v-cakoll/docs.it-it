---
ms.openlocfilehash: 07527c247e6ccd53d2a77793946ffc796c3e1cbb
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181847"
---
### <a name="switchsystemwindowsformsuselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="a7d00-101">Opzione di compatibilità switch. System. Windows. Forms. UseLegacyImages non supportata</span><span class="sxs-lookup"><span data-stu-id="a7d00-101">Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="a7d00-102">L' `Switch.System.Windows.Forms.UseLegacyImages` opzione di compatibilità, introdotta in .NET Framework 4,8, non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="a7d00-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a7d00-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="a7d00-103">Change description</span></span>

<span data-ttu-id="a7d00-104">A partire dalla .NET Framework 4,8, il `Switch.System.Windows.Forms.UseLegacyImages` cambio di compatibilità ha risolto i possibili problemi di scalabilità delle immagini negli scenari ClickOnce negli ambienti con valori DPI elevati.</span><span class="sxs-lookup"><span data-stu-id="a7d00-104">Starting with the .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="a7d00-105">Quando è impostato `true`su, l'opzione consente all'utente di ripristinare il ridimensionamento delle immagini legacy su schermi a DPI elevato la cui scala è impostata su un valore maggiore del 100%.</span><span class="sxs-lookup"><span data-stu-id="a7d00-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="a7d00-106">Per ulteriori informazioni, vedere le [Note sulla versione di .NET Framework 4,8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="a7d00-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="a7d00-107">In .NET Core l' `Switch.System.Windows.Forms.UseLegacyImages` opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="a7d00-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a7d00-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="a7d00-108">Version introduced</span></span>

<span data-ttu-id="a7d00-109">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="a7d00-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a7d00-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="a7d00-110">Recommended action</span></span>

<span data-ttu-id="a7d00-111">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="a7d00-111">Remove the switch.</span></span> <span data-ttu-id="a7d00-112">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="a7d00-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="a7d00-113">Category</span><span class="sxs-lookup"><span data-stu-id="a7d00-113">Category</span></span>

<span data-ttu-id="a7d00-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="a7d00-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a7d00-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="a7d00-115">Affected APIs</span></span>

- <span data-ttu-id="a7d00-116">nessuno</span><span class="sxs-lookup"><span data-stu-id="a7d00-116">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->

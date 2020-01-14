---
ms.openlocfilehash: 3eab49acd3eaa5b6d5802af5f4e6f0fe2699ee97
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937046"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="76886-101">Opzione di compatibilità UseLegacyImages non supportata</span><span class="sxs-lookup"><span data-stu-id="76886-101">UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="76886-102">L'opzione di compatibilità `Switch.System.Windows.Forms.UseLegacyImages`, introdotta in .NET Framework 4,8, non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="76886-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="76886-103">Descrizione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="76886-103">Change description</span></span>

<span data-ttu-id="76886-104">A partire dalla .NET Framework 4,8, l'opzione di compatibilità `Switch.System.Windows.Forms.UseLegacyImages` ha risolto i possibili problemi di scalabilità delle immagini negli scenari ClickOnce negli ambienti ad alta risoluzione.</span><span class="sxs-lookup"><span data-stu-id="76886-104">Starting with the .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="76886-105">Quando è impostato su `true`, l'opzione consente all'utente di ripristinare il ridimensionamento delle immagini legacy su schermi a DPI elevato la cui scala è impostata su un valore maggiore del 100%.</span><span class="sxs-lookup"><span data-stu-id="76886-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="76886-106">Per ulteriori informazioni, vedere le [Note sulla versione di .NET Framework 4,8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="76886-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="76886-107">In .NET Core, l'opzione `Switch.System.Windows.Forms.UseLegacyImages` non è supportata.</span><span class="sxs-lookup"><span data-stu-id="76886-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="76886-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="76886-108">Version introduced</span></span>

<span data-ttu-id="76886-109">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="76886-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="76886-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="76886-110">Recommended action</span></span>

<span data-ttu-id="76886-111">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="76886-111">Remove the switch.</span></span> <span data-ttu-id="76886-112">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="76886-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="76886-113">Categoria</span><span class="sxs-lookup"><span data-stu-id="76886-113">Category</span></span>

<span data-ttu-id="76886-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="76886-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="76886-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="76886-115">Affected APIs</span></span>

- <span data-ttu-id="76886-116">nessuna</span><span class="sxs-lookup"><span data-stu-id="76886-116">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->

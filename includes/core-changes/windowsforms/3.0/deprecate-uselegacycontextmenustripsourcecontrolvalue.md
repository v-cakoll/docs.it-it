---
ms.openlocfilehash: 3ada05a13ec7acde1d8374ed733d0d51cdfb408c
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721653"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a><span data-ttu-id="64e0a-101">Opzione di compatibilità UseLegacyContextMenuStripSourceControlValue non supportata</span><span class="sxs-lookup"><span data-stu-id="64e0a-101">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>

<span data-ttu-id="64e0a-102">L' `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` opzione di compatibilità, introdotta in .NET Framework 4.7.2, non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="64e0a-102">The `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch, which was introduced in .NET Framework 4.7.2, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="64e0a-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="64e0a-103">Change description</span></span>

<span data-ttu-id="64e0a-104">A partire da .NET Framework 4.7.2, l' `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` opzione di compatibilità consente allo sviluppatore di rifiutare esplicitamente il nuovo comportamento della <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> proprietà, che ora restituisce un riferimento al controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="64e0a-104">Starting with the .NET Framework 4.7.2, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch allows the developer to opt out of the new behavior of the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property, which now returns a reference to the source control.</span></span> <span data-ttu-id="64e0a-105">Il comportamento precedente della proprietà era restituire `null` .</span><span class="sxs-lookup"><span data-stu-id="64e0a-105">The previous behavior of the property was to return `null`.</span></span> <span data-ttu-id="64e0a-106">Per ulteriori informazioni, vedere [ \< AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="64e0a-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="64e0a-107">In .NET Core l' `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="64e0a-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="64e0a-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="64e0a-108">Version introduced</span></span>

<span data-ttu-id="64e0a-109">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="64e0a-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="64e0a-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="64e0a-110">Recommended action</span></span>

<span data-ttu-id="64e0a-111">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="64e0a-111">Remove the switch.</span></span> <span data-ttu-id="64e0a-112">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="64e0a-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="64e0a-113">Category</span><span class="sxs-lookup"><span data-stu-id="64e0a-113">Category</span></span>

<span data-ttu-id="64e0a-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64e0a-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="64e0a-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="64e0a-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->

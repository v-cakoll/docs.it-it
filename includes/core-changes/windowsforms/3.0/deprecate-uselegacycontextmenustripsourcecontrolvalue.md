---
ms.openlocfilehash: 5aca2b8b3ca6572194692888eae3c5614245b481
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75936985"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a><span data-ttu-id="880ab-101">Opzione di compatibilità UseLegacyContextMenuStripSourceControlValue non supportata</span><span class="sxs-lookup"><span data-stu-id="880ab-101">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>

<span data-ttu-id="880ab-102">L'opzione `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` di compatibilità, introdotta in .NET Framework 4.7.2, non è supportata in Windows Form in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="880ab-102">The `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch, which was introduced in .NET Framework 4.7.2, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="880ab-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="880ab-103">Change description</span></span>

<span data-ttu-id="880ab-104">A partire da .NET Framework 4.7.2, l'opzione `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` di compatibilità <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> consente allo sviluppatore di rifiutare esplicitamente il nuovo comportamento della proprietà, che ora restituisce un riferimento al controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="880ab-104">Starting with the .NET Framework 4.7.2, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch allows the developer to opt out of the new behavior of the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property, which now returns a reference to the source control.</span></span> <span data-ttu-id="880ab-105">Il comportamento precedente della proprietà `null`consisteva nel restituire .</span><span class="sxs-lookup"><span data-stu-id="880ab-105">The previous behavior of the property was to return `null`.</span></span> <span data-ttu-id="880ab-106">Per ulteriori informazioni, vedere [ \<Elemento> AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="880ab-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="880ab-107">In .NET Core `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` l'opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="880ab-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="880ab-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="880ab-108">Version introduced</span></span>

<span data-ttu-id="880ab-109">3.0 Anteprima 9</span><span class="sxs-lookup"><span data-stu-id="880ab-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="880ab-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="880ab-110">Recommended action</span></span>

<span data-ttu-id="880ab-111">Rimuovere l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="880ab-111">Remove the switch.</span></span> <span data-ttu-id="880ab-112">L'opzione non è supportata e non sono disponibili funzionalità alternative.</span><span class="sxs-lookup"><span data-stu-id="880ab-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="880ab-113">Category</span><span class="sxs-lookup"><span data-stu-id="880ab-113">Category</span></span>

<span data-ttu-id="880ab-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="880ab-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="880ab-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="880ab-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->

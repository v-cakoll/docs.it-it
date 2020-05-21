---
ms.openlocfilehash: dd850e83540ffed4dc95b00f807f49b0dd3725e9
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720998"
---
### <a name="domainupdownuselegacyscrolling-compatibility-switch-not-supported"></a><span data-ttu-id="bc3f1-101">Opzione di compatibilità DomainUpDown. UseLegacyScrolling non supportata</span><span class="sxs-lookup"><span data-stu-id="bc3f1-101">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>

<span data-ttu-id="bc3f1-102">L' `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` opzione di compatibilità, introdotta in .NET Framework 4.7.1, non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="bc3f1-102">The `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="bc3f1-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="bc3f1-103">Change description</span></span>

<span data-ttu-id="bc3f1-104">A partire da .NET Framework 4.7.1, l' `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` opzione di compatibilità consente agli sviluppatori di rifiutare esplicitamente <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> le <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> azioni e indipendenti.</span><span class="sxs-lookup"><span data-stu-id="bc3f1-104">Starting with the .NET Framework 4.7.1, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch allowed developers to opt-out of independent <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> actions.</span></span> <span data-ttu-id="bc3f1-105">Il Commuter ha ripristinato il comportamento legacy, in cui <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> viene ignorato se il testo del contesto è presente e lo sviluppatore deve usare <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> Action sul controllo prima dell' <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> azione.</span><span class="sxs-lookup"><span data-stu-id="bc3f1-105">The switch restored the legacy behavior, in which the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> is ignored if context text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="bc3f1-106">Per ulteriori informazioni, vedere [ \< AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="bc3f1-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="bc3f1-107">In .NET Core l' `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="bc3f1-107">In .NET Core, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bc3f1-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bc3f1-108">Version introduced</span></span>

<span data-ttu-id="bc3f1-109">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="bc3f1-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bc3f1-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="bc3f1-110">Recommended action</span></span>

<span data-ttu-id="bc3f1-111">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="bc3f1-111">Remove the switch.</span></span> <span data-ttu-id="bc3f1-112">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="bc3f1-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="bc3f1-113">Category</span><span class="sxs-lookup"><span data-stu-id="bc3f1-113">Category</span></span>

<span data-ttu-id="bc3f1-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc3f1-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bc3f1-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="bc3f1-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->

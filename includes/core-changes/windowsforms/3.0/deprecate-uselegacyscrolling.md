---
ms.openlocfilehash: 80fc75d0736e2ae17699073a025e79b52b340613
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937012"
---
### <a name="domainupdownuselegacyscrolling-compatibility-switch-not-supported"></a><span data-ttu-id="000fb-101">Opzione di compatibilità DomainUpDown.UseLegacyScrolling non supportata</span><span class="sxs-lookup"><span data-stu-id="000fb-101">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>

<span data-ttu-id="000fb-102">L'opzione `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` di compatibilità, introdotta in .NET Framework 4.7.1, non è supportata in Windows Form in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="000fb-102">The `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="000fb-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="000fb-103">Change description</span></span>

<span data-ttu-id="000fb-104">A partire da .NET Framework 4.7.1, l'opzione `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` di <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> compatibilità ha consentito agli sviluppatori di rifiutare esplicitamente l'indipendenza e le azioni.</span><span class="sxs-lookup"><span data-stu-id="000fb-104">Starting with the .NET Framework 4.7.1, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch allowed developers to opt-out of independent <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> actions.</span></span> <span data-ttu-id="000fb-105">L'opzione ha ripristinato il <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> comportamento legacy, in cui viene ignorato <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> se è presente <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> il testo del contesto e lo sviluppatore deve usare l'azione sul controllo prima dell'azione.</span><span class="sxs-lookup"><span data-stu-id="000fb-105">The switch restored the legacy behavior, in which the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> is ignored if context text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="000fb-106">Per ulteriori informazioni, vedere [ \<Elemento> AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="000fb-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="000fb-107">In .NET Core `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` l'opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="000fb-107">In .NET Core, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="000fb-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="000fb-108">Version introduced</span></span>

<span data-ttu-id="000fb-109">3.0 Anteprima 9</span><span class="sxs-lookup"><span data-stu-id="000fb-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="000fb-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="000fb-110">Recommended action</span></span>

<span data-ttu-id="000fb-111">Rimuovere l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="000fb-111">Remove the switch.</span></span> <span data-ttu-id="000fb-112">L'opzione non è supportata e non sono disponibili funzionalità alternative.</span><span class="sxs-lookup"><span data-stu-id="000fb-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="000fb-113">Category</span><span class="sxs-lookup"><span data-stu-id="000fb-113">Category</span></span>

<span data-ttu-id="000fb-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="000fb-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="000fb-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="000fb-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->

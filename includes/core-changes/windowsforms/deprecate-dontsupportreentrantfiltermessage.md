---
ms.openlocfilehash: cb72e1b92172b8989ce99b47181c13561a7ccd76
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181797"
---
### <a name="switchsystemwindowsformsdontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a><span data-ttu-id="86079-101">Opzione di compatibilità switch. System. Windows. Forms. DontSupportReentrantFilterMessage non supportata</span><span class="sxs-lookup"><span data-stu-id="86079-101">Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported</span></span>

<span data-ttu-id="86079-102">L' `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` opzione di compatibilità, introdotta in .NET Framework 4.6.1, non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="86079-102">The `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="86079-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="86079-103">Change description</span></span>

<span data-ttu-id="86079-104">A partire da .NET Framework 4.6.1, l' `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` opzione di compatibilità risolve <xref:System.IndexOutOfRangeException> le possibili eccezioni <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> quando il messaggio viene chiamato con <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> un'implementazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="86079-104">Starting with the .NET Framework 4.6.1, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch addresses possible <xref:System.IndexOutOfRangeException> exceptions when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> message is called with a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="86079-105">Per altre informazioni, vedere [Mitigazione: Implementazioni personalizzate di IMessageFilter.](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)PreFilterMessage.</span><span class="sxs-lookup"><span data-stu-id="86079-105">For more information, see [Mitigation: Custom IMessageFilter.PreFilterMessage Implementations](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span></span>

<span data-ttu-id="86079-106">In .NET Core l' `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="86079-106">In .NET Core, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="86079-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="86079-107">Version introduced</span></span>

<span data-ttu-id="86079-108">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="86079-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="86079-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="86079-109">Recommended action</span></span>

<span data-ttu-id="86079-110">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="86079-110">Remove the switch.</span></span> <span data-ttu-id="86079-111">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="86079-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="86079-112">Category</span><span class="sxs-lookup"><span data-stu-id="86079-112">Category</span></span>

<span data-ttu-id="86079-113">Windows Form</span><span class="sxs-lookup"><span data-stu-id="86079-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="86079-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="86079-114">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->

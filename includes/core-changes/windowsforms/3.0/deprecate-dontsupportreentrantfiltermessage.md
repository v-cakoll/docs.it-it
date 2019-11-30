---
ms.openlocfilehash: cb72e1b92172b8989ce99b47181c13561a7ccd76
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644005"
---
### <a name="switchsystemwindowsformsdontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a><span data-ttu-id="46b75-101">Opzione di compatibilità switch. System. Windows. Forms. DontSupportReentrantFilterMessage non supportata</span><span class="sxs-lookup"><span data-stu-id="46b75-101">Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported</span></span>

<span data-ttu-id="46b75-102">L'opzione di compatibilità `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`, introdotta in .NET Framework 4.6.1, non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="46b75-102">The `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="46b75-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="46b75-103">Change description</span></span>

<span data-ttu-id="46b75-104">A partire da .NET Framework 4.6.1, l'opzione di compatibilità `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` risolve possibili <xref:System.IndexOutOfRangeException> eccezioni quando viene chiamato il messaggio <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> con un'implementazione di <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> personalizzata.</span><span class="sxs-lookup"><span data-stu-id="46b75-104">Starting with the .NET Framework 4.6.1, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch addresses possible <xref:System.IndexOutOfRangeException> exceptions when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> message is called with a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="46b75-105">Per altre informazioni, vedere [Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span><span class="sxs-lookup"><span data-stu-id="46b75-105">For more information, see [Mitigation: Custom IMessageFilter.PreFilterMessage Implementations](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span></span>

<span data-ttu-id="46b75-106">In .NET Core, l'opzione `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` non è supportata.</span><span class="sxs-lookup"><span data-stu-id="46b75-106">In .NET Core, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="46b75-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="46b75-107">Version introduced</span></span>

<span data-ttu-id="46b75-108">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="46b75-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="46b75-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="46b75-109">Recommended action</span></span>

<span data-ttu-id="46b75-110">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="46b75-110">Remove the switch.</span></span> <span data-ttu-id="46b75-111">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="46b75-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="46b75-112">Category</span><span class="sxs-lookup"><span data-stu-id="46b75-112">Category</span></span>

<span data-ttu-id="46b75-113">Windows Form</span><span class="sxs-lookup"><span data-stu-id="46b75-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="46b75-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="46b75-114">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->

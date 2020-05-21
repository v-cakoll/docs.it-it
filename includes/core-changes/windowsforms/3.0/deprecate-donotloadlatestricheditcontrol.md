---
ms.openlocfilehash: cb8c0532bb2bcfbcd619cd382f3d236b431c3480
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721040"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a><span data-ttu-id="dd840-101">Opzione di compatibilità DoNotLoadLatestRichEditControl non supportata</span><span class="sxs-lookup"><span data-stu-id="dd840-101">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>

<span data-ttu-id="dd840-102">L' `Switch.System.Windows.Forms.UseLegacyImages` opzione di compatibilità, introdotta in .NET Framework 4.7.1, non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="dd840-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="dd840-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="dd840-103">Change description</span></span>

<span data-ttu-id="dd840-104">Nel .NET Framework 4.6.2 e nelle versioni precedenti, il <xref:System.Windows.Forms.RichTextBox> controllo creerà un'istanza del controllo RichEdit Win32 v 3.0 e per le applicazioni destinate .NET Framework 4.7.1, il <xref:System.Windows.Forms.RichTextBox> controllo creerà un'istanza di RichEdit v 4.1 (in *Msftedit. dll*).</span><span class="sxs-lookup"><span data-stu-id="dd840-104">In the .NET Framework 4.6.2 and previous versions, the <xref:System.Windows.Forms.RichTextBox> control would instantiate the Win32 RichEdit control v3.0, and for applications that target .NET Framework 4.7.1, the  <xref:System.Windows.Forms.RichTextBox> control would instantiate RichEdit v4.1 (in *msftedit.dll*).</span></span> <span data-ttu-id="dd840-105">L' `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` opzione di compatibilità è stata introdotta per consentire alle applicazioni destinate .NET Framework 4.7.1 e versioni successive di rifiutare esplicitamente il nuovo controllo RichEdit v 4.1 e usare invece il vecchio controllo RichEdit V3.</span><span class="sxs-lookup"><span data-stu-id="dd840-105">The `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` compatibility switch was introduced to allow applications that target .NET Framework 4.7.1 and later versions to opt-out of the new RichEdit v4.1 control and use the old RichEdit v3 control instead.</span></span>

<span data-ttu-id="dd840-106">In .NET Core l' `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="dd840-106">In .NET Core, the `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` switch is not supported.</span></span> <span data-ttu-id="dd840-107">Sono supportate solo le nuove versioni del <xref:System.Windows.Forms.RichTextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="dd840-107">Only new versions of the  <xref:System.Windows.Forms.RichTextBox> control are supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="dd840-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="dd840-108">Version introduced</span></span>

<span data-ttu-id="dd840-109">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="dd840-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="dd840-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="dd840-110">Recommended action</span></span>

<span data-ttu-id="dd840-111">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="dd840-111">Remove the switch.</span></span> <span data-ttu-id="dd840-112">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="dd840-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="dd840-113">Category</span><span class="sxs-lookup"><span data-stu-id="dd840-113">Category</span></span>

<span data-ttu-id="dd840-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd840-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dd840-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="dd840-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

#### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->

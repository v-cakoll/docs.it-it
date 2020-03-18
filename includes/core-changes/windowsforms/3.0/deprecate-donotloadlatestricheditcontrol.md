---
ms.openlocfilehash: 3f0e8fb4d0d727b40cff5de7cfdc7529bf32dac4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937002"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a><span data-ttu-id="d2036-101">Opzione di compatibilità DoNotLoadLatestRichEditControl non supportata</span><span class="sxs-lookup"><span data-stu-id="d2036-101">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>

<span data-ttu-id="d2036-102">L'opzione `Switch.System.Windows.Forms.UseLegacyImages` di compatibilità, introdotta in .NET Framework 4.7.1, non è supportata in Windows Form in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d2036-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d2036-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="d2036-103">Change description</span></span>

<span data-ttu-id="d2036-104">In .NET Framework 4.6.2 e <xref:System.Windows.Forms.RichTextBox> versioni precedenti, il controllo crea un'istanza del controllo Win32 RichEdit v3.0 <xref:System.Windows.Forms.RichTextBox> e per le applicazioni destinate a .NET Framework 4.7.1, il controllo crea un'istanza di RichEdit v4.1 (in *msftedit.dll*).</span><span class="sxs-lookup"><span data-stu-id="d2036-104">In the .NET Framework 4.6.2 and previous versions, the <xref:System.Windows.Forms.RichTextBox> control would instantiate the Win32 RichEdit control v3.0, and for applications that target .NET Framework 4.7.1, the  <xref:System.Windows.Forms.RichTextBox> control would instantiate RichEdit v4.1 (in *msftedit.dll*).</span></span> <span data-ttu-id="d2036-105">L'opzione `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` di compatibilità è stata introdotta per consentire alle applicazioni destinate a .NET Framework 4.7.1 e versioni successive di rifiutare esplicitamente il nuovo controllo RichEdit v4.1 e di utilizzare invece il controllo RichEdit v3 precedente.</span><span class="sxs-lookup"><span data-stu-id="d2036-105">The `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` compatibility switch was introduced to allow applications that target .NET Framework 4.7.1 and later versions to opt-out of the new RichEdit v4.1 control and use the old RichEdit v3 control instead.</span></span>

<span data-ttu-id="d2036-106">In .NET Core `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` l'opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="d2036-106">In .NET Core, the `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` switch is not supported.</span></span> <span data-ttu-id="d2036-107">Sono supportate <xref:System.Windows.Forms.RichTextBox> solo le nuove versioni del controllo.</span><span class="sxs-lookup"><span data-stu-id="d2036-107">Only new versions of the  <xref:System.Windows.Forms.RichTextBox> control are supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d2036-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="d2036-108">Version introduced</span></span>

<span data-ttu-id="d2036-109">3.0 Anteprima 9</span><span class="sxs-lookup"><span data-stu-id="d2036-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d2036-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="d2036-110">Recommended action</span></span>

<span data-ttu-id="d2036-111">Rimuovere l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="d2036-111">Remove the switch.</span></span> <span data-ttu-id="d2036-112">L'opzione non è supportata e non sono disponibili funzionalità alternative.</span><span class="sxs-lookup"><span data-stu-id="d2036-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="d2036-113">Category</span><span class="sxs-lookup"><span data-stu-id="d2036-113">Category</span></span>

<span data-ttu-id="d2036-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="d2036-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d2036-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="d2036-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->

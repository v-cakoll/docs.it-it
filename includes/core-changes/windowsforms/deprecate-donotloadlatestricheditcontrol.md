---
ms.openlocfilehash: 265fc5bea97bf85bcb9cc8111f915e14297d9957
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181729"
---
### <a name="switchsystemwindowsformsdonotloadlatestricheditcontrol-compatibility-switch-not-supported"></a><span data-ttu-id="636e7-101">Opzione di compatibilità switch. System. Windows. Forms. DoNotLoadLatestRichEditControl non supportata</span><span class="sxs-lookup"><span data-stu-id="636e7-101">Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>

<span data-ttu-id="636e7-102">L' `Switch.System.Windows.Forms.UseLegacyImages` opzione di compatibilità, introdotta in .NET Framework 4.7.1, non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="636e7-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="636e7-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="636e7-103">Change description</span></span>

<span data-ttu-id="636e7-104">Nel .NET Framework 4.6.2 e nelle versioni precedenti, il <xref:System.Windows.Forms.RichTextBox> controllo creerà un'istanza del controllo RichEdit Win32 v 3.0 e per le applicazioni destinate .NET Framework 4.7.1 <xref:System.Windows.Forms.RichTextBox> , il controllo creerà un'istanza di RichEdit v 4.1 (in  *Msftedit. dll*).</span><span class="sxs-lookup"><span data-stu-id="636e7-104">In the .NET Framework 4.6.2 and previous versions, the <xref:System.Windows.Forms.RichTextBox> control would instantiate the Win32 RichEdit control v3.0, and for applications that target .NET Framework 4.7.1, the  <xref:System.Windows.Forms.RichTextBox> control would instantiate RichEdit v4.1 (in *msftedit.dll*).</span></span> <span data-ttu-id="636e7-105">L' `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` opzione di compatibilità è stata introdotta per consentire alle applicazioni destinate .NET Framework 4.7.1 e versioni successive di rifiutare esplicitamente il nuovo controllo RichEdit v 4.1 e usare invece il vecchio controllo RichEdit V3.</span><span class="sxs-lookup"><span data-stu-id="636e7-105">The `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` compatibility switch was introduced to allow applications that target .NET Framework 4.7.1 and later versions to opt-out of the new RichEdit v4.1 control and use the old RichEdit v3 control instead.</span></span>

<span data-ttu-id="636e7-106">In .NET Core l' `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="636e7-106">In .NET Core, the `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` switch is not supported.</span></span> <span data-ttu-id="636e7-107">Sono supportate solo le <xref:System.Windows.Forms.RichTextBox> nuove versioni del controllo.</span><span class="sxs-lookup"><span data-stu-id="636e7-107">Only new versions of the  <xref:System.Windows.Forms.RichTextBox> control are supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="636e7-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="636e7-108">Version introduced</span></span>

<span data-ttu-id="636e7-109">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="636e7-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="636e7-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="636e7-110">Recommended action</span></span>

<span data-ttu-id="636e7-111">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="636e7-111">Remove the switch.</span></span> <span data-ttu-id="636e7-112">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="636e7-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="636e7-113">Category</span><span class="sxs-lookup"><span data-stu-id="636e7-113">Category</span></span>

<span data-ttu-id="636e7-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="636e7-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="636e7-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="636e7-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->

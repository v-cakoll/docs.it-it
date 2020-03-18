---
ms.openlocfilehash: 9631e64bb403a3fe7b1b91e8ac592b57ce8068d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937101"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a><span data-ttu-id="298ee-101">L'opzione di compatibilità DoNotSupportSelectAllShortcutInMultilineTextBox non è supportata</span><span class="sxs-lookup"><span data-stu-id="298ee-101">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>

<span data-ttu-id="298ee-102">L'opzione `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` di compatibilità, introdotta in .NET Framework 4.6.1, non è supportata in Windows Form in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="298ee-102">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="298ee-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="298ee-103">Change description</span></span>

<span data-ttu-id="298ee-104">A partire da .NET Framework 4.6.1, selezionando <xref:System.Windows.Forms.TextBox> il tasto di scelta rapida <kbd>Ctrl</kbd> + <kbd>A</kbd> in un controllo selezionato tutto il testo.</span><span class="sxs-lookup"><span data-stu-id="298ee-104">Starting with .NET Framework 4.6.1, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key in a <xref:System.Windows.Forms.TextBox> control selected all text.</span></span> <span data-ttu-id="298ee-105">In .NET Framework 4.6 e versioni precedenti, la selezione del tasto di scelta rapida <kbd>Ctrl</kbd> + <kbd>A</kbd> non è riuscita a selezionare tutto il testo se la casella [di testo.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) e <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> le proprietà sono state entrambe impostate `true`su .</span><span class="sxs-lookup"><span data-stu-id="298ee-105">In .NET Framework 4.6 and previous versions, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key failed to select all text if the [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) and <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> properties were both set to `true`.</span></span> <span data-ttu-id="298ee-106">L'opzione `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` di compatibilità è stata introdotta in .NET Framework 4.6.1 per mantenere il comportamento originale.</span><span class="sxs-lookup"><span data-stu-id="298ee-106">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch was introduced in .NET Framework 4.6.1 to retain the original behavior.</span></span> <span data-ttu-id="298ee-107">Per ulteriori informazioni, vedere <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="298ee-107">For more information see <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="298ee-108">In .NET Core `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` l'opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="298ee-108">In .NET Core, the `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="298ee-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="298ee-109">Version introduced</span></span>

<span data-ttu-id="298ee-110">3.0 Anteprima 9</span><span class="sxs-lookup"><span data-stu-id="298ee-110">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="298ee-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="298ee-111">Recommended action</span></span>

<span data-ttu-id="298ee-112">Rimuovere l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="298ee-112">Remove the switch.</span></span> <span data-ttu-id="298ee-113">L'opzione non è supportata e non sono disponibili funzionalità alternative.</span><span class="sxs-lookup"><span data-stu-id="298ee-113">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="298ee-114">Category</span><span class="sxs-lookup"><span data-stu-id="298ee-114">Category</span></span>

<span data-ttu-id="298ee-115">Windows Form</span><span class="sxs-lookup"><span data-stu-id="298ee-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="298ee-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="298ee-116">Affected APIs</span></span>

- <span data-ttu-id="298ee-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="298ee-117">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->

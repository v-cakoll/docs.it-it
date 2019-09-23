---
ms.openlocfilehash: a9d0fe3516ade04bc38b804268a9d989f6891d80
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181837"
---
### <a name="switchsystemwindowsformsdonotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a><span data-ttu-id="af580-101">Opzione di compatibilità switch. System. Windows. Forms. DoNotSupportSelectAllShortcutInMultilineTextBox non supportata</span><span class="sxs-lookup"><span data-stu-id="af580-101">Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>

<span data-ttu-id="af580-102">L' `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` opzione di compatibilità, introdotta in .NET Framework 4.6.1, non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="af580-102">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="af580-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="af580-103">Change description</span></span>

<span data-ttu-id="af580-104">A partire da .NET Framework 4.6.1, selezionando il tasto <kbd>CTRL</kbd> + <kbd>un</kbd> tasto <xref:System.Windows.Forms.TextBox> di scelta rapida in un controllo è stato selezionato tutto il testo.</span><span class="sxs-lookup"><span data-stu-id="af580-104">Starting with .NET Framework 4.6.1, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key in a <xref:System.Windows.Forms.TextBox> control selected all text.</span></span> <span data-ttu-id="af580-105">In .NET Framework 4,6 e versioni precedenti, selezionando il tasto <kbd>CTRL</kbd> + <kbd>un</kbd> tasto di scelta rapida non è stato possibile selezionare tutto il <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> testo se [TextBox. ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) e le proprietà sono entrambe impostate su. `true`</span><span class="sxs-lookup"><span data-stu-id="af580-105">In .NET Framework 4.6 and previous versions, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key failed to select all text if the [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) and <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> properties were both set to `true`.</span></span> <span data-ttu-id="af580-106">L' `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` opzione di compatibilità è stata introdotta in .NET Framework 4.6.1 per mantenere il comportamento originale.</span><span class="sxs-lookup"><span data-stu-id="af580-106">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch was introduced in .NET Framework 4.6.1 to retain the original behavior.</span></span> <span data-ttu-id="af580-107">Per altre informazioni, vedere <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="af580-107">For more information see <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="af580-108">In .NET Core l' `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="af580-108">In .NET Core, the `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="af580-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="af580-109">Version introduced</span></span>

<span data-ttu-id="af580-110">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="af580-110">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="af580-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="af580-111">Recommended action</span></span>

<span data-ttu-id="af580-112">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="af580-112">Remove the switch.</span></span> <span data-ttu-id="af580-113">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="af580-113">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="af580-114">Category</span><span class="sxs-lookup"><span data-stu-id="af580-114">Category</span></span>

<span data-ttu-id="af580-115">Windows Form</span><span class="sxs-lookup"><span data-stu-id="af580-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="af580-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="af580-116">Affected APIs</span></span>

- <span data-ttu-id="af580-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="af580-117">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->

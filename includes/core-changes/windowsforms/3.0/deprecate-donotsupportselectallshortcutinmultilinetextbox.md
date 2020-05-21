---
ms.openlocfilehash: bba74f26eafd52b966928835d5003d03af1eabdc
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721062"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a><span data-ttu-id="665b5-101">Opzione di compatibilità DoNotSupportSelectAllShortcutInMultilineTextBox non supportata</span><span class="sxs-lookup"><span data-stu-id="665b5-101">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>

<span data-ttu-id="665b5-102">L' `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` opzione di compatibilità, introdotta in .NET Framework 4.6.1, non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="665b5-102">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="665b5-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="665b5-103">Change description</span></span>

<span data-ttu-id="665b5-104">A partire da .NET Framework 4.6.1, selezionando il tasto <kbd>CTRL</kbd>  +  <kbd>un</kbd> tasto di scelta rapida in un controllo è stato <xref:System.Windows.Forms.TextBox> selezionato tutto il testo.</span><span class="sxs-lookup"><span data-stu-id="665b5-104">Starting with .NET Framework 4.6.1, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key in a <xref:System.Windows.Forms.TextBox> control selected all text.</span></span> <span data-ttu-id="665b5-105">In .NET Framework 4,6 e versioni precedenti, selezionando il tasto <kbd>CTRL</kbd>  +  <kbd>un</kbd> tasto di scelta rapida non è stato possibile selezionare tutto il testo se [TextBox. ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) e le <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> proprietà sono entrambe impostate su `true` .</span><span class="sxs-lookup"><span data-stu-id="665b5-105">In .NET Framework 4.6 and previous versions, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key failed to select all text if the [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) and <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> properties were both set to `true`.</span></span> <span data-ttu-id="665b5-106">L' `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` opzione di compatibilità è stata introdotta in .NET Framework 4.6.1 per mantenere il comportamento originale.</span><span class="sxs-lookup"><span data-stu-id="665b5-106">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch was introduced in .NET Framework 4.6.1 to retain the original behavior.</span></span> <span data-ttu-id="665b5-107">Per ulteriori informazioni, vedere <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="665b5-107">For more information see <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="665b5-108">In .NET Core l' `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="665b5-108">In .NET Core, the `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="665b5-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="665b5-109">Version introduced</span></span>

<span data-ttu-id="665b5-110">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="665b5-110">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="665b5-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="665b5-111">Recommended action</span></span>

<span data-ttu-id="665b5-112">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="665b5-112">Remove the switch.</span></span> <span data-ttu-id="665b5-113">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="665b5-113">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="665b5-114">Category</span><span class="sxs-lookup"><span data-stu-id="665b5-114">Category</span></span>

<span data-ttu-id="665b5-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="665b5-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="665b5-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="665b5-116">Affected APIs</span></span>

- <span data-ttu-id="665b5-117">Nessuno</span><span class="sxs-lookup"><span data-stu-id="665b5-117">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->

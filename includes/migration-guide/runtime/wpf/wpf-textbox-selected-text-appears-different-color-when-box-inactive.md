---
ms.openlocfilehash: 74ce1bbc9a887aee3a33eaf05084e8c2000967c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235755"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="57a38-101">Il testo selezionato nel controllo TextBox WPF viene visualizzato con un colore diverso quando la casella di testo è inattiva</span><span class="sxs-lookup"><span data-stu-id="57a38-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

|   |   |
|---|---|
|<span data-ttu-id="57a38-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="57a38-102">Details</span></span>|<span data-ttu-id="57a38-103">In .NET Framework 4.5, se una casella di testo WPF è inattiva (non ha lo stato attivo), il testo selezionato nella casella verrà visualizzato con un colore diverso rispetto a quando il controllo è attivo.</span><span class="sxs-lookup"><span data-stu-id="57a38-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>|
|<span data-ttu-id="57a38-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="57a38-104">Suggestion</span></span>|<span data-ttu-id="57a38-105">È possibile ripristinare il comportamento precedente di .NET Framework 4.0 impostando la proprietà <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> su <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="57a38-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>|
|<span data-ttu-id="57a38-106">Ambito</span><span class="sxs-lookup"><span data-stu-id="57a38-106">Scope</span></span>|<span data-ttu-id="57a38-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="57a38-107">Edge</span></span>|
|<span data-ttu-id="57a38-108">Versione</span><span class="sxs-lookup"><span data-stu-id="57a38-108">Version</span></span>|<span data-ttu-id="57a38-109">4.5</span><span class="sxs-lookup"><span data-stu-id="57a38-109">4.5</span></span>|
|<span data-ttu-id="57a38-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="57a38-110">Type</span></span>|<span data-ttu-id="57a38-111">Runtime</span><span class="sxs-lookup"><span data-stu-id="57a38-111">Runtime</span></span>|
|<span data-ttu-id="57a38-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="57a38-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|

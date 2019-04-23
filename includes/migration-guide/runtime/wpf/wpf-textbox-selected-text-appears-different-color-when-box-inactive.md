---
ms.openlocfilehash: 74ce1bbc9a887aee3a33eaf05084e8c2000967c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804253"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="c98a7-101">Il testo selezionato nel controllo TextBox WPF viene visualizzato con un colore diverso quando la casella di testo è inattiva</span><span class="sxs-lookup"><span data-stu-id="c98a7-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c98a7-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c98a7-102">Details</span></span>|<span data-ttu-id="c98a7-103">In .NET Framework 4.5, se una casella di testo WPF è inattiva (non ha lo stato attivo), il testo selezionato nella casella verrà visualizzato con un colore diverso rispetto a quando il controllo è attivo.</span><span class="sxs-lookup"><span data-stu-id="c98a7-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>|
|<span data-ttu-id="c98a7-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="c98a7-104">Suggestion</span></span>|<span data-ttu-id="c98a7-105">È possibile ripristinare il comportamento precedente di .NET Framework 4.0 impostando la proprietà <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> su <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="c98a7-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>|
|<span data-ttu-id="c98a7-106">Ambito</span><span class="sxs-lookup"><span data-stu-id="c98a7-106">Scope</span></span>|<span data-ttu-id="c98a7-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c98a7-107">Edge</span></span>|
|<span data-ttu-id="c98a7-108">Versione</span><span class="sxs-lookup"><span data-stu-id="c98a7-108">Version</span></span>|<span data-ttu-id="c98a7-109">4.5</span><span class="sxs-lookup"><span data-stu-id="c98a7-109">4.5</span></span>|
|<span data-ttu-id="c98a7-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="c98a7-110">Type</span></span>|<span data-ttu-id="c98a7-111">Runtime</span><span class="sxs-lookup"><span data-stu-id="c98a7-111">Runtime</span></span>|
|<span data-ttu-id="c98a7-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="c98a7-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|

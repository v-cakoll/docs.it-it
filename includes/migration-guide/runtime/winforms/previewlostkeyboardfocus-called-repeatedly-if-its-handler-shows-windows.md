---
ms.openlocfilehash: 2aa6603e2ed77ffa94fbc6325cd5db50985bda6a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620414"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a><span data-ttu-id="64197-101">PreviewLostKeyboardFocus viene chiamato ripetutamente se il gestore visualizza una finestra di messaggio di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64197-101">PreviewLostKeyboardFocus is called repeatedly if its handler shows a Windows Forms message box</span></span>

#### <a name="details"></a><span data-ttu-id="64197-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="64197-102">Details</span></span>

<span data-ttu-id="64197-103">A partire da .NET Framework 4.5, la chiamata di <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> da un gestore <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> causerà la riattivazione del gestore alla chiusura della finestra di messaggio, con un potenziale ciclo infinito di finestre di messaggio.</span><span class="sxs-lookup"><span data-stu-id="64197-103">Beginning in the .NET Framework 4.5, calling <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> from a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> handler will cause the handler to re-fire when the message box is closed, potentially resulting in an infinite loop of message boxes.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="64197-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="64197-104">Suggestion</span></span>

<span data-ttu-id="64197-105">Esistono due modi per aggirare questo problema:</span><span class="sxs-lookup"><span data-stu-id="64197-105">There are two options to work around this issue:</span></span><ol><li><span data-ttu-id="64197-106">Può essere evitato chiamando <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> invece di <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="64197-106">It may be avoided by calling <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> instead of <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</span></span></li><li><span data-ttu-id="64197-107">Può essere evitato visualizzando la finestra di messaggio da un gestore eventi <xref:System.Windows.UIElement.LostKeyboardFocus>, anziché un gestore eventi <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="64197-107">It may be avoided by showing the message box from a <xref:System.Windows.UIElement.LostKeyboardFocus> event handler (as opposed to a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName> event handler).</span></span></li></ol>

| <span data-ttu-id="64197-108">Nome</span><span class="sxs-lookup"><span data-stu-id="64197-108">Name</span></span>    | <span data-ttu-id="64197-109">Valore</span><span class="sxs-lookup"><span data-stu-id="64197-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="64197-110">Scope</span><span class="sxs-lookup"><span data-stu-id="64197-110">Scope</span></span>   |<span data-ttu-id="64197-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="64197-111">Edge</span></span>|
|<span data-ttu-id="64197-112">Version</span><span class="sxs-lookup"><span data-stu-id="64197-112">Version</span></span>|<span data-ttu-id="64197-113">4.5</span><span class="sxs-lookup"><span data-stu-id="64197-113">4.5</span></span>|
|<span data-ttu-id="64197-114">Type</span><span class="sxs-lookup"><span data-stu-id="64197-114">Type</span></span>|<span data-ttu-id="64197-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="64197-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="64197-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="64197-116">Affected APIs</span></span>

-<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType></li></ul>|

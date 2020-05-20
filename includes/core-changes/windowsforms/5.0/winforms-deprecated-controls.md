---
ms.openlocfilehash: c9720f51e40ada4cd2cf6997ba7006a232893553
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702496"
---
### <a name="removed-status-bar-controls"></a><span data-ttu-id="21117-101">Rimossi controlli barra di stato</span><span class="sxs-lookup"><span data-stu-id="21117-101">Removed status bar controls</span></span>

<span data-ttu-id="21117-102">A partire da .NET 5,0 Preview 1, alcuni Windows Forms controlli non sono più disponibili.</span><span class="sxs-lookup"><span data-stu-id="21117-102">Starting in .NET 5.0 Preview 1, some Windows Forms controls are no longer available.</span></span>

#### <a name="change-description"></a><span data-ttu-id="21117-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="21117-103">Change description</span></span>

<span data-ttu-id="21117-104">A partire da .NET 5,0 Preview 1, alcuni dei controlli Windows Forms correlati alla barra di stato non sono più disponibili.</span><span class="sxs-lookup"><span data-stu-id="21117-104">Starting with .NET 5.0 Preview 1, some of the status bar-related Windows Forms controls are no longer available.</span></span> <span data-ttu-id="21117-105">I controlli di sostituzione con una progettazione e un supporto migliori sono stati introdotti nella .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="21117-105">Replacement controls that have better design and support were introduced in .NET Framework 2.0.</span></span> <span data-ttu-id="21117-106">I controlli deprecati sono stati rimossi in precedenza dalle caselle degli strumenti della finestra di progettazione, ma erano ancora disponibili per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="21117-106">The deprecated controls were previously removed from designer toolboxes but were still available to be used.</span></span> <span data-ttu-id="21117-107">A questo punto sono stati rimossi completamente.</span><span class="sxs-lookup"><span data-stu-id="21117-107">Now, they have been completely removed.</span></span>

<span data-ttu-id="21117-108">I tipi seguenti non sono più disponibili:</span><span class="sxs-lookup"><span data-stu-id="21117-108">The following types are no longer available:</span></span>

* `StatusBar`
* `StatusBarDrawItemEventArgs`
* `StatusBarDrawItemEventHandler`
* `StatusBarPanel`
* `StatusBarPanelAutoSize`
* `StatusBarPanelBorderStyle`
* `StatusBarPanelClickEventArgs`
* `StatusBarPanelClickEventHandler`
* `StatusBarPanelStyle`

#### <a name="version-introduced"></a><span data-ttu-id="21117-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="21117-109">Version introduced</span></span>

<span data-ttu-id="21117-110">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="21117-110">5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="21117-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="21117-111">Recommended action</span></span>

<span data-ttu-id="21117-112">Passare alle API sostitutive per questi controlli e i relativi scenari:</span><span class="sxs-lookup"><span data-stu-id="21117-112">Move to the replacement APIs for these controls and their scenarios:</span></span>

| <span data-ttu-id="21117-113">Controllo precedente (API)</span><span class="sxs-lookup"><span data-stu-id="21117-113">Old Control (API)</span></span> | <span data-ttu-id="21117-114">Sostituzione consigliata</span><span class="sxs-lookup"><span data-stu-id="21117-114">Recommended Replacement</span></span>                          |
|-------------------|--------------------------------------------------|
| <span data-ttu-id="21117-115">StatusBar</span><span class="sxs-lookup"><span data-stu-id="21117-115">StatusBar</span></span>         | <xref:System.Windows.Forms.StatusStrip>          |
| <span data-ttu-id="21117-116">StatusBarPanel</span><span class="sxs-lookup"><span data-stu-id="21117-116">StatusBarPanel</span></span>    | <xref:System.Windows.Forms.ToolStripStatusLabel> |

#### <a name="category"></a><span data-ttu-id="21117-117">Category</span><span class="sxs-lookup"><span data-stu-id="21117-117">Category</span></span>

<span data-ttu-id="21117-118">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="21117-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="21117-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="21117-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.StatusBar?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanel?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelAutoSize?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelBorderStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelStyle?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:System.Windows.Forms.StatusBar`
- `T:System.Windows.Forms.StatusBarDrawItemEventArgs`
- `T:System.Windows.Forms.StatusBarDrawItemEventHandler`
- `T:System.Windows.Forms.StatusBarPanel`
- `T:System.Windows.Forms.StatusBarPanelAutoSize`
- `T:System.Windows.Forms.StatusBarPanelBorderStyle`
- `T:System.Windows.Forms.StatusBarPanelClickEventArgs`
- `T:System.Windows.Forms.StatusBarPanelClickEventHandler`
- `T:System.Windows.Forms.StatusBarPanelStyle` 

-->

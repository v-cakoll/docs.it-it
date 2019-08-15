---
title: 'Procedura: Abilitare la visualizzazione affiancata in un controllo ListView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 8a45a8a484bd373f53585b1b113a51e59b30fca2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040360"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="10971-102">Procedura: Abilitare la visualizzazione affiancata in un controllo ListView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="10971-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="10971-103">La funzionalità di visualizzazione affiancata <xref:System.Windows.Forms.ListView> del controllo consente di fornire un equilibrio visivo tra informazioni grafiche e testuali.</span><span class="sxs-lookup"><span data-stu-id="10971-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="10971-104">Le informazioni testuali visualizzate per un elemento nella visualizzazione affiancata corrisponde alle informazioni della colonna definite per la visualizzazione dettagli.</span><span class="sxs-lookup"><span data-stu-id="10971-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="10971-105">Funzioni di visualizzazione affiancate in combinazione con le funzionalità di raggruppamento o di contrassegno di <xref:System.Windows.Forms.ListView> inserimento nel controllo.</span><span class="sxs-lookup"><span data-stu-id="10971-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>

 <span data-ttu-id="10971-106">La visualizzazione affiancata usa un'icona 32 x 32 e varie righe di testo, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="10971-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>

 <span data-ttu-id="10971-107">![Visualizzazione affiancata in un controllo ListView](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Icone e testo di visualizzazione affiancata")</span><span class="sxs-lookup"><span data-stu-id="10971-107">![Tile View in a ListView Control](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>

 <span data-ttu-id="10971-108">Le proprietà e i metodi della visualizzazione affiancata consentono di specificare i campi di colonna da visualizzare per ogni elemento e di controllare collettivamente le dimensioni e l'aspetto di tutti gli elementi all'interno di una finestra di visualizzazione affiancata.</span><span class="sxs-lookup"><span data-stu-id="10971-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="10971-109">Per maggiore chiarezza, la prima riga di testo in una sezione è sempre il nome dell'elemento; non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="10971-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>

 <span data-ttu-id="10971-110">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.ListView> modulo contenente un controllo.</span><span class="sxs-lookup"><span data-stu-id="10971-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="10971-111">Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="10971-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

> [!NOTE]
> <span data-ttu-id="10971-112">La visualizzazione affiancata è disponibile solo in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="10971-112">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="10971-113">Nei sistemi operativi precedenti, qualsiasi codice correlato alla visualizzazione affiancata non ha alcun effetto e il controllo <xref:System.Windows.Forms.ListView> viene visualizzato nella visualizzazione Icone grandi.</span><span class="sxs-lookup"><span data-stu-id="10971-113">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="10971-114">Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="10971-114">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>

## <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="10971-115">Per impostare la visualizzazione affiancata nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="10971-115">To set tile view in the designer</span></span>

1. <span data-ttu-id="10971-116">In Visual Studio selezionare il <xref:System.Windows.Forms.ListView> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="10971-116">In Visual Studio, select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>

2. <span data-ttu-id="10971-117">Nella finestra **Proprietà** selezionare la <xref:System.Windows.Forms.ListView.View%2A> proprietà e scegliere **riquadro**.</span><span class="sxs-lookup"><span data-stu-id="10971-117">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>

## <a name="see-also"></a><span data-ttu-id="10971-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10971-118">See also</span></span>

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="10971-119">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="10971-119">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)

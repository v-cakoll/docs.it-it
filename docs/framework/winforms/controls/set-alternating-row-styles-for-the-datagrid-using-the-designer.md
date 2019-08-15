---
title: 'Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: 1be746d4cce36344e034692a0e2e8e6a9e9320d5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040432"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="8fa4d-102">Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="8fa4d-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="8fa4d-103">I dati tabulari vengono spesso presentati in un formato di tipo Ledger, in cui le righe alternate hanno colori di sfondo diversi.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-103">Tabular data is often presented in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="8fa4d-104">Questo formato permette agli utenti di individuare più facilmente le celle di ogni riga, soprattutto nelle tabelle estese in larghezza con molte colonne.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>

<span data-ttu-id="8fa4d-105">Con il controllo <xref:System.Windows.Forms.DataGridView>, è possibile specificare informazioni di stile complete per le righe alterne.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="8fa4d-106">È possibile utilizzare le caratteristiche di stile, ad esempio il colore di primo piano e il tipo di carattere, oltre al colore di sfondo, per distinguere le righe alternate.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-106">You can use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span> <span data-ttu-id="8fa4d-107">Per ulteriori informazioni, vedere la pagina relativa agli [stili delle celle nel controllo DataGridView Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-107">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="8fa4d-108">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.DataGridView> modulo contenente un controllo.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="8fa4d-109">Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>


### <a name="define-styles-for-alternating-rows"></a><span data-ttu-id="8fa4d-110">Definire gli stili per le righe alternate</span><span class="sxs-lookup"><span data-stu-id="8fa4d-110">Define styles for alternating rows</span></span>

1. <span data-ttu-id="8fa4d-111">Selezionare il <xref:System.Windows.Forms.DataGridView> controllo nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-111">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>

2. <span data-ttu-id="8fa4d-112">Nella finestra **Proprietà** fare clic sul pulsante con i puntini di sospensione (![il pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-112">In the **Properties** window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> property.</span></span>

3. <span data-ttu-id="8fa4d-113">Nella finestra di dialogo **Generatore CellStyle** , definire lo stile impostando le proprietà e usare il riquadro di **Anteprima** per confermare le scelte effettuate.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-113">In the **CellStyle Builder** dialog box, define the style by setting the properties, and use the **Preview** pane to confirm your choices.</span></span> <span data-ttu-id="8fa4d-114">Gli stili specificati vengono usati per tutte le altre righe visualizzate nel controllo, a partire dal secondo.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-114">The styles you specify are used for every other row displayed in the control, starting with the second one.</span></span>

4. <span data-ttu-id="8fa4d-115">Per definire gli stili per le righe rimanenti, ripetere i passaggi 2 e <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 3 usando la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-115">To define styles for the remaining rows, repeat steps 2 and 3 using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8fa4d-116">Le celle vengono visualizzate utilizzando gli stili ereditati da più proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-116">Cells are displayed using styles inherited from multiple properties.</span></span> <span data-ttu-id="8fa4d-117">Per ulteriori informazioni sull'ereditarietà dello stile, vedere la pagina relativa agli [stili delle celle nel controllo DataGridView Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-117">For more information about style inheritance, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8fa4d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fa4d-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="8fa4d-119">Stili delle celle nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8fa4d-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8fa4d-120">Formattazione e stile di base nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8fa4d-120">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8fa4d-121">Uso della finestra di progettazione con il controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8fa4d-121">Using the Designer with the Windows Forms DataGridView Control</span></span>](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8fa4d-122">Procedura: Creare un progetto di Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="8fa4d-122">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="8fa4d-123">Procedura: Aggiungere controlli a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fa4d-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)

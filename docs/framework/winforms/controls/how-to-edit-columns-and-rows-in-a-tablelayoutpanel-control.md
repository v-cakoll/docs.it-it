---
title: 'Procedura: modificare colonne e righe in un controllo TableLayoutPanel'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: 4473b20eea57088104a51eb1b6c080219223d214
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628644"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="5ddd2-102">Procedura: modificare colonne e righe in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5ddd2-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>

<span data-ttu-id="5ddd2-103">Per modificare le righe e le colonne dei controlli, è possibile usare l'editor della raccolta del controllo <xref:System.Windows.Forms.TableLayoutPanel>, denominato finestra di dialogo **stili colonna e riga** .</span><span class="sxs-lookup"><span data-stu-id="5ddd2-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>

> [!NOTE]
> <span data-ttu-id="5ddd2-104">Se si desidera che un controllo si estenda su più righe o colonne, impostare le proprietà `RowSpan` e `ColumnSpan` sul controllo.</span><span class="sxs-lookup"><span data-stu-id="5ddd2-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="5ddd2-105">Per altre informazioni, vedere [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="5ddd2-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>
>
> <span data-ttu-id="5ddd2-106">Se si desidera allineare un controllo all'interno di una cella o se si desidera che un controllo si estenda all'interno di una cella, utilizzare la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> del controllo.</span><span class="sxs-lookup"><span data-stu-id="5ddd2-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="5ddd2-107">Per altre informazioni, vedere [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="5ddd2-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>

## <a name="to-edit-rows-and-columns"></a><span data-ttu-id="5ddd2-108">Per modificare righe e colonne</span><span class="sxs-lookup"><span data-stu-id="5ddd2-108">To edit rows and columns</span></span>

1. <span data-ttu-id="5ddd2-109">Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="5ddd2-109">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="5ddd2-110">Fare clic sul glifo delle azioni della finestra di progettazione del controllo <xref:System.Windows.Forms.TableLayoutPanel> (![Small Black Arrow](./media/designer-actions-glyph.gif)) e selezionare **modifica righe e colonne** per aprire la finestra di dialogo **stili colonna e riga** .</span><span class="sxs-lookup"><span data-stu-id="5ddd2-110">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="5ddd2-111">È anche possibile fare clic con il pulsante destro del mouse sul controllo <xref:System.Windows.Forms.TableLayoutPanel> e scegliere **modifica righe e colonne** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="5ddd2-111">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>

3. <span data-ttu-id="5ddd2-112">Per aggiungere o rimuovere colonne, selezionare le **colonne** nella casella di riepilogo a discesa **tipo di membro** .</span><span class="sxs-lookup"><span data-stu-id="5ddd2-112">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>

4. <span data-ttu-id="5ddd2-113">Per aggiungere o rimuovere righe, selezionare **righe** dall'elenco a discesa **tipo di membro** .</span><span class="sxs-lookup"><span data-stu-id="5ddd2-113">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>

5. <span data-ttu-id="5ddd2-114">Fare clic sul pulsante **Aggiungi** per aggiungere una riga o una colonna alla fine dell'elenco dei **membri** .</span><span class="sxs-lookup"><span data-stu-id="5ddd2-114">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>

6. <span data-ttu-id="5ddd2-115">Fare clic sul pulsante **Inserisci** per aggiungere una riga o una colonna prima dell'elemento attualmente selezionato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5ddd2-115">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>

7. <span data-ttu-id="5ddd2-116">Se si aggiunge una riga o una colonna, selezionare il **tipo di dimensione** per la nuova riga o colonna.</span><span class="sxs-lookup"><span data-stu-id="5ddd2-116">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="5ddd2-117">Per altre informazioni, vedere <xref:System.Windows.Forms.SizeType>.</span><span class="sxs-lookup"><span data-stu-id="5ddd2-117">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>

8. <span data-ttu-id="5ddd2-118">Per rimuovere una riga o una colonna, fare clic sul pulsante **Rimuovi** per eliminare l'elemento attualmente selezionato nell'elenco dei **membri** .</span><span class="sxs-lookup"><span data-stu-id="5ddd2-118">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ddd2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ddd2-119">See also</span></span>

- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="5ddd2-120">Controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5ddd2-120">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)

---
title: 'Procedura: Modificare colonne e righe in un controllo TableLayoutPanel'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: 40129deed1f43480b7bde59ef8a67f4561af5d38
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724687"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="a8976-102">Procedura: Modificare colonne e righe in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a8976-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>
<span data-ttu-id="a8976-103">È possibile usare l'editor della raccolta del <xref:System.Windows.Forms.TableLayoutPanel> controllo, ossia il **stili di riga e colonna** della finestra di dialogo per modificare le righe e colonne dei controlli.</span><span class="sxs-lookup"><span data-stu-id="a8976-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8976-104">Se si vuole un controllo per estendersi su più righe o colonne, impostare il `RowSpan` e `ColumnSpan` proprietà sul controllo.</span><span class="sxs-lookup"><span data-stu-id="a8976-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="a8976-105">Per altre informazioni, vedere [Procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="a8976-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="a8976-106">Se si desidera allineare un controllo all'interno di una cella o se si desidera un controllo da estendere all'interno di una cella, usare il controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8976-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="a8976-107">Per altre informazioni, vedere [Procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="a8976-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="a8976-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="a8976-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a8976-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="a8976-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a8976-110">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="a8976-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-edit-rows-and-columns"></a><span data-ttu-id="a8976-111">Per modificare righe e colonne</span><span class="sxs-lookup"><span data-stu-id="a8976-111">To edit rows and columns</span></span>  
  
1.  <span data-ttu-id="a8976-112">Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="a8976-112">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="a8976-113">Scegliere il <xref:System.Windows.Forms.TableLayoutPanel> glifo smart tag del controllo (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) e selezionare **Modifica righe e colonne** per aprire il  **Stili di riga e colonna** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="a8976-113">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="a8976-114">È possibile anche con il pulsante destro selezionare la <xref:System.Windows.Forms.TableLayoutPanel> controllo e scegliere **Modifica righe e colonne** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="a8976-114">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="a8976-115">Per aggiungere o rimuovere colonne, selezionare **colonne** dalle **tipo di membro** casella di riepilogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="a8976-115">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>  
  
4.  <span data-ttu-id="a8976-116">Per aggiungere o rimuovere righe, selezionare **righe** dalle **tipo di membro** casella di riepilogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="a8976-116">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>  
  
5.  <span data-ttu-id="a8976-117">Fare clic sui **Add** per aggiungere una riga o colonna alla fine della **membro** elenco.</span><span class="sxs-lookup"><span data-stu-id="a8976-117">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>  
  
6.  <span data-ttu-id="a8976-118">Fare clic sui **Inserisci** pulsante per aggiungere una riga o colonna prima dell'elemento attualmente selezionato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a8976-118">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>  
  
7.  <span data-ttu-id="a8976-119">Se si aggiunge una riga o colonna, selezionare la **tipo di dimensione** per la nuova riga o colonna.</span><span class="sxs-lookup"><span data-stu-id="a8976-119">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="a8976-120">Per altre informazioni, vedere <xref:System.Windows.Forms.SizeType>.</span><span class="sxs-lookup"><span data-stu-id="a8976-120">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>  
  
8.  <span data-ttu-id="a8976-121">Per rimuovere una riga o colonna, scegliere il **rimuovere** pulsante per eliminare l'elemento attualmente selezionato nel **membro** elenco.</span><span class="sxs-lookup"><span data-stu-id="a8976-121">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8976-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8976-122">See also</span></span>
- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="a8976-123">Controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a8976-123">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)

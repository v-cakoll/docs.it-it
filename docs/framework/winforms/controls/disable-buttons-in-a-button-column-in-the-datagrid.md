---
title: Disabilitare i pulsanti in una colonna di un pulsante nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
ms.openlocfilehash: 691781a43005d66e13029ab8110eb7f9daacc35f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745944"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2f711-102">Procedura: disabilitare i pulsanti in una colonna del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2f711-102">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2f711-103">Il controllo <xref:System.Windows.Forms.DataGridView> comprende la classe <xref:System.Windows.Forms.DataGridViewButtonCell> per la visualizzazione delle celle con un'interfaccia utente simile a un pulsante.</span><span class="sxs-lookup"><span data-stu-id="2f711-103">The <xref:System.Windows.Forms.DataGridView> control includes the <xref:System.Windows.Forms.DataGridViewButtonCell> class for displaying cells with a user interface (UI) like a button.</span></span> <span data-ttu-id="2f711-104">La classe <xref:System.Windows.Forms.DataGridViewButtonCell> non fornisce tuttavia un modo per visualizzare il pulsante nella cella come disabilitato.</span><span class="sxs-lookup"><span data-stu-id="2f711-104">However, <xref:System.Windows.Forms.DataGridViewButtonCell> does not provide a way to disable the appearance of the button displayed by the cell.</span></span>  
  
 <span data-ttu-id="2f711-105">L'esempio di codice seguente illustra come personalizzare la classe <xref:System.Windows.Forms.DataGridViewButtonCell> per visualizzare pulsanti che possono apparire disabilitati.</span><span class="sxs-lookup"><span data-stu-id="2f711-105">The following code example demonstrates how to customize the <xref:System.Windows.Forms.DataGridViewButtonCell> class to display buttons that can appear disabled.</span></span> <span data-ttu-id="2f711-106">Nell'esempio viene definito un nuovo tipo di cella, `DataGridViewDisableButtonCell`, derivato dalla classe <xref:System.Windows.Forms.DataGridViewButtonCell>.</span><span class="sxs-lookup"><span data-stu-id="2f711-106">The example defines a new cell type, `DataGridViewDisableButtonCell`, that derives from <xref:System.Windows.Forms.DataGridViewButtonCell>.</span></span> <span data-ttu-id="2f711-107">Questo tipo di cella fornisce la nuova proprietà `Enabled`, che può essere impostata su `false` per disegnare un pulsante disabilitato nella cella.</span><span class="sxs-lookup"><span data-stu-id="2f711-107">This cell type provides a new `Enabled` property that can be set to `false` to draw a disabled button in the cell.</span></span> <span data-ttu-id="2f711-108">Viene inoltre definito il nuovo tipo di colonna `DataGridViewDisableButtonColumn`, in cui sono visualizzati oggetti `DataGridViewDisableButtonCell`.</span><span class="sxs-lookup"><span data-stu-id="2f711-108">The example also defines a new column type, `DataGridViewDisableButtonColumn`, that displays `DataGridViewDisableButtonCell` objects.</span></span> <span data-ttu-id="2f711-109">Per illustrare il funzionamento del nuovo tipo di cella e di colonna, il valore corrente di ciascun oggetto <xref:System.Windows.Forms.DataGridViewCheckBoxCell> nel controllo <xref:System.Windows.Forms.DataGridView> padre determina se la proprietà `Enabled` di `DataGridViewDisableButtonCell` nella stessa riga è `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="2f711-109">To demonstrate this new cell and column type, the current value of each <xref:System.Windows.Forms.DataGridViewCheckBoxCell> in the parent <xref:System.Windows.Forms.DataGridView> determines whether the `Enabled` property of the `DataGridViewDisableButtonCell` in the same row is `true` or `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f711-110">Quando si deriva dalla classe <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewColumn> e si aggiungono nuove proprietà alla classe derivata, accertarsi di eseguire l'override del metodo `Clone` per copiare le nuove proprietà durante le operazioni di clonazione.</span><span class="sxs-lookup"><span data-stu-id="2f711-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="2f711-111">È anche necessario chiamare il metodo `Clone` della classe base in modo che le proprietà della classe base vengano copiate nella nuova cella o colonna.</span><span class="sxs-lookup"><span data-stu-id="2f711-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f711-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f711-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2f711-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2f711-113">Compiling the Code</span></span>  
 <span data-ttu-id="2f711-114">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f711-114">This example requires:</span></span>  
  
- <span data-ttu-id="2f711-115">Riferimenti agli assembly System, System.Drawing, System.Windows.Forms e System.Windows.Forms.VisualStyles.</span><span class="sxs-lookup"><span data-stu-id="2f711-115">References to the System, System.Drawing, System.Windows.Forms and System.Windows.Forms.VisualStyles assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f711-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f711-116">See also</span></span>

- [<span data-ttu-id="2f711-117">Personalizzazione del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2f711-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2f711-118">Architettura del controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="2f711-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="2f711-119">Tipi di colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2f711-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)

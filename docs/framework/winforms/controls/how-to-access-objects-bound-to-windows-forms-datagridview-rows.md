---
title: Accedere a oggetti associati a righe DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
ms.openlocfilehash: 0b9a4becb78ae817141728467c1e9ea5b693476d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743171"
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a><span data-ttu-id="9842d-102">Procedura: accedere a oggetti associati a righe DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9842d-102">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>
<span data-ttu-id="9842d-103">A volte è utile visualizzare una tabella di informazioni archiviate in una raccolta di oggetti business.</span><span class="sxs-lookup"><span data-stu-id="9842d-103">Sometimes it is useful to display a table of information stored in a collection of business objects.</span></span> <span data-ttu-id="9842d-104">Quando si associa un controllo <xref:System.Windows.Forms.DataGridView> a una raccolta di questo tipo, ogni proprietà pubblica viene visualizzata nella rispettiva colonna, a meno che la proprietà non sia stata contrassegnata come non visualizzabile con <xref:System.ComponentModel.BrowsableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9842d-104">When you bind a <xref:System.Windows.Forms.DataGridView> control to such a collection, each public property is displayed in its own column unless the property has been marked non-browsable with a <xref:System.ComponentModel.BrowsableAttribute>.</span></span> <span data-ttu-id="9842d-105">Ad esempio, una raccolta di oggetti `Customer` avrebbe colonne come **Nome** e **Indirizzo**.</span><span class="sxs-lookup"><span data-stu-id="9842d-105">For example, a collection of `Customer` objects would have columns such as **Name** and **Address**.</span></span>  
  
 <span data-ttu-id="9842d-106">Se questi oggetti contengono informazioni aggiuntive e codice a cui si desidera accedere, è possibile raggiungerli tramite gli oggetti riga.</span><span class="sxs-lookup"><span data-stu-id="9842d-106">If these objects contain additional information and code that you want to access, you can reach it through row objects.</span></span> <span data-ttu-id="9842d-107">Nell'esempio di codice riportato di seguito, gli utenti possono selezionare più righe e fare clic su un pulsante per inviare una fattura a ogni cliente corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9842d-107">In the following code example, users can select multiple rows and click a button to send an invoice to each of the corresponding customers.</span></span>  
  
### <a name="to-access-row-bound-objects"></a><span data-ttu-id="9842d-108">Per accedere agli oggetti associati a righe</span><span class="sxs-lookup"><span data-stu-id="9842d-108">To access row-bound objects</span></span>  
  
- <span data-ttu-id="9842d-109">Usare la proprietà <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9842d-109">Use the <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="9842d-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="9842d-110">Example</span></span>  
 <span data-ttu-id="9842d-111">L'esempio di codice completo include una semplice implementazione `Customer` e associa <xref:System.Windows.Forms.DataGridView> a un oggetto <xref:System.Collections.ArrayList> contenente alcuni oggetti `Customer`.</span><span class="sxs-lookup"><span data-stu-id="9842d-111">The complete code example includes a simple `Customer` implementation and binds the <xref:System.Windows.Forms.DataGridView> to an <xref:System.Collections.ArrayList> containing a few `Customer` objects.</span></span> <span data-ttu-id="9842d-112">Il gestore dell'evento <xref:System.Windows.Forms.Control.Click> di <xref:System.Windows.Forms.Button?displayProperty=nameWithType> deve accedere agli oggetti `Customer` tramite le righe, perché la raccolta di clienti non è accessibile al di fuori del gestore dell'evento <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9842d-112">The <xref:System.Windows.Forms.Control.Click> event handler of the <xref:System.Windows.Forms.Button?displayProperty=nameWithType> must access the `Customer` objects through the rows, because the customer collection is not accessible outside the <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> event handler.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9842d-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="9842d-113">Compiling the Code</span></span>  
 <span data-ttu-id="9842d-114">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9842d-114">This example requires:</span></span>  
  
- <span data-ttu-id="9842d-115">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9842d-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9842d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9842d-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9842d-117">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9842d-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="9842d-118">Procedura: Associare oggetti ai controlli DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9842d-118">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)

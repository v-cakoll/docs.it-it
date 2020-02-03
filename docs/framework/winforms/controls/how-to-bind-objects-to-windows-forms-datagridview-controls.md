---
title: Associare oggetti ai controlli DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: d5aa5cb64c7fb2b82d69d6c87134ee901b84f5c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746708"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a><span data-ttu-id="a0f4a-102">Procedura: associare oggetti ai controlli DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a0f4a-102">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="a0f4a-103">L'esempio di codice seguente illustra come associare un insieme di oggetti a un controllo <xref:System.Windows.Forms.DataGridView> in modo che ogni oggetto venga visualizzato come riga separata.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-103">The following code example demonstrates how to bind a collection of objects to a <xref:System.Windows.Forms.DataGridView> control so that each object displays as a separate row.</span></span> <span data-ttu-id="a0f4a-104">L'esempio descrive anche come visualizzare una proprietà con un tipo di enumerazione in una classe <xref:System.Windows.Forms.DataGridViewComboBoxColumn> in maniera che l'elenco a discesa della casella combinata contenga i valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-104">This example also illustrates how to display a property with an enumeration type in a <xref:System.Windows.Forms.DataGridViewComboBoxColumn> so that the combo box drop-down list contains the enumeration values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0f4a-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="a0f4a-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a0f4a-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a0f4a-106">Compiling the Code</span></span>  
 <span data-ttu-id="a0f4a-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0f4a-107">This example requires:</span></span>  
  
- <span data-ttu-id="a0f4a-108">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0f4a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0f4a-109">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="a0f4a-110">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a0f4a-110">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a0f4a-111">Procedura: Accedere a oggetti associati a righe di DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a0f4a-111">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)

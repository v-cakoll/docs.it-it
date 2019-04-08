---
title: 'Procedura: Usare il modello di riga per personalizzare le righe nel controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: cb3a826262a49a8653e3a344bd126d434f2522dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073043"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="0353a-102">Procedura: Usare il modello di riga per personalizzare le righe nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0353a-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0353a-103">Il <xref:System.Windows.Forms.DataGridView> controllo Usa il modello di riga come base per tutte le righe da aggiungere al controllo tramite associazione dati o quando si chiama il <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> metodo senza specificare una riga esistente da usare.</span><span class="sxs-lookup"><span data-stu-id="0353a-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="0353a-104">Il modello di riga offre un maggiore controllo sull'aspetto e comportamento di righe di <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> fornisce proprietà.</span><span class="sxs-lookup"><span data-stu-id="0353a-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="0353a-105">Con il modello di riga, è possibile impostare qualsiasi <xref:System.Windows.Forms.DataGridViewRow> proprietà, tra cui <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="0353a-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="0353a-106">Esistono alcune situazioni in cui è necessario utilizzare il modello di riga per ottenere un risultato particolare.</span><span class="sxs-lookup"><span data-stu-id="0353a-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="0353a-107">Ad esempio, le informazioni sull'altezza di riga non può essere archiviati un <xref:System.Windows.Forms.DataGridViewCellStyle>, pertanto è necessario usare un modello di riga per modificare l'altezza predefinita per tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="0353a-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="0353a-108">Il modello di riga è utile anche quando si creano il proprio classi derivate da <xref:System.Windows.Forms.DataGridViewRow> e si desidera utilizzare un tipo personalizzato al controllo vengono aggiunte nuove righe.</span><span class="sxs-lookup"><span data-stu-id="0353a-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0353a-109">Il modello di riga viene utilizzato solo quando vengono aggiunte righe.</span><span class="sxs-lookup"><span data-stu-id="0353a-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="0353a-110">È possibile modificare le righe esistenti modificando il modello di riga.</span><span class="sxs-lookup"><span data-stu-id="0353a-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="0353a-111">Usare il modello di riga</span><span class="sxs-lookup"><span data-stu-id="0353a-111">To use the row template</span></span>  
  
-   <span data-ttu-id="0353a-112">Impostare le proprietà per l'oggetto recuperato dal <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="0353a-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0353a-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0353a-113">Compiling the Code</span></span>  
 <span data-ttu-id="0353a-114">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0353a-114">This example requires:</span></span>  
  
-   <span data-ttu-id="0353a-115">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="0353a-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="0353a-116">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0353a-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0353a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0353a-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0353a-118">Formattazione e stile di base nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="0353a-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="0353a-119">Stili della cella nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="0353a-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)

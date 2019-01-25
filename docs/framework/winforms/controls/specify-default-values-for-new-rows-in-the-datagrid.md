---
title: 'Procedura: Specificare i valori predefiniti per le nuove righe nel controllo DataGridView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
ms.openlocfilehash: dab9ba7ca16cf0c886601e3c8fea579e70b2f30d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596774"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="659dc-102">Procedura: Specificare i valori predefiniti per le nuove righe nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="659dc-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="659dc-103">È possibile rendere più pratico immissione di dati quando l'applicazione predefinita compilato utilizzando i valori per le righe appena aggiunte.</span><span class="sxs-lookup"><span data-stu-id="659dc-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="659dc-104">Con il <xref:System.Windows.Forms.DataGridView> (classe), è possibile inserire i valori predefiniti con il <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> evento.</span><span class="sxs-lookup"><span data-stu-id="659dc-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="659dc-105">Questo evento viene generato quando l'utente immette la riga per i nuovi record.</span><span class="sxs-lookup"><span data-stu-id="659dc-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="659dc-106">Quando il codice gestisce questo evento, è possibile popolare desiderate celle con valori di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="659dc-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="659dc-107">Esempio di codice seguente viene illustrato come specificare i valori predefiniti per le nuove righe usando la <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> evento.</span><span class="sxs-lookup"><span data-stu-id="659dc-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="659dc-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="659dc-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="659dc-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="659dc-109">Compiling the Code</span></span>  
 <span data-ttu-id="659dc-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="659dc-110">This example requires:</span></span>  
  
-   <span data-ttu-id="659dc-111">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="659dc-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="659dc-112">Oggetto `NewCustomerId` funzione per la generazione univoco `CustomerID` valori.</span><span class="sxs-lookup"><span data-stu-id="659dc-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
-   <span data-ttu-id="659dc-113">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="659dc-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="659dc-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="659dc-114">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [<span data-ttu-id="659dc-115">Immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="659dc-115">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="659dc-116">Uso della riga per i nuovi record del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="659dc-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)

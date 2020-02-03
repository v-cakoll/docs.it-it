---
title: Specificare i valori predefiniti per le nuove righe nel controllo DataGridView
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
ms.openlocfilehash: 364f922aefc10e57f2ed7f3a0c2a5b25c922d87a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742937"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="ee4d7-102">Procedura: specificare i valori predefiniti per le nuove righe nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ee4d7-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="ee4d7-103">È possibile rendere più semplice l'immissione dei dati quando l'applicazione compila i valori predefiniti per le nuove righe aggiunte.</span><span class="sxs-lookup"><span data-stu-id="ee4d7-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="ee4d7-104">Con la classe <xref:System.Windows.Forms.DataGridView>, è possibile inserire i valori predefiniti con l'evento <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.</span><span class="sxs-lookup"><span data-stu-id="ee4d7-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="ee4d7-105">Questo evento viene generato quando l'utente immette la riga per i nuovi record.</span><span class="sxs-lookup"><span data-stu-id="ee4d7-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="ee4d7-106">Quando il codice gestisce questo evento, è possibile popolare le celle desiderate con i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="ee4d7-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="ee4d7-107">Nell'esempio di codice seguente viene illustrato come specificare i valori predefiniti per le nuove righe utilizzando l'evento <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.</span><span class="sxs-lookup"><span data-stu-id="ee4d7-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee4d7-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee4d7-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ee4d7-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ee4d7-109">Compiling the Code</span></span>  
 <span data-ttu-id="ee4d7-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee4d7-110">This example requires:</span></span>  
  
- <span data-ttu-id="ee4d7-111">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="ee4d7-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="ee4d7-112">Funzione `NewCustomerId` per la generazione di valori `CustomerID` univoci.</span><span class="sxs-lookup"><span data-stu-id="ee4d7-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
- <span data-ttu-id="ee4d7-113">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee4d7-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee4d7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee4d7-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [<span data-ttu-id="ee4d7-115">Immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ee4d7-115">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="ee4d7-116">Uso della riga per i nuovi record del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ee4d7-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)

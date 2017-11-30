---
title: 'Procedura: specificare i valori predefiniti per le nuove righe nel controllo DataGridView di Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 577d5c3bc4b4afef845cd51b62b7d48fcc9d4a7e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="7ca84-102">Procedura: specificare i valori predefiniti per le nuove righe nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="7ca84-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7ca84-103">È possibile rendere più semplice immissione dei dati quando l'applicazione predefinita inserisce i valori per le righe appena aggiunte.</span><span class="sxs-lookup"><span data-stu-id="7ca84-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="7ca84-104">Con il <xref:System.Windows.Forms.DataGridView> (classe), è possibile inserire i valori predefiniti con il <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> evento.</span><span class="sxs-lookup"><span data-stu-id="7ca84-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="7ca84-105">Questo evento viene generato quando l'utente immette la riga per nuovi record.</span><span class="sxs-lookup"><span data-stu-id="7ca84-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="7ca84-106">Quando il codice gestisce questo evento, è possibile popolare desiderate celle con valori di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="7ca84-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="7ca84-107">Esempio di codice riportato di seguito viene illustrato come specificare i valori predefiniti per le nuove righe utilizzando la <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> evento.</span><span class="sxs-lookup"><span data-stu-id="7ca84-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ca84-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ca84-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7ca84-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7ca84-109">Compiling the Code</span></span>  
 <span data-ttu-id="7ca84-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ca84-110">This example requires:</span></span>  
  
-   <span data-ttu-id="7ca84-111">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="7ca84-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="7ca84-112">Oggetto `NewCustomerId` funzione per la generazione univoco `CustomerID` valori.</span><span class="sxs-lookup"><span data-stu-id="7ca84-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
-   <span data-ttu-id="7ca84-113">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7ca84-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ca84-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ca84-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 [<span data-ttu-id="7ca84-115">Immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="7ca84-115">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="7ca84-116">Uso della riga per i nuovi record del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="7ca84-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)

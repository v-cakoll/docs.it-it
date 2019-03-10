---
title: 'Procedura: Creare un bordo intorno a un controllo Windows Form usando il riempimento di controllo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
ms.openlocfilehash: 66748eef299c9175814fb130a7eda359c5de0546
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720306"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a><span data-ttu-id="76aeb-102">Procedura: Creare un bordo intorno a un controllo Windows Form usando il riempimento di controllo</span><span class="sxs-lookup"><span data-stu-id="76aeb-102">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>
<span data-ttu-id="76aeb-103">Esempio di codice seguente viene illustrato come creare un bordo o di struttura intorno a un <xref:System.Windows.Forms.RichTextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="76aeb-103">The following code example demonstrates how to create a border or outline around a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="76aeb-104">L'esempio imposta il valore di un <xref:System.Windows.Forms.Panel> del controllo <xref:System.Windows.Forms.Padding> proprietà su 5 e il <xref:System.Windows.Forms.Control.Dock%2A> proprietà di un elemento figlio <xref:System.Windows.Forms.RichTextBox> il controllo a <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="76aeb-104">The example sets the value of a <xref:System.Windows.Forms.Panel> control’s <xref:System.Windows.Forms.Padding> property to 5 and sets the <xref:System.Windows.Forms.Control.Dock%2A> property of a child <xref:System.Windows.Forms.RichTextBox> control to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="76aeb-105">Il <xref:System.Windows.Forms.Control.BackColor%2A> del <xref:System.Windows.Forms.Panel> NFS è impostata su <xref:System.Drawing.Color.Blue%2A>, che consente di creare un bordo blu il <xref:System.Windows.Forms.RichTextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="76aeb-105">The <xref:System.Windows.Forms.Control.BackColor%2A> of the <xref:System.Windows.Forms.Panel> control is set to <xref:System.Drawing.Color.Blue%2A>, which creates a blue border around the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76aeb-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="76aeb-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="76aeb-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76aeb-107">See also</span></span>
- <xref:System.Windows.Forms.Padding>
- [<span data-ttu-id="76aeb-108">Margini e spaziatura nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="76aeb-108">Margin and Padding in Windows Forms Controls</span></span>](margin-and-padding-in-windows-forms-controls.md)

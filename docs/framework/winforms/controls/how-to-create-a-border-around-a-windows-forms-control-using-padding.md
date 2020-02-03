---
title: Creare un bordo intorno a un controllo usando la spaziatura interna
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
ms.openlocfilehash: 114186ab5784cf892cb01e9fe2648ce22cecc4b7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742195"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a><span data-ttu-id="60a7b-102">Procedura: creare un bordo intorno a un controllo di Windows Form mediante la spaziatura</span><span class="sxs-lookup"><span data-stu-id="60a7b-102">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>
<span data-ttu-id="60a7b-103">Nell'esempio di codice riportato di seguito viene illustrato come creare un bordo o un contorno attorno a un controllo <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="60a7b-103">The following code example demonstrates how to create a border or outline around a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="60a7b-104">Nell'esempio viene impostato il valore della proprietà <xref:System.Windows.Forms.Padding> di un controllo <xref:System.Windows.Forms.Panel> su 5 e la proprietà <xref:System.Windows.Forms.Control.Dock%2A> di un controllo <xref:System.Windows.Forms.RichTextBox> figlio viene impostata su <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="60a7b-104">The example sets the value of a <xref:System.Windows.Forms.Panel> control’s <xref:System.Windows.Forms.Padding> property to 5 and sets the <xref:System.Windows.Forms.Control.Dock%2A> property of a child <xref:System.Windows.Forms.RichTextBox> control to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="60a7b-105">Il <xref:System.Windows.Forms.Control.BackColor%2A> del controllo <xref:System.Windows.Forms.Panel> è impostato su <xref:System.Drawing.Color.Blue%2A>, che crea un bordo blu attorno al controllo <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="60a7b-105">The <xref:System.Windows.Forms.Control.BackColor%2A> of the <xref:System.Windows.Forms.Panel> control is set to <xref:System.Drawing.Color.Blue%2A>, which creates a blue border around the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60a7b-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="60a7b-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="60a7b-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60a7b-107">See also</span></span>

- <xref:System.Windows.Forms.Padding>
- [<span data-ttu-id="60a7b-108">Margini e spaziatura nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="60a7b-108">Margin and Padding in Windows Forms Controls</span></span>](margin-and-padding-in-windows-forms-controls.md)

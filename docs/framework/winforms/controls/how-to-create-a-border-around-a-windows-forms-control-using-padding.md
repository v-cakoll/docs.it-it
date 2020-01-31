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
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>Procedura: creare un bordo intorno a un controllo di Windows Form mediante la spaziatura
Nell'esempio di codice riportato di seguito viene illustrato come creare un bordo o un contorno attorno a un controllo <xref:System.Windows.Forms.RichTextBox>. Nell'esempio viene impostato il valore della proprietà <xref:System.Windows.Forms.Padding> di un controllo <xref:System.Windows.Forms.Panel> su 5 e la proprietà <xref:System.Windows.Forms.Control.Dock%2A> di un controllo <xref:System.Windows.Forms.RichTextBox> figlio viene impostata su <xref:System.Windows.Forms.DockStyle.Fill>. Il <xref:System.Windows.Forms.Control.BackColor%2A> del controllo <xref:System.Windows.Forms.Panel> è impostato su <xref:System.Drawing.Color.Blue%2A>, che crea un bordo blu attorno al controllo <xref:System.Windows.Forms.RichTextBox>.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Padding>
- [Margini e spaziatura nei controlli Windows Form](margin-and-padding-in-windows-forms-controls.md)

---
title: 'Procedura: creare un bordo intorno a un controllo di Windows Form mediante la spaziatura'
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
ms.openlocfilehash: 7866b78afd768fa99ceacfdee13c086a9ac00e0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530289"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>Procedura: creare un bordo intorno a un controllo di Windows Form mediante la spaziatura
Esempio di codice riportato di seguito viene illustrato come creare un bordo o di struttura intorno a un <xref:System.Windows.Forms.RichTextBox> controllo. Nell'esempio viene impostato il valore di un <xref:System.Windows.Forms.Panel> del controllo <xref:System.Windows.Forms.Padding> su 5 e imposta il <xref:System.Windows.Forms.Control.Dock%2A> proprietà di un elemento figlio <xref:System.Windows.Forms.RichTextBox> il controllo a <xref:System.Windows.Forms.DockStyle.Fill>. Il <xref:System.Windows.Forms.Control.BackColor%2A> del <xref:System.Windows.Forms.Panel> NFS è impostata su <xref:System.Drawing.Color.Blue%2A>, che consente di creare un bordo blu il <xref:System.Windows.Forms.RichTextBox> controllo.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.Padding#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Padding>  
 [Margini e spaziatura nei controlli Windows Form](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)

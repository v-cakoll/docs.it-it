---
title: 'Procedura: Creare un bordo intorno a un controllo di Windows Forms usando la spaziatura'
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
ms.openlocfilehash: e3bbf43dbe45e675df172a6c3e1db16a3ba9caa8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124026"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>Procedura: Creare un bordo intorno a un controllo di Windows Forms usando la spaziatura
Esempio di codice seguente viene illustrato come creare un bordo o di struttura intorno a un <xref:System.Windows.Forms.RichTextBox> controllo. L'esempio imposta il valore di un <xref:System.Windows.Forms.Panel> del controllo <xref:System.Windows.Forms.Padding> proprietà su 5 e il <xref:System.Windows.Forms.Control.Dock%2A> proprietà di un elemento figlio <xref:System.Windows.Forms.RichTextBox> il controllo a <xref:System.Windows.Forms.DockStyle.Fill>. Il <xref:System.Windows.Forms.Control.BackColor%2A> del <xref:System.Windows.Forms.Panel> NFS è impostata su <xref:System.Drawing.Color.Blue%2A>, che consente di creare un bordo blu il <xref:System.Windows.Forms.RichTextBox> controllo.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Padding>
- [Margini e spaziatura nei controlli Windows Form](margin-and-padding-in-windows-forms-controls.md)

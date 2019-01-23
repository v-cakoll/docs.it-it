---
title: 'Procedura: Usare una classe Control Rendering'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: 4453e04f6fe36ad2b0de7696da68d55264cd47b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534670"
---
# <a name="how-to-use-a-control-rendering-class"></a>Procedura: Usare una classe Control Rendering
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Forms.ComboBoxRenderer> classe per il rendering di controllo di finestra la freccia a discesa di una casella combinata. L'esempio è costituito il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo di un controllo personalizzato semplice. Il <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> proprietà viene utilizzata per determinare se gli stili di visualizzazione sono abilitati nell'area client delle finestre dell'applicazione. Se gli stili visivi sono attivi, il <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> metodo verrà eseguito il rendering la freccia a discesa con stili di visualizzazione; in caso contrario, il <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> metodo verrà eseguito il rendering sulla freccia giù nello stile classico di Windows.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo personalizzato derivato dal <xref:System.Windows.Forms.Control> classe.  
  
-   Oggetto <xref:System.Windows.Forms.Form> che ospita il controllo personalizzato.  
  
-   Fa riferimento per la <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, e <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> gli spazi dei nomi.  
  
## <a name="see-also"></a>Vedere anche
- [Rendering dei controlli con stili visivi](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)

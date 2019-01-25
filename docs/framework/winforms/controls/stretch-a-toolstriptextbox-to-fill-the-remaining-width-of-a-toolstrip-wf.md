---
title: 'Procedura: Allargare ToolStripTextBox la parte rimanente di un controllo ToolStrip (Windows Form)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: 411c00743f0a02bdd498211d03b195aaaf023ecb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612268"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>Procedura: Allargare ToolStripTextBox la parte rimanente di un controllo ToolStrip (Windows Form)
Quando si imposta il <xref:System.Windows.Forms.ToolStrip.Stretch%2A> proprietà di un <xref:System.Windows.Forms.ToolStrip> il controllo a `true`, il controllo riempimento dall'inizio alla fine del contenitore e ridimensiona quando si ridimensiona il relativo contenitore. In questa configurazione, si potrebbe risultare utile per estendere un elemento nel controllo, ad esempio un <xref:System.Windows.Forms.ToolStripTextBox>, per riempire lo spazio disponibile e ridimensionati quando il controllo viene ridimensionato. Questa estensione è utile, ad esempio, se si vuole ottenere un aspetto e comportamento simile alla barra degli indirizzi in Microsoft® Internet Explorer.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente fornisce una classe derivata da <xref:System.Windows.Forms.ToolStripTextBox> chiamato `ToolStripSpringTextBox`. Questa classe esegue l'override di <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> metodo per calcolare la larghezza dell'elemento padre disponibile <xref:System.Windows.Forms.ToolStrip> controllo dopo che la larghezza combinata di tutti gli altri elementi è stato sottratto. Questo esempio di codice fornisce anche un <xref:System.Windows.Forms.Form> classe e un `Program` classe dimostrano il nuovo comportamento.  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [Architettura del controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)
- [Procedura: Usare la proprietà Spring in modo interattivo in un controllo StatusStrip](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)

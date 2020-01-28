---
title: 'Procedura: allargare un oggetto ToolStripTextBox in modo da coprire tutta la larghezza di un elemento ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742846"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>Procedura: allargare un oggetto ToolStripTextBox in modo da coprire tutta la larghezza di un elemento ToolStrip (Windows Form)
Quando si imposta la proprietà <xref:System.Windows.Forms.ToolStrip.Stretch%2A> di un controllo <xref:System.Windows.Forms.ToolStrip> su `true`, il controllo riempie il contenitore da fine a fine e viene ridimensionato quando il relativo contenitore viene ridimensionato. In questa configurazione può risultare utile estendere un elemento del controllo, ad esempio un <xref:System.Windows.Forms.ToolStripTextBox>, per riempire lo spazio disponibile e ridimensionare quando il controllo viene ridimensionato. Questa estensione è utile, ad esempio, se si desidera ottenere un aspetto e un comportamento simili alla barra degli indirizzi in Microsoft® Internet Explorer.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene fornita una classe derivata da <xref:System.Windows.Forms.ToolStripTextBox> denominata `ToolStripSpringTextBox`. Questa classe esegue l'override del metodo <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> per calcolare la larghezza disponibile del controllo <xref:System.Windows.Forms.ToolStrip> padre dopo che la larghezza combinata di tutti gli altri elementi è stata sottratta. Questo esempio di codice fornisce anche una classe <xref:System.Windows.Forms.Form> e una classe `Program` per illustrare il nuovo comportamento.  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)
- [Procedura: Usare la proprietà Spring in modo interattivo in un controllo StatusStrip](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)

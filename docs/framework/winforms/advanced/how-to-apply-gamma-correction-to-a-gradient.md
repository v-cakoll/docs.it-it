---
title: 'Procedura: Applicare la correzione gamma a una sfumatura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e812e441233c1d29a67dac639048e20a659549f0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753563"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>Procedura: Applicare la correzione gamma a una sfumatura
È possibile abilitare la correzione gamma per un pennello sfumato lineare impostando la proprietà del pennello <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà `true`. È possibile disabilitare la correzione gamma impostando il <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà `false`. La correzione gamma è disabilitata per impostazione predefinita.  
  
## <a name="example"></a>Esempio  

Nell'esempio seguente è un metodo che viene chiamato da un controllo <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. L'esempio crea un pennello sfumato lineare e tale utilizzato per riempire i due rettangoli. Il primo rettangolo viene riempito senza la correzione gamma e il secondo rettangolo viene riempito con la correzione gamma.  
  
 La figura seguente mostra i due rettangoli colorati. Il rettangolo superiore che non dispone di correzione gamma, viene visualizzato scuro al centro. Il rettangolo nella parte inferiore che include la correzione gamma, sembra avere ulteriori intensità uniforme.  
  
 ![Due riempimento sfumatura rettangoli, con e senza la correzione gamma.](./media/how-to-apply-gamma-correction-to-a-gradient/two-rectangles-gamma-gradient.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [Uso di un pennello a sfumatura per il riempimento di forme](using-a-gradient-brush-to-fill-shapes.md)

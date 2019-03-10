---
title: 'Procedura: Applicare la correzione Gamma a una sfumatura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e7205058bc2b93ac453b8c37bfc8d5236433158d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708080"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>Procedura: Applicare la correzione Gamma a una sfumatura
È possibile abilitare la correzione gamma per un pennello sfumato lineare impostando la proprietà del pennello <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà `true`. È possibile disabilitare la correzione gamma impostando il <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà `false`. La correzione gamma è disabilitata per impostazione predefinita.  
  
## <a name="example"></a>Esempio  
 L'esempio crea un pennello sfumato lineare e tale utilizzato per riempire i due rettangoli. Il primo rettangolo viene riempito senza la correzione gamma e il secondo rettangolo viene riempito con la correzione gamma.  
  
 La figura seguente mostra i due rettangoli colorati. Il rettangolo superiore che non dispone di correzione gamma, viene visualizzato scuro al centro. Il rettangolo nella parte inferiore che include la correzione gamma, sembra avere ulteriori intensità uniforme.  
  
 ![Sfumatura](./media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Drawing2D.LinearGradientBrush>
- [Uso di un pennello a sfumatura per il riempimento di forme](using-a-gradient-brush-to-fill-shapes.md)

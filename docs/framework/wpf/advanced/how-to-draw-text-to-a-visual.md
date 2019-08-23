---
title: 'Procedura: Disegnare testo in un oggetto visivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: bd760a06150098d0fff17dbdce95b55a0e5fe713
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963853"
---
# <a name="how-to-draw-text-to-a-visual"></a>Procedura: Disegnare testo in un oggetto visivo
Nell'esempio seguente viene illustrato come creare un testo in <xref:System.Windows.Media.DrawingVisual> un oggetto <xref:System.Windows.Media.DrawingContext> utilizzando un oggetto. Un contesto di disegno viene restituito chiamando il <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> metodo di un <xref:System.Windows.Media.DrawingVisual> oggetto. È possibile disegnare grafica e testo in un contesto di disegno.  
  
 Per disegnare testo nel contesto di disegno, usare il <xref:System.Windows.Media.DrawingContext.DrawText%2A> metodo di un <xref:System.Windows.Media.DrawingContext> oggetto. Al termine della creazione del contenuto nel contesto di disegno, chiamare il <xref:System.Windows.Media.DrawingContext.Close%2A> metodo per chiudere il contesto di disegno e salvare in modo permanente il contenuto.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> Per l'esempio di codice completo dal quale è stato estratto l'esempio di codice precedente, vedere [Hit Test Using DrawingVisuals Sample (Esempio di Hit Test mediante DrawingVisual)](https://go.microsoft.com/fwlink/?LinkID=159994).

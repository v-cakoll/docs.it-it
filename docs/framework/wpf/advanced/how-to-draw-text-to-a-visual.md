---
title: 'Procedura: disegnare testo in un oggetto Visual'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 735a84a034587b1433403a45edc7c2f459340273
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-draw-text-to-a-visual"></a>Procedura: disegnare testo in un oggetto Visual
Nell'esempio seguente viene illustrato come disegnare testo in un <xref:System.Windows.Media.DrawingVisual> utilizzando un <xref:System.Windows.Media.DrawingContext> oggetto. Un contesto di disegno viene restituito dalla chiamata di <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> metodo di un <xref:System.Windows.Media.DrawingVisual> oggetto. È possibile creare grafica e testo in un contesto di disegno.  
  
 Per disegnare il testo nel contesto di disegno, utilizzare il <xref:System.Windows.Media.DrawingContext.DrawText%2A> metodo di un <xref:System.Windows.Media.DrawingContext> oggetto. Dopo aver terminato di disegno del contenuto nel contesto di disegno, chiamare il <xref:System.Windows.Media.DrawingContext.Close%2A> metodo per chiudere il contesto di disegno e mantenere il contenuto.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  Per l'esempio di codice completo dal quale è stato estratto l'esempio di codice precedente, vedere [Hit Test Using DrawingVisuals Sample (Esempio di Hit Test mediante DrawingVisual)](http://go.microsoft.com/fwlink/?LinkID=159994).

---
title: 'Procedura: Applicare animazioni al testo'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: 56a12ca915cc320619a094df38d118eabf202734
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545438"
---
# <a name="how-to-apply-animations-to-text"></a>Procedura: Applicare animazioni al testo
Le animazioni possono modificare la visualizzazione e l'aspetto del testo nell'applicazione. Negli esempi seguenti utilizzano tipi diversi di animazioni per modificare la visualizzazione di testo in un <xref:System.Windows.Controls.TextBlock> controllo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.Animation.DoubleAnimation> per animare la larghezza del blocco di testo. Il valore della larghezza varia dalla larghezza del blocco di testo a 0 per una durata pari a 10 secondi, quindi inverte i valori della larghezza e continua. Questo tipo di animazione crea un effetto a comparsa.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.Animation.DoubleAnimation> animare l'opacità del blocco di testo. Il valore dell'opacità varia da 1,0 a 0 per una durata pari a 5 secondi, quindi inverte i valori dell'opacità e continua.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 Il diagramma seguente mostra l'effetto del <xref:System.Windows.Controls.TextBlock> controllo modifica l'opacità da `1.00` a `0.00` durante l'intervallo di 5 secondi definito dal <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 ![Testo modifica di opacità da 1.00 a 0.00](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")  
Opacità del testo modificata da 1,00 a 0,00  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.Animation.ColorAnimation> animare il colore di primo piano del blocco di testo. Il valore del colore di primo piano varia da un colore a un altro per una durata pari a 5 secondi, quindi inverte i valori del colore e continua.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.Animation.DoubleAnimation> per ruotare il blocco di testo. Il blocco di testo esegue una rotazione completa per una durata pari a 20 secondi, quindi continua a ripetere la rotazione.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)

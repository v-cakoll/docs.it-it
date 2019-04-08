---
title: 'Procedura: Applicare animazioni al testo'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: 38aa432fecc5b5e10d8eb90be9c1c596728ed613
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108212"
---
# <a name="how-to-apply-animations-to-text"></a>Procedura: Applicare animazioni al testo
Le animazioni possono modificare la visualizzazione e l'aspetto del testo nell'applicazione. Gli esempi seguenti usano diversi tipi di animazioni per modificare la visualizzazione di testo in un <xref:System.Windows.Controls.TextBlock> controllo.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un <xref:System.Windows.Media.Animation.DoubleAnimation> per animare la larghezza del blocco di testo. Il valore della larghezza varia dalla larghezza del blocco di testo a 0 per una durata pari a 10 secondi, quindi inverte i valori della larghezza e continua. Questo tipo di animazione crea un effetto a comparsa.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 L'esempio seguente usa un <xref:System.Windows.Media.Animation.DoubleAnimation> animare l'opacità del blocco di testo. Il valore dell'opacità varia da 1,0 a 0 per una durata pari a 5 secondi, quindi inverte i valori dell'opacità e continua.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 Il diagramma seguente mostra l'effetto del <xref:System.Windows.Controls.TextBlock> modifica l'opacità viene modificata dal controllo `1.00` a `0.00` durante l'intervallo di 5 secondi definito dal <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 ![Testo modifica dell'opacità da 1,00 a 0,00.](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  
   
 L'esempio seguente usa un <xref:System.Windows.Media.Animation.ColorAnimation> animare il colore di primo piano del blocco di testo. Il valore del colore di primo piano varia da un colore a un altro per una durata pari a 5 secondi, quindi inverte i valori del colore e continua.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 L'esempio seguente usa un <xref:System.Windows.Media.Animation.DoubleAnimation> per ruotare il blocco di testo. Il blocco di testo esegue una rotazione completa per una durata pari a 20 secondi, quindi continua a ripetere la rotazione.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md)

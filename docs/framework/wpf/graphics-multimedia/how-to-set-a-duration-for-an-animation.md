---
title: "Procedura: impostare una durata per un'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: df9e12e1bd3a365c3013d0f75df663bd46186ee2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561375"
---
# <a name="how-to-set-a-duration-for-an-animation"></a>Procedura: impostare una durata per un'animazione
Oggetto <xref:System.Windows.Media.Animation.Timeline> rappresenta un intervallo di tempo e la lunghezza del segmento varia a seconda della sequenza temporale <xref:System.Windows.Duration>. Quando un <xref:System.Windows.Media.Animation.Timeline> raggiunge la fine della durata, la riproduzione viene interrotta. Se il <xref:System.Windows.Media.Animation.Timeline> ha sequenze temporali figlio, la relativa riproduzione anche interrotta. Nel caso di un'animazione, la <xref:System.Windows.Duration> specifica il tempo impiegato dall'animazione per la transizione dal valore iniziale al valore finale.  
  
 È possibile specificare un <xref:System.Windows.Duration> con un specifico tempo finito o il valore speciale <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>. Durata di un'animazione deve essere sempre un valore di ora, perché un'animazione deve sempre avere una lunghezza definita, finita, in caso contrario, l'animazione sarebbe in grado di eseguire la transizione tra i valori di destinazione. Le sequenze temporali contenitore (<xref:System.Windows.Media.Animation.TimelineGroup> oggetti), ad esempio <xref:System.Windows.Media.Animation.Storyboard> e <xref:System.Windows.Media.Animation.ParallelTimeline>, hanno una durata predefinita di <xref:System.Windows.Duration.Automatic%2A>, ovvero terminano automaticamente al termine dell'esecuzione dell'ultimo figlio.  
  
 Nel seguente esempio, la larghezza, altezza e riempimento colore di un <xref:System.Windows.Shapes.Rectangle> viene animata. Le durate sono impostate su sequenze temporali di animazione e il contenitore risultante in effetti di animazione, tra cui il controllo della velocità percepita di un'animazione e l'override della durata delle sequenze temporali figlio con la durata della sequenza temporale di un contenitore.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Duration>  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)

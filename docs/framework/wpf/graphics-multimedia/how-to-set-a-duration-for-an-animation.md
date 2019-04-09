---
title: "Procedura: Impostare una durata per un'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: bdae1689ffeb8c54d756b9debbd26d57a052892d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198790"
---
# <a name="how-to-set-a-duration-for-an-animation"></a>Procedura: Impostare una durata per un'animazione
Oggetto <xref:System.Windows.Media.Animation.Timeline> rappresenta un intervallo di tempo e la lunghezza di tale intervallo viene determinato dalla sequenza temporale <xref:System.Windows.Duration>. Quando un <xref:System.Windows.Media.Animation.Timeline> raggiunge la fine della durata, la riproduzione viene interrotta. Se il <xref:System.Windows.Media.Animation.Timeline> ha sequenze temporali figlio, la relativa riproduzione anche interrotta. Nel caso di un'animazione, il <xref:System.Windows.Duration> specifica il tempo impiegato dall'animazione per eseguire la transizione dal valore iniziale a quello finale.  
  
 È possibile specificare una <xref:System.Windows.Duration> con un specifico tempo finito o i valori speciali <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>. Durata di un'animazione deve essere sempre un valore di ora, poiché un'animazione deve sempre avere una lunghezza definita e limitata, in caso contrario, l'animazione non saprebbe come eseguire la transizione tra i valori di destinazione. Le sequenze temporali contenitore (<xref:System.Windows.Media.Animation.TimelineGroup> oggetti), ad esempio <xref:System.Windows.Media.Animation.Storyboard> e <xref:System.Windows.Media.Animation.ParallelTimeline>, hanno una durata predefinita di <xref:System.Windows.Duration.Automatic%2A>, il che significa che si trova automaticamente al termine dell'esecuzione dell'ultima sequenza figlio.  
  
 Nel seguente esempio, la larghezza, altezza e riempimento colore di un <xref:System.Windows.Shapes.Rectangle> viene animata. Le durate sono impostate su sequenze temporali di animazione e il contenitore risultante in effetti di animazione tra cui il controllo della velocità percepita di un'animazione e la durata delle sequenze temporali figlio con la durata di una sequenza temporale contenitore viene sottoposto a override.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Duration>
- [Cenni preliminari sull'animazione](animation-overview.md)

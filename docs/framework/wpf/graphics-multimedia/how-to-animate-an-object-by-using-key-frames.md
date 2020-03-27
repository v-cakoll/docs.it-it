---
title: 'Procedura: animare un oggetto utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0bc33b189fd856dbe8106c1db35bc18e27ea131e
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344712"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>Procedura: animare un oggetto utilizzando fotogrammi chiave
In questo esempio viene illustrato come animare <xref:System.Windows.Controls.Page.Background%2A> un oggetto, che in questo esempio è la proprietà di un <xref:System.Windows.Controls.Page> controllo, utilizzando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> viene utilizzata la <xref:System.Windows.Controls.Page.Background%2A> classe per <xref:System.Windows.Controls.Page> animare le modifiche di colore per la proprietà di un controllo. L'animazione di esempio diventa un pennello di sfondo diverso a intervalli regolari. Questa animazione <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> usa la classe per creare tre diversi fotogrammi chiave. L'animazione utilizza i fotogrammi chiave nel modo seguente:  
  
1. Alla fine del primo secondo, aggiunge un'animazione a un'istanza della <xref:System.Windows.Media.LinearGradientBrush> classe. Questa sezione dell'esempio applica una sfumatura lineare al colore di sfondo in modo che il colore si snoda dal giallo all'arancione al rosso.  
  
2. Alla fine del secondo successivo, aggiunge un'animazione a un'istanza della <xref:System.Windows.Media.RadialGradientBrush> classe. Questa sezione dell'esempio applica una sfumatura radiale al colore di sfondo in modo che il colore si snoda dal bianco al blu al nero.  
  
3. Alla fine del terzo secondo, aggiunge un'animazione a un'istanza della <xref:System.Windows.Media.DrawingBrush> classe. Questa sezione dell'esempio applica un motivo a scacchiera allo sfondo.  
  
4. L'animazione ricomincia e si ripete all'infinito.  
  
> [!NOTE]
> <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>è l'unico tipo di fotogramma <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> chiave che è possibile utilizzare con la classe. Fotogrammi <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> chiave come creare improvvisi cambiamenti nei valori, cioè i cambiamenti di colore in questo esempio si verificano improvvisamente.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)

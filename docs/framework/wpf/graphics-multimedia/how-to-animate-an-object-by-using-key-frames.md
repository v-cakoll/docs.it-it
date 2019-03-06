---
title: 'Procedura: Animare un oggetto utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 1e0e464adf70aeeaecb522d328d3087ca66a530c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368558"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>Procedura: Animare un oggetto utilizzando fotogrammi chiave
In questo esempio illustra come animare un oggetto, che in questo esempio è il <xref:System.Windows.Controls.Page.Background%2A> proprietà di un <xref:System.Windows.Controls.Page> controllo, usando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> classe per animare il colore cambia per il <xref:System.Windows.Controls.Page.Background%2A> proprietà di un <xref:System.Windows.Controls.Page> controllo. L'animazione di esempio modifica di un pennello di sfondo differente a intervalli regolari. Questa animazione Usa il <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> classe per creare tre fotogrammi chiave diversi. L'animazione Usa i fotogrammi chiave nel modo seguente:  
  
1.  Alla fine del secondo prima, aggiunge un'animazione a un'istanza di <xref:System.Windows.Media.LinearGradientBrush> classe. In questa sezione dell'esempio applica una sfumatura lineare per il colore di sfondo in modo che il colore di transizione da giallo a arancione e impostato su rosso.  
  
2.  Alla fine del secondo successivo, aggiunge un'animazione a un'istanza di <xref:System.Windows.Media.RadialGradientBrush> classe. In questa sezione dell'esempio applica una sfumatura radiale per il colore di sfondo in modo che passa il colore da bianco a blu su nero.  
  
3.  Alla fine del secondo terzo, aggiunge un'animazione a un'istanza di <xref:System.Windows.Media.DrawingBrush> classe. Questa sezione dell'esempio riguarda un motivo a scacchi allo sfondo.  
  
4.  L'animazione viene avviato nuovamente e viene ripetuta all'infinito.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> è l'unico tipo di fotogramma chiave che è possibile usare con il <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> classe. Fotogrammi chiave, ad esempio <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> creano cambiamenti improvvisi nei valori, vale a dire, le modifiche di colore in questo esempio si verificano improvvisamente.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
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

---
title: "Procedura: Aggiungere un'animazione a un oggetto usando fotogrammi chiave"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: ffbe1845b634c8f94eb6a10dfa44fcf9903e0cd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933914"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>Procedura: Aggiungere un'animazione a un oggetto usando fotogrammi chiave
Questo esempio illustra come animare un oggetto, che in questo esempio è la <xref:System.Windows.Controls.Page.Background%2A> proprietà di un <xref:System.Windows.Controls.Page> controllo, usando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> la classe per aggiungere un'animazione alle modifiche <xref:System.Windows.Controls.Page.Background%2A> dei colori per <xref:System.Windows.Controls.Page> la proprietà di un controllo. L'animazione di esempio viene modificata in un pennello dello sfondo diverso a intervalli regolari. Questa animazione usa la <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> classe per creare tre fotogrammi chiave diversi. L'animazione usa i fotogrammi chiave nel modo seguente:  
  
1. Alla fine del primo secondo, aggiunge un'animazione a un'istanza della <xref:System.Windows.Media.LinearGradientBrush> classe. Questa sezione dell'esempio applica una sfumatura lineare al colore di sfondo, in modo che il colore passi da giallo a arancione a rosso.  
  
2. Alla fine del secondo successivo, aggiunge un'animazione a un'istanza della <xref:System.Windows.Media.RadialGradientBrush> classe. Questa sezione dell'esempio applica una sfumatura radiale al colore di sfondo, in modo che il colore passi da bianco a blu a nero.  
  
3. Alla fine del terzo secondo, aggiunge un'animazione a un'istanza della <xref:System.Windows.Media.DrawingBrush> classe. Questa sezione dell'esempio applica uno schema a scacchi allo sfondo.  
  
4. L'animazione inizia di nuovo e si ripete per un tempo illimitato.  
  
> [!NOTE]
> <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>è l'unico tipo di fotogramma chiave che è possibile utilizzare con <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> la classe. I fotogrammi <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> chiave come creano modifiche improvvise nei valori, ovvero le modifiche dei colori in questo esempio si verificano improvvisamente.  
  
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

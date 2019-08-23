---
title: "Procedura: Aggiungere un'animazione a una matrice usando fotogrammi chiave"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 6aa3e27cdfda7597c9b6acbf2980a2774f2b667b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963031"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Procedura: Aggiungere un'animazione a una matrice usando fotogrammi chiave
In questo esempio viene illustrato come animare <xref:System.Windows.Media.MatrixTransform.Matrix%2A> la proprietà di <xref:System.Windows.Media.MatrixTransform> un oggetto utilizzando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> la classe per aggiungere un' <xref:System.Windows.Media.MatrixTransform.Matrix%2A> animazione alla proprietà <xref:System.Windows.Media.MatrixTransform>di un oggetto. Nell'esempio viene utilizzato <xref:System.Windows.Media.MatrixTransform> l'oggetto per trasformare l'aspetto e la posizione <xref:System.Windows.Controls.Button>di un oggetto.  
  
 Questa animazione usa la <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> classe per creare due fotogrammi chiave ed esegue le operazioni seguenti:  
  
1. Anima il primo <xref:System.Windows.Media.Matrix> durante i primi 0,2 secondi. Nell'esempio vengono modificate <xref:System.Windows.Media.Matrix.M11%2A> le <xref:System.Windows.Media.Matrix.M12%2A> proprietà e di <xref:System.Windows.Media.Matrix>. Questa modifica determina l'estensione del pulsante e la distorsione. Nell'esempio vengono anche modificate <xref:System.Windows.Media.Matrix.OffsetX%2A> le <xref:System.Windows.Media.Matrix.OffsetY%2A> proprietà e in modo che il pulsante cambi la posizione.  
  
2. Aggiunge un'animazione alla <xref:System.Windows.Media.Matrix> seconda a 1,0 secondi. Il pulsante si sposta in un'altra posizione mentre il pulsante non è più inclinato o allungato.  
  
3. Ripete l'animazione per un periodo illimitato.  
  
> [!NOTE]
> I fotogrammi chiave che derivano dall' <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> oggetto creano salti improvvisi tra i valori, ovvero lo spostamento dell'animazione è Jerky.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)

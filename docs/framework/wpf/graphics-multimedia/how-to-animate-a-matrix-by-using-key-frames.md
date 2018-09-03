---
title: 'Procedura: animare una matrice utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 8f58b43a870f2c85ae4349965f586a33e2f75a2a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485850"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Procedura: animare una matrice utilizzando fotogrammi chiave
In questo esempio illustra come animare la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform> usando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform>. L'esempio Usa la <xref:System.Windows.Media.MatrixTransform> oggetto da trasformare l'aspetto e la posizione di un <xref:System.Windows.Controls.Button>.  
  
 Questa animazione Usa il <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> classe per creare due fotogrammi chiave ed esegue le seguenti operazioni:  
  
1.  Aggiunge un'animazione prima <xref:System.Windows.Media.Matrix> durante i primi secondi 0,2. Le modifiche di esempio il <xref:System.Windows.Media.Matrix.M11%2A> e <xref:System.Windows.Media.Matrix.M12%2A> delle proprietà del <xref:System.Windows.Media.Matrix>. Questa modifica fa sì che il pulsante per l'estensione e diventare asimmetrici. Nell'esempio viene modificato anche il <xref:System.Windows.Media.Matrix.OffsetX%2A> e <xref:System.Windows.Media.Matrix.OffsetY%2A> proprietà in modo che il pulsante Cambia posizione.  
  
2.  Aggiunge un'animazione secondo <xref:System.Windows.Media.Matrix> a 1,0 secondi. Il pulsante si sposta in una posizione diversa mentre il pulsante non è più inclinato o esteso.  
  
3.  Si ripete per un periodo illimitato l'animazione.  
  
> [!NOTE]
>  Fotogrammi chiave che derivano dal <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> oggetto creano salti improvvisi tra valori, vale a dire lo spostamento dell'animazione è a scatti.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>  
 <xref:System.Windows.Media.MatrixTransform>  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Procedure relative ai fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)

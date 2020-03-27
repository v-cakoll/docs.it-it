---
title: 'Procedura: animare una matrice utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344910"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Procedura: animare una matrice utilizzando fotogrammi chiave
In questo esempio viene <xref:System.Windows.Media.MatrixTransform.Matrix%2A> illustrato <xref:System.Windows.Media.MatrixTransform> come animare la proprietà di un utilizzando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene utilizzata la <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform>oggetto . Nell'esempio <xref:System.Windows.Media.MatrixTransform> viene utilizzato l'oggetto per <xref:System.Windows.Controls.Button>trasformare l'aspetto e la posizione di un oggetto .  
  
 Questa animazione <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> usa la classe per creare due fotogrammi chiave ed esegue le operazioni seguenti:This animation uses the class to create two key frames and does the following with them:  
  
1. Aggiunge un'animazione al primo <xref:System.Windows.Media.Matrix> durante i primi 0,2 secondi. Nell'esempio <xref:System.Windows.Media.Matrix.M11%2A> vengono <xref:System.Windows.Media.Matrix.M12%2A> modificate <xref:System.Windows.Media.Matrix>le proprietà e dell'oggetto . Questa modifica fa sì che il pulsante si allunghi e diventi inclinato. Nell'esempio vengono <xref:System.Windows.Media.Matrix.OffsetX%2A> <xref:System.Windows.Media.Matrix.OffsetY%2A> modificate anche le proprietà e in modo che il pulsante cambi posizione.  
  
2. Aggiunge un'animazione al secondo <xref:System.Windows.Media.Matrix> a 1,0 secondi. Il pulsante si sposta in un'altra posizione mentre il pulsante non è più inclinato o allungato.  
  
3. Ripete l'animazione all'infinito.  
  
> [!NOTE]
> I fotogrammi chiave <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> che derivano dall'oggetto creano salti improvvisi tra i valori, ovvero il movimento dell'animazione è a scatti.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)

---
title: 'Procedura: animare una matrice utilizzando fotogrammi chiave'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c8c67b5c8e179485083a40aa8a196fbee3e0fc24
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Procedura: animare una matrice utilizzando fotogrammi chiave
In questo esempio viene illustrato come animare la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform> utilizzando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> classe da cui iniziare l'animazione di <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform>. Nell'esempio viene utilizzato il <xref:System.Windows.Media.MatrixTransform> oggetto per trasformare l'aspetto e la posizione di un <xref:System.Windows.Controls.Button>.  
  
 Viene utilizzata la <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> classe per creare due fotogrammi chiave ed esegue le seguenti operazioni:  
  
1.  Aggiunge un'animazione prima <xref:System.Windows.Media.Matrix> durante i primi 0,2 secondi. Le modifiche di esempio di <xref:System.Windows.Media.Matrix.M11%2A> e <xref:System.Windows.Media.Matrix.M12%2A> le proprietà del <xref:System.Windows.Media.Matrix>. Questa modifica, il pulsante per l'estensione e diventano asimmetrica. Nell'esempio viene modificato anche il <xref:System.Windows.Media.Matrix.OffsetX%2A> e <xref:System.Windows.Media.Matrix.OffsetY%2A> proprietà in modo che il pulsante Cambia posizione.  
  
2.  Aggiunge un'animazione secondo <xref:System.Windows.Media.Matrix> a 1,0 secondi. Pulsante Sposta in un'altra posizione, mentre il pulsante non è più appropriato o estesa.  
  
3.  Ripete l'animazione per un periodo illimitato.  
  
> [!NOTE]
>  Fotogrammi chiave che derivano dal <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> oggetto creano improvvisi tra due valori, vale a dire lo spostamento dell'animazione scatti.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>  
 <xref:System.Windows.Media.MatrixTransform>  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Procedure relative ai fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)

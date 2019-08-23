---
title: 'Procedura: Applicare trasformazioni al testo'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: b749d21c1b5940d216e244393eeb3c133dc153b6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956475"
---
# <a name="how-to-apply-transforms-to-text"></a>Procedura: Applicare trasformazioni al testo
Le trasformazioni possono modificare la visualizzazione del testo nell'applicazione. Negli esempi seguenti vengono usati tipi diversi di trasformazioni di rendering per influenzare la visualizzazione del testo <xref:System.Windows.Controls.TextBlock> in un controllo.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra la rotazione del testo intorno a un punto specifico del piano x-y bidimensionale.  
  
 ![Testo ruotato con RotateTransform](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 Nell'esempio di codice seguente viene <xref:System.Windows.Media.RotateTransform> usato un oggetto per ruotare il testo. Il <xref:System.Windows.Media.RotateTransform.Angle%2A> valore 90 ruota l'elemento 90 gradi in senso orario.  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 Nell'esempio seguente la seconda riga del testo è ridimensionata del 150% lungo l'asse x, mentre la terza riga del testo è ridimensionata del 150% lungo l'asse y.  
  
 ![Testo ridimensionato con ScaleTransform](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg) 
  
 Nell'esempio di codice seguente viene <xref:System.Windows.Media.ScaleTransform> usato un oggetto per ridimensionare il testo dalle dimensioni originali.  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
> Il ridimensionamento del testo non coincide con l'aumento delle dimensioni dei caratteri del testo. Le dimensioni dei caratteri vengono calcolate in modo indipendente per fornire la migliore risoluzione a dimensioni diverse. Il testo ridimensionato mantiene invece le proporzioni del testo nelle dimensioni originali.  
  
 Nell'esempio seguente il testo è inclinato lungo l'asse x.  
  
 ![Testo inclinato con SkewTransform](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)
   
 Nell'esempio di codice seguente viene <xref:System.Windows.Media.SkewTransform> usato un oggetto per inclinare il testo. L'inclinazione, nota anche come distorsione, è una trasformazione che estende lo spazio delle coordinate in modo non uniforme. In questo esempio le due stringhe di testo sono inclinate di -30° e 30° lungo la coordinata x.  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 Nell'esempio seguente il testo è traslato, o spostato, lungo l'asse x e y.  
  
 ![Offset del testo con TranslateTransform](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 Nell'esempio di codice seguente viene <xref:System.Windows.Media.TranslateTransform> usato un oggetto per eseguire l'offset del testo. In questo esempio una copia del testo con un leggero offset sotto il testo primario crea un effetto di ombreggiatura.  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
> In <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> è disponibile un set completo di funzionalità per la fornitura di effetti ombreggiatura. Per altre informazioni, vedere [creare un testo con un'ombreggiatura](how-to-create-text-with-a-shadow.md).  
  
## <a name="see-also"></a>Vedere anche

- [Applicare animazioni al testo](how-to-apply-animations-to-text.md)

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
ms.openlocfilehash: 46a57364e0c18cc4c9fe7884642cd0b718c20f31
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776962"
---
# <a name="how-to-apply-transforms-to-text"></a>Procedura: Applicare trasformazioni al testo
Le trasformazioni possono modificare la visualizzazione del testo nell'applicazione. Gli esempi seguenti usano diversi tipi di trasformazioni di rendering per modificare la visualizzazione di testo in un <xref:System.Windows.Controls.TextBlock> controllo.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra la rotazione del testo intorno a un punto specifico del piano x-y bidimensionale.  
  
 ![Testo ruotato con RotateTransform](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 Il codice seguente viene illustrato come utilizzare un <xref:System.Windows.Media.RotateTransform> per ruotare il testo. Un <xref:System.Windows.Media.RotateTransform.Angle%2A> valore pari a 90 Ruota l'elemento di 90 gradi in senso orario.  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 Nell'esempio seguente la seconda riga del testo è ridimensionata del 150% lungo l'asse x, mentre la terza riga del testo è ridimensionata del 150% lungo l'asse y.  
  
 ![Testo ridimensionato con ScaleTransform](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg) 
  
 Il codice seguente viene illustrato come utilizzare un <xref:System.Windows.Media.ScaleTransform> per ridimensionare il testo rispetto alle dimensioni originali.  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  Il ridimensionamento del testo non coincide con l'aumento delle dimensioni dei caratteri del testo. Le dimensioni dei caratteri vengono calcolate in modo indipendente per fornire la migliore risoluzione a dimensioni diverse. Il testo ridimensionato mantiene invece le proporzioni del testo nelle dimensioni originali.  
  
 Nell'esempio seguente il testo è inclinato lungo l'asse x.  
  
 ![Testo inclinato con SkewTransform](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)
   
 Il codice seguente viene illustrato come utilizzare un <xref:System.Windows.Media.SkewTransform> per inclinare il testo. L'inclinazione, nota anche come distorsione, è una trasformazione che estende lo spazio delle coordinate in modo non uniforme. In questo esempio le due stringhe di testo sono inclinate di -30° e 30° lungo la coordinata x.  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 Nell'esempio seguente il testo è traslato, o spostato, lungo l'asse x e y.  
  
 ![Offset del testo con TranslateTransform](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 Il codice seguente viene illustrato come utilizzare un <xref:System.Windows.Media.TranslateTransform> per spostare il testo. In questo esempio una copia del testo con un leggero offset sotto il testo primario crea un effetto di ombreggiatura.  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  Il <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> offre un'ampia gamma di funzionalità per ottenere effetti di ombreggiatura. Per altre informazioni, vedere [creare testo con ombreggiatura](how-to-create-text-with-a-shadow.md).  
  
## <a name="see-also"></a>Vedere anche

- [Applicare animazioni al testo](how-to-apply-animations-to-text.md)

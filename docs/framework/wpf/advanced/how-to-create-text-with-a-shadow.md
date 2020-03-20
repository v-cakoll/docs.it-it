---
title: 'Procedura: Creare testo con ombreggiatura'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: c3e8135372ce4a092552c812cd971cb70bc49bf3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186853"
---
# <a name="how-to-create-text-with-a-shadow"></a>Procedura: Creare testo con ombreggiatura
Gli esempi inclusi in questa sezione mostrano come creare un effetto di ombreggiatura per il testo visualizzato.  
  
## <a name="example"></a>Esempio  
 L'oggetto <xref:System.Windows.Media.Effects.DropShadowEffect> consente di creare una varietà [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] di effetti di ombreggiatura per gli oggetti. Nell'esempio seguente viene illustrato un effetto di ombreggiatura applicato al testo. Poiché in questo caso l'ombreggiatura è sfumata, il colore dell'ombreggiatura sarà sfocato.  
  
 ![Ombreggiatura del testo con &#61; 0,25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg)
  
 È possibile controllare la larghezza di <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> un'ombreggiatura impostando la proprietà . Il valore `4.0` di indica una larghezza di ombreggiatura di 4 pixel. È possibile controllare la morbidezza, o sfocatura, di un'ombra modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> proprietà. Il valore `0.0` di indica nessuna sfocatura. Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura sfumata.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> Questi effetti di ombreggiatura [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] non passano attraverso la pipeline di rendering del testo. Di conseguenza, ClearType è disabilitato quando si usano questi effetti.  
  
 Nell'esempio seguente viene illustrato un effetto di ombreggiatura piena applicato al testo. In questo caso, l'ombreggiatura non è sfocata.  
  
 ![Ombreggiatura del testo con morbidezza &#61; 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg)
  
 È possibile creare un'ombreggiatura rigida impostando la <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> proprietà su `0.0`, che indica che non viene utilizzata alcuna sfocatura. È possibile controllare la direzione <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> dell'ombreggiatura modificando la proprietà . Impostare il valore direzionale di `0` `360`questa proprietà su un grado compreso tra e . Nella figura seguente vengono illustrati <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> i valori direzionali dell'impostazione della proprietà.  
  
 ![Impostazione del grado DropShadow dell'ombreggiatura](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura piena.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>Uso di un effetto di sfocatura  
 Un <xref:System.Windows.Media.Effects.BlurBitmapEffect> può essere utilizzato per creare un effetto simile a un'ombreggiatura che può essere posizionato dietro un oggetto di testo. Un effetto bitmap di sfocatura applicato al testo consente di sfocare il testo in tutte le direzioni in modo uniforme.  
  
 L'esempio seguente illustra un effetto di sfocatura applicato al testo.  
  
 ![Ombreggiatura del testo con BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 Nell'esempio di codice seguente viene illustrato come creare un effetto di sfocatura.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>Uso di una trasformazione di traslazione  
 Un <xref:System.Windows.Media.TranslateTransform> può essere utilizzato per creare un effetto simile a un'ombreggiatura che può essere posizionato dietro un oggetto di testo.  
  
 Nell'esempio di <xref:System.Windows.Media.TranslateTransform> codice riportato di seguito viene illustrato come utilizzare un oggetto per eseguire l'offset del testo. In questo esempio una copia del testo con un leggero offset sotto il testo primario crea un effetto di ombreggiatura.  
  
 ![Ombreggiatura del testo con TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)
  
 Nell'esempio di codice seguente viene illustrato come creare una trasformazione per un effetto di ombreggiatura.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]

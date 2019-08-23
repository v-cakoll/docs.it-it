---
title: "Procedura: Creare testo con un'ombreggiatura"
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 0fe64e4e9e7aadbd30a38743647251f9fa49ba95
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960435"
---
# <a name="how-to-create-text-with-a-shadow"></a>Procedura: Creare testo con un'ombreggiatura
Gli esempi inclusi in questa sezione mostrano come creare un effetto di ombreggiatura per il testo visualizzato.  
  
## <a name="example"></a>Esempio  
 L' <xref:System.Windows.Media.Effects.DropShadowEffect> oggetto consente di creare un'ampia gamma di effetti ombreggiatura per [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] gli oggetti. Nell'esempio seguente viene illustrato un effetto di ombreggiatura applicato al testo. Poiché in questo caso l'ombreggiatura è sfumata, il colore dell'ombreggiatura sarà sfocato.  
  
 ![Ombreggiatura del testo con &#61; morbidezza 0,25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg) 
  
 È possibile controllare la larghezza di un'ombreggiatura impostando <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> la proprietà. Il valore `4.0` indica una larghezza ombreggiata di 4 pixel. È possibile controllare la morbidezza o la sfocatura di un'ombreggiatura modificando <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> la proprietà. Un valore `0.0` indica che non è presente alcuna sfocatura. Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura sfumata.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> Questi effetti di ombreggiatura non passano attraverso [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] la pipeline di rendering del testo. Di conseguenza, ClearType è disabilitato quando si usano questi effetti.  
  
 Nell'esempio seguente viene illustrato un effetto di ombreggiatura piena applicato al testo. In questo caso, l'ombreggiatura non è sfocata.  
  
 ![Ombreggiatura del testo con &#61; morbidezza 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg) 
  
 È possibile creare un'ombreggiatura rigida impostando <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> la `0.0`proprietà su, che indica che non viene utilizzata alcuna sfocatura. È possibile controllare la direzione dell'ombreggiatura modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> proprietà. Impostare il valore direzionale di questa proprietà su un grado compreso `0` tra `360`e. Nella figura seguente vengono mostrati i valori direzionali <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> dell'impostazione della proprietà.  
  
 ![Impostazione del grado DropShadow dell'ombreggiatura](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura piena.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>Uso di un effetto di sfocatura  
 Un <xref:System.Windows.Media.Effects.BlurBitmapEffect> oggetto può essere usato per creare un effetto simile all'ombreggiatura che può essere posizionato dietro un oggetto di testo. Un effetto bitmap di sfocatura applicato al testo consente di sfocare il testo in tutte le direzioni in modo uniforme.  
  
 L'esempio seguente illustra un effetto di sfocatura applicato al testo.  
  
 ![Ombreggiatura del testo con BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 Nell'esempio di codice seguente viene illustrato come creare un effetto di sfocatura.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>Uso di una trasformazione di traslazione  
 Un <xref:System.Windows.Media.TranslateTransform> oggetto può essere usato per creare un effetto simile all'ombreggiatura che può essere posizionato dietro un oggetto di testo.  
  
 Nell'esempio di codice seguente viene <xref:System.Windows.Media.TranslateTransform> usato un oggetto per eseguire l'offset del testo. In questo esempio una copia del testo con un leggero offset sotto il testo primario crea un effetto di ombreggiatura.  
  
 ![Ombreggiatura del testo con TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)    
  
 Nell'esempio di codice seguente viene illustrato come creare una trasformazione per un effetto di ombreggiatura.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]

---
title: "Procedura: Creare un testo con un'ombreggiatura"
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 4d200aa980e8f2e6d22291669dfb07db54a5f0c0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370676"
---
# <a name="how-to-create-text-with-a-shadow"></a>Procedura: Creare un testo con un'ombreggiatura
Gli esempi inclusi in questa sezione mostrano come creare un effetto di ombreggiatura per il testo visualizzato.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Media.Effects.DropShadowEffect> oggetto consente di creare una varietà di effetti di ombreggiatura per [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] oggetti. Nell'esempio seguente viene illustrato un effetto di ombreggiatura applicato al testo. Poiché in questo caso l'ombreggiatura è sfumata, il colore dell'ombreggiatura sarà sfocato.  
  
 ![Ombreggiatura del testo con Softness &#61; 0,25](./media/shadowtext01.jpg "ShadowText01")  
Esempio di testo con un'ombreggiatura sfumata  
  
 È possibile controllare la larghezza dell'ombreggiatura impostando il <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> proprietà. Un valore di `4.0` indica una larghezza dell'ombreggiatura di 4 pixel. È possibile controllare la sfumatura, o sfocatura, di un'ombreggiatura modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> proprietà. Un valore di `0.0` non indica alcuna sfocatura. Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura sfumata.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  Questi effetti di ombreggiatura non esamina il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] pipeline di rendering del testo. Di conseguenza, ClearType è disabilitato quando si usano questi effetti.  
  
 Nell'esempio seguente viene illustrato un effetto di ombreggiatura piena applicato al testo. In questo caso, l'ombreggiatura non è sfocata.  
  
 ![Ombreggiatura del testo con Softness &#61; 0](./media/shadowtext02.jpg "ShadowText02")  
Esempio di testo con un'ombreggiatura piena  
  
 È possibile creare un'ombreggiatura piena impostando il <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> proprietà `0.0`, che indica che viene usata alcuna sfocatura. È possibile controllare la direzione dell'ombreggiatura modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> proprietà. Impostare il valore direzionale di questa proprietà su un grado compreso tra `0` e `360`. La figura seguente mostra i valori direzionali del <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> l'impostazione della proprietà.  
  
 ![Impostazione del grado DropShadow dell'ombreggiatura](./media/shadowtext08.png "ShadowText08")  
Diagramma di direzione DropShadow  
  
 Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura piena.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>Uso di un effetto di sfocatura  
 Oggetto <xref:System.Windows.Media.Effects.BlurBitmapEffect> può essere utilizzato per creare un effetto simile all'ombreggiatura che può essere posizionato dietro un oggetto testo. Un effetto bitmap di sfocatura applicato al testo consente di sfocare il testo in tutte le direzioni in modo uniforme.  
  
 L'esempio seguente illustra un effetto di sfocatura applicato al testo.  
  
 ![Ombreggiatura del testo con BlurBitmapEffect](./media/shadowtext06.jpg "ShadowText06")  
Esempio di testo con un effetto di sfocatura  
  
 Nell'esempio di codice seguente viene illustrato come creare un effetto di sfocatura.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>Uso di una trasformazione di traslazione  
 Oggetto <xref:System.Windows.Media.TranslateTransform> può essere utilizzato per creare un effetto simile all'ombreggiatura che può essere posizionato dietro un oggetto testo.  
  
 Il codice seguente viene illustrato come utilizzare un <xref:System.Windows.Media.TranslateTransform> per spostare il testo. In questo esempio una copia del testo con un leggero offset sotto il testo primario crea un effetto di ombreggiatura.  
  
 ![Ombreggiatura del testo con TranslateTransform](./media/shadowtext07.jpg "ShadowText07")  
Esempio di testo che usa una trasformazione per un effetto di ombreggiatura  
  
 Nell'esempio di codice seguente viene illustrato come creare una trasformazione per un effetto di ombreggiatura.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]

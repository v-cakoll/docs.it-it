---
title: 'Procedura: Creare testo con ombreggiatura'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31bbc3da54c10304e52f93d38365a8d9ed005505
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-text-with-a-shadow"></a>Procedura: Creare testo con ombreggiatura
Gli esempi inclusi in questa sezione mostrano come creare un effetto di ombreggiatura per il testo visualizzato.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Media.Effects.DropShadowEffect> oggetto consente di creare una varietà di effetti di ombreggiatura per [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] oggetti. Nell'esempio seguente viene illustrato un effetto di ombreggiatura applicato al testo. Poiché in questo caso l'ombreggiatura è sfumata, il colore dell'ombreggiatura sarà sfocato.  
  
 ![Ombreggiatura del testo con Softness &#61; 0,25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")  
Esempio di testo con un'ombreggiatura sfumata  
  
 È possibile controllare la larghezza dell'ombreggiatura impostando il <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> proprietà. Il valore `4.0` indica la larghezza dell'ombreggiatura di 4 pixel. È possibile controllare la sfumatura, o sfocatura, di un'ombreggiatura modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> proprietà. Il valore `0.0` non indica nessuna sfocatura. Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura sfumata.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  Questi effetti di ombreggiatura passa attraverso il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] pipeline di rendering del testo. Di conseguenza, ClearType è disabilitato quando si usano questi effetti.  
  
 Nell'esempio seguente viene illustrato un effetto di ombreggiatura piena applicato al testo. In questo caso, l'ombreggiatura non è sfocata.  
  
 ![Ombreggiatura del testo con Softness &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")  
Esempio di testo con un'ombreggiatura piena  
  
 È possibile creare un'ombreggiatura impostando il <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> proprietà `0.0`, che indica che è utilizzata nessuna sfocatura. È possibile controllare la direzione dell'ombreggiatura modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> proprietà. Impostare il valore direzionale di questa proprietà su un livello tra `0` e `360`. La figura seguente mostra i valori di direzionale il <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> l'impostazione della proprietà.  
  
 ![Impostazione del grado DropShadow dell'ombreggiatura](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")  
Diagramma di direzione DropShadow  
  
 Nell'esempio di codice seguente viene illustrato come creare un'ombreggiatura piena.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>Uso di un effetto di sfocatura  
 Oggetto <xref:System.Windows.Media.Effects.BlurBitmapEffect> può essere utilizzato per creare un effetto di ombreggiatura simile che può essere posizionato dietro un oggetto testo. Un effetto bitmap di sfocatura applicato al testo consente di sfocare il testo in tutte le direzioni in modo uniforme.  
  
 L'esempio seguente illustra un effetto di sfocatura applicato al testo.  
  
 ![Ombreggiatura del testo con BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")  
Esempio di testo con un effetto di sfocatura  
  
 Nell'esempio di codice seguente viene illustrato come creare un effetto di sfocatura.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>Uso di una trasformazione di traslazione  
 Oggetto <xref:System.Windows.Media.TranslateTransform> può essere utilizzato per creare un effetto di ombreggiatura simile che può essere posizionato dietro un oggetto testo.  
  
 Nell'esempio di codice viene illustrato come utilizzare un <xref:System.Windows.Media.TranslateTransform> per spostare il testo. In questo esempio una copia del testo con un leggero offset sotto il testo primario crea un effetto di ombreggiatura.  
  
 ![Ombreggiatura del testo con TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")  
Esempio di testo che usa una trasformazione per un effetto di ombreggiatura  
  
 Nell'esempio di codice seguente viene illustrato come creare una trasformazione per un effetto di ombreggiatura.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]

---
title: Cenni preliminari sugli effetti bitmap
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 4a5e73f21d4ce4988f56c139d13038dca902b5b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186999"
---
# <a name="bitmap-effects-overview"></a>Cenni preliminari sugli effetti bitmap
Gli effetti bitmap consentono a progettisti e sviluppatori di applicare effetti visivi al contenuto di Windows Presentation Foundation (WPF) di cui è stato eseguito il rendering. Ad esempio, gli effetti bitmap <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> consentono di applicare facilmente un effetto o un effetto di sfocatura a un'immagine o a un pulsante.  
  
> [!IMPORTANT]
> In .NET Framework 4 o <xref:System.Windows.Media.Effects.BitmapEffect> versioni successive, la classe è obsoleta. Se si tenta <xref:System.Windows.Media.Effects.BitmapEffect> di utilizzare la classe, si otterrà un'eccezione obsoleta. L'alternativa non obsoleta <xref:System.Windows.Media.Effects.BitmapEffect> alla <xref:System.Windows.Media.Effects.Effect> classe è la classe . Nella maggior parte <xref:System.Windows.Media.Effects.Effect> dei casi, la classe è significativamente più veloce.  

<a name="wpf_effects"></a>
## <a name="wpf-bitmap-effects"></a>Effetti bitmap WPF  
 Gli effetti<xref:System.Windows.Media.Effects.BitmapEffect> bitmap (oggetto) sono semplici operazioni di elaborazione dei pixel. Un effetto bitmap <xref:System.Windows.Media.Imaging.BitmapSource> prende un come <xref:System.Windows.Media.Imaging.BitmapSource> input e produce un nuovo dopo aver applicato l'effetto, ad esempio una sfocatura o un'ombra esterna. Ogni effetto bitmap espone proprietà che possono controllare <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> <xref:System.Windows.Media.Effects.BlurBitmapEffect>le proprietà di filtro, ad esempio di .  
  
 In caso speciale, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]in , gli effetti <xref:System.Windows.Media.Visual> possono essere impostati come proprietà su oggetti attivi, ad esempio un <xref:System.Windows.Controls.Button> oggetto o <xref:System.Windows.Controls.TextBox>. L'elaborazione dei pixel viene applicata e sottoposta a rendering in fase di esecuzione. In questo caso, al momento <xref:System.Windows.Media.Visual> del rendering, <xref:System.Windows.Media.Imaging.BitmapSource> un oggetto viene convertito <xref:System.Windows.Media.Effects.BitmapEffect>automaticamente nell'equivalente e viene alimentato come input nel file . L'output sostituisce il <xref:System.Windows.Media.Visual> comportamento di rendering predefinito dell'oggetto. Questo è <xref:System.Windows.Media.Effects.BitmapEffect> il motivo per cui gli oggetti impongono agli oggetti visivi di eseguire il rendering nel software solo, ad esempio nessuna accelerazione hardware sugli oggetti visivi quando vengono applicati gli effetti.  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect>simula un oggetto che appare fuori fuoco.  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>crea un alone di colore intorno al perimetro di un oggetto.  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>crea un'ombra dietro un oggetto.  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect>crea uno svelo che solleva la superficie di un'immagine in base a una curva specificata.  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect>crea una mappatura <xref:System.Windows.Media.Visual> di rilievo di un per dare l'impressione di profondità e texture da una fonte di luce artificiale.  
  
> [!NOTE]
> Gli effetti bitmap WPFWPF vengono sottoposti a rendering in modalità software. e anche qualsiasi oggetto che applica un effetto verrà sottoposto a rendering in modalità software. Le prestazioni diminuiscono in modo più sensibile quando si usano effetti bitmap su elementi visivi di grandi dimensioni o quando si animano le proprietà di un effetto bitmap. Ciò non significa che gli effetti bitmap non debbano mai essere usati in questo modo, ma che è necessario prestare attenzione ed eseguire numerosi test affinché gli utenti acquisiscano l'esperienza necessaria.  
  
> [!NOTE]
> Gli effetti bitmap WPFWPF non supportano l'esecuzione di attendibilità parziale. Per l'uso degli effetti bitmap, un'applicazione deve disporre di autorizzazioni di attendibilità completa.  
  
<a name="applyeffects"></a>
## <a name="how-to-apply-an-effect"></a>Come applicare un effetto  
 <xref:System.Windows.Media.Effects.BitmapEffect>è una <xref:System.Windows.Media.Visual>proprietà su . Pertanto, applicare effetti a oggetti <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Image>visivi, ad esempio un oggetto , <xref:System.Windows.Media.DrawingVisual>, o <xref:System.Windows.UIElement>, è semplice come impostare una proprietà . <xref:System.Windows.UIElement.BitmapEffect%2A>può essere impostato <xref:System.Windows.Media.Effects.BitmapEffect> su un singolo oggetto o più <xref:System.Windows.Media.Effects.BitmapEffectGroup> effetti possono essere concatenati utilizzando l'oggetto.  
  
 Nell'esempio riportato di <xref:System.Windows.Media.Effects.BitmapEffect> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]seguito viene illustrato come applicare un oggetto in .  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 Nell'esempio seguente viene <xref:System.Windows.Media.Effects.BitmapEffect> illustrato come applicare un nel codice.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> Quando <xref:System.Windows.Media.Effects.BitmapEffect> un oggetto viene applicato a <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Canvas>un contenitore di layout, ad esempio o , l'effetto viene applicato alla struttura ad albero visuale dell'elemento o dell'oggetto visivo, inclusi tutti i relativi elementi figlio.  
  
<a name="customeffects"></a>
## <a name="creating-custom-effects"></a>Creazione di effetti personalizzati  
 WPFWPF fornisce anche interfacce non gestite per creare effetti personalizzati che possono essere usati nelle applicazioni WPFWPF gestite. Per materiale di riferimento aggiuntivo per la creazione di effetti bitmap personalizzati, vedere la documentazione [Unmanaged WPF Bitmap Effect](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh) (Effetto bitmap WPF non gestito).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [Unmanaged WPF Bitmap Effect](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh) (Effetto bitmap WPF non gestito)
- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
- [Sicurezza](../security-wpf.md)
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
- [Grafica 2D e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)

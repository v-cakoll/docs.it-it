---
title: Cenni preliminari sugli effetti bitmap
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: f2fa42d5d63cad6a71efd259416dad3416bf2d72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935296"
---
# <a name="bitmap-effects-overview"></a>Cenni preliminari sugli effetti bitmap
Gli effetti bitmap consentono alle finestre di progettazione e agli sviluppatori di applicare effetti visivi al contenuto del Windows Presentation Foundation di rendering (WPF). Gli effetti bitmap, ad esempio, consentono di applicare facilmente <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> un effetto o un effetto di sfocatura a un'immagine o a un pulsante.  
  
> [!IMPORTANT]
> In .NET Framework 4 o versione successiva, la <xref:System.Windows.Media.Effects.BitmapEffect> classe è obsoleta. Se si tenta di utilizzare la <xref:System.Windows.Media.Effects.BitmapEffect> classe, si otterrà un'eccezione obsoleta. L'alternativa non obsoleta alla <xref:System.Windows.Media.Effects.BitmapEffect> classe è la <xref:System.Windows.Media.Effects.Effect> classe. Nella maggior parte dei casi <xref:System.Windows.Media.Effects.Effect> , la classe è notevolmente più veloce.  

<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>Effetti bitmap WPF  
 Gli effetti bitmap<xref:System.Windows.Media.Effects.BitmapEffect> (oggetto) sono semplici operazioni di elaborazione di pixel. Un effetto bitmap accetta <xref:System.Windows.Media.Imaging.BitmapSource> come input e produce un nuovo <xref:System.Windows.Media.Imaging.BitmapSource> oggetto dopo l'applicazione dell'effetto, ad esempio un'ombreggiatura o una sfumatura. Ogni effetto bitmap espone proprietà che consentono <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> di controllare le proprietà di <xref:System.Windows.Media.Effects.BlurBitmapEffect>filtro, ad esempio.  
  
 Come caso speciale [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], in gli effetti possono essere impostati come proprietà su <xref:System.Windows.Controls.Button> oggetti attivi <xref:System.Windows.Media.Visual> , ad esempio o <xref:System.Windows.Controls.TextBox>. L'elaborazione dei pixel viene applicata e sottoposta a rendering in fase di esecuzione. In questo caso, al momento del rendering, un <xref:System.Windows.Media.Visual> viene convertito automaticamente <xref:System.Windows.Media.Imaging.BitmapSource> nell'equivalente e viene <xref:System.Windows.Media.Effects.BitmapEffect>alimentato come input per. L'output sostituisce il <xref:System.Windows.Media.Visual> comportamento di rendering predefinito dell'oggetto. Questo è il <xref:System.Windows.Media.Effects.BitmapEffect> motivo per cui gli oggetti forzano il rendering degli oggetti visivi nel software solo, ovvero nessuna accelerazione hardware sugli oggetti visivi quando vengono applicati gli effetti.  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect>simula un oggetto che risulta non attivo.  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>Crea un alone di colore intorno al perimetro di un oggetto.  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>Crea un'ombreggiatura dietro un oggetto.  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect>Crea una smussatura che solleva la superficie di un'immagine in base a una curva specificata.  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect>Crea un bump mapping di un <xref:System.Windows.Media.Visual> oggetto per dare l'impressione di profondità e trama da una sorgente di luce artificiale.  
  
> [!NOTE]
> Gli effetti bitmap [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] vengono sottoposti a rendering in modalità software e anche qualsiasi oggetto che applica un effetto verrà sottoposto a rendering in modalità software. Le prestazioni diminuiscono in modo più sensibile quando si usano effetti bitmap su elementi visivi di grandi dimensioni o quando si animano le proprietà di un effetto bitmap. Ciò non significa che gli effetti bitmap non debbano mai essere usati in questo modo, ma che è necessario prestare attenzione ed eseguire numerosi test affinché gli utenti acquisiscano l'esperienza necessaria.  
  
> [!NOTE]
> Gli effetti bitmap [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] non supportano l'esecuzione in situazioni di attendibilità parziale. Per l'uso degli effetti bitmap, un'applicazione deve disporre di autorizzazioni di attendibilità completa.  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>Come applicare un effetto  
 <xref:System.Windows.Media.Effects.BitmapEffect>è una proprietà in <xref:System.Windows.Media.Visual>. Per applicare gli effetti agli oggetti visivi, ad <xref:System.Windows.Controls.Button>esempio <xref:System.Windows.Controls.Image> <xref:System.Windows.Media.DrawingVisual>,, o <xref:System.Windows.UIElement>, è quindi sufficiente impostare una proprietà. <xref:System.Windows.UIElement.BitmapEffect%2A>può essere impostato su un singolo <xref:System.Windows.Media.Effects.BitmapEffect> oggetto o più effetti possono essere concatenati tramite l' <xref:System.Windows.Media.Effects.BitmapEffectGroup> oggetto.  
  
 Nell'esempio seguente viene illustrato come applicare un <xref:System.Windows.Media.Effects.BitmapEffect> oggetto [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]in.  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 Nell'esempio seguente viene illustrato come applicare un <xref:System.Windows.Media.Effects.BitmapEffect> oggetto nel codice.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> Quando un <xref:System.Windows.Media.Effects.BitmapEffect> oggetto viene applicato a un contenitore di layout, <xref:System.Windows.Controls.DockPanel> ad <xref:System.Windows.Controls.Canvas>esempio o, l'effetto viene applicato alla struttura ad albero visuale dell'elemento o dell'oggetto visivo, inclusi tutti i relativi elementi figlio.  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>Creazione di effetti personalizzati  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sono disponibili anche interfacce non gestite per creare effetti personalizzati da usare nelle applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] non gestite. Per materiale di riferimento aggiuntivo per la creazione di effetti bitmap personalizzati, vedere la documentazione [Unmanaged WPF Bitmap Effect](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh) (Effetto bitmap WPF non gestito).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [Effetto bitmap WPF non gestito](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
- [Sicurezza](../security-wpf.md)
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
- [Grafica bidimensionale e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)

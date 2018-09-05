---
title: Cenni preliminari sugli effetti bitmap
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 97b878621d5aa1860cd955755d9bbc344b95b993
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43724243"
---
# <a name="bitmap-effects-overview"></a>Cenni preliminari sugli effetti bitmap
Gli effetti bitmap consentono a progettisti e agli sviluppatori di applicare effetti visivi al rendering del contenuto Windows Presentation Foundation (WPF). Ad esempio, gli effetti bitmap consentono di applicare facilmente un <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> effetto o un effetto sfocatura a un'immagine o un pulsante.  
  
> [!IMPORTANT]
>  Nel [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] o versioni successive, il <xref:System.Windows.Media.Effects.BitmapEffect> classe è obsoleta. Se si prova a usare il <xref:System.Windows.Media.Effects.BitmapEffect> (classe), si otterrà un'eccezione obsoleta. L'alternativa non obsoleta per le <xref:System.Windows.Media.Effects.BitmapEffect> classe è il <xref:System.Windows.Media.Effects.Effect> classe. Nella maggior parte dei casi, il <xref:System.Windows.Media.Effects.Effect> classe è notevolmente più veloce.  
  
  
  
<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>Effetti bitmap WPF  
 Effetti bitmap (<xref:System.Windows.Media.Effects.BitmapEffect> oggetto) sono i pixel semplici operazioni di elaborazione. Un effetto bitmap accetta un <xref:System.Windows.Media.Imaging.BitmapSource> come input e produce un nuovo oggetto <xref:System.Windows.Media.Imaging.BitmapSource> dopo aver applicato l'effetto, ad esempio un' sfocatura o un'ombreggiatura. Ogni effetto bitmap espone proprietà che possono controllare le proprietà di filtro, ad esempio <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> di <xref:System.Windows.Media.Effects.BlurBitmapEffect>.  
  
 Un caso speciale, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], gli effetti possono nelze nastavit come proprietà in tempo reale <xref:System.Windows.Media.Visual> oggetti, ad esempio un <xref:System.Windows.Controls.Button> o <xref:System.Windows.Controls.TextBox>. L'elaborazione dei pixel viene applicata e sottoposta a rendering in fase di esecuzione. In questo caso, al momento del rendering, un <xref:System.Windows.Media.Visual> viene convertito automaticamente nel relativo <xref:System.Windows.Media.Imaging.BitmapSource> equivalente e inserito come input per il <xref:System.Windows.Media.Effects.BitmapEffect>. L'output sostituisce il <xref:System.Windows.Media.Visual> comportamento di rendering predefinito dell'oggetto. È per questo motivo <xref:System.Windows.Media.Effects.BitmapEffect> oggetti forzare gli oggetti visivi per il rendering software solo, ovvero senza accelerazione hardware sugli oggetti visivi quando vengono applicati gli effetti.  
  
-   <xref:System.Windows.Media.Effects.BlurBitmapEffect> Consente di simulare un oggetto visualizzato out-di-lo stato attivo.  
  
-   <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> Crea un alone di colore attorno al perimetro di un oggetto.  
  
-   <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> Consente di creare un'ombreggiatura dietro a un oggetto.  
  
-   <xref:System.Windows.Media.Effects.BevelBitmapEffect> Crea una smussatura che solleva la superficie di un'immagine in base a una curva specificata.  
  
-   <xref:System.Windows.Media.Effects.EmbossBitmapEffect> Crea un bump mapping di un <xref:System.Windows.Media.Visual> per dare l'impressione di profondità e trama da una sorgente di luce artificiale.  
  
> [!NOTE]
>  Gli effetti bitmap [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] vengono sottoposti a rendering in modalità software e anche qualsiasi oggetto che applica un effetto verrà sottoposto a rendering in modalità software. Le prestazioni diminuiscono in modo più sensibile quando si usano effetti bitmap su elementi visivi di grandi dimensioni o quando si animano le proprietà di un effetto bitmap. Ciò non significa che gli effetti bitmap non debbano mai essere usati in questo modo, ma che è necessario prestare attenzione ed eseguire numerosi test affinché gli utenti acquisiscano l'esperienza necessaria.  
  
> [!NOTE]
>  Gli effetti bitmap [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] non supportano l'esecuzione in situazioni di attendibilità parziale. Per l'uso degli effetti bitmap, un'applicazione deve disporre di autorizzazioni di attendibilità completa.  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>Come applicare un effetto  
 <xref:System.Windows.Media.Effects.BitmapEffect> è una proprietà in <xref:System.Windows.Media.Visual>. Pertanto, l'applicazione di effetti agli oggetti visivi, ad esempio un <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>, o <xref:System.Windows.UIElement>, è facile come impostare una proprietà. <xref:System.Windows.UIElement.BitmapEffect%2A> può essere impostato su un singolo <xref:System.Windows.Media.Effects.BitmapEffect> oggetto o più effetti possano essere concatenati usando il <xref:System.Windows.Media.Effects.BitmapEffectGroup> oggetto.  
  
 Nell'esempio seguente viene illustrato come applicare una <xref:System.Windows.Media.Effects.BitmapEffect> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 Nell'esempio seguente viene illustrato come applicare un <xref:System.Windows.Media.Effects.BitmapEffect> nel codice.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  Quando un <xref:System.Windows.Media.Effects.BitmapEffect> viene applicato a un contenitore di layout, ad esempio <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.Canvas>, l'effetto viene applicato per la struttura ad albero visuale dell'elemento o oggetto visivo, inclusi tutti i relativi elementi figlio.  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>Creazione di effetti personalizzati  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sono disponibili anche interfacce non gestite per creare effetti personalizzati da usare nelle applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] non gestite. Per materiale di riferimento aggiuntivo per la creazione di effetti bitmap personalizzati, vedere la documentazione [Unmanaged WPF Bitmap Effect](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh) (Effetto bitmap WPF non gestito).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Effects.BitmapEffectGroup>  
 <xref:System.Windows.Media.Effects.BitmapEffectInput>  
 <xref:System.Windows.Media.Effects.BitmapEffectCollection>  
 [Effetto Bitmap WPF non gestito](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)  
 [Cenni preliminari sulla creazione dell'immagine](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Sicurezza](../../../../docs/framework/wpf/security-wpf.md)  
 [Cenni preliminari sul rendering della grafica WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Grafica bidimensionale e creazione di immagini](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)

---
title: Cenni preliminari sugli effetti bitmap
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 4a5c304363efe7d0e9bd9e14ff916f8d852ab3a8
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636016"
---
# <a name="bitmap-effects-overview"></a>Cenni preliminari sugli effetti bitmap
Gli effetti bitmap consentono alle finestre di progettazione e agli sviluppatori di applicare effetti visivi al contenuto del Windows Presentation Foundation di rendering (WPF). Gli effetti bitmap consentono, ad esempio, di applicare facilmente un effetto <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> o un effetto di sfocatura a un'immagine o a un pulsante.  
  
> [!IMPORTANT]
> In .NET Framework 4 o versione successiva la classe <xref:System.Windows.Media.Effects.BitmapEffect> è obsoleta. Se si tenta di utilizzare la classe <xref:System.Windows.Media.Effects.BitmapEffect>, si otterrà un'eccezione obsoleta. L'alternativa non obsoleta alla classe <xref:System.Windows.Media.Effects.BitmapEffect> è la classe <xref:System.Windows.Media.Effects.Effect>. Nella maggior parte dei casi, la classe <xref:System.Windows.Media.Effects.Effect> è notevolmente più veloce.  

<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>Effetti bitmap WPF  
 Gli effetti bitmap (oggetto<xref:System.Windows.Media.Effects.BitmapEffect>) sono semplici operazioni di elaborazione di pixel. Un effetto bitmap accetta un <xref:System.Windows.Media.Imaging.BitmapSource> come input e produce una nuova <xref:System.Windows.Media.Imaging.BitmapSource> dopo aver applicato l'effetto, ad esempio un'ombreggiatura o una sfumatura. Ogni effetto bitmap espone proprietà che consentono di controllare le proprietà di filtro, ad esempio <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> di <xref:System.Windows.Media.Effects.BlurBitmapEffect>.  
  
 Come caso speciale, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]gli effetti possono essere impostati come proprietà sugli oggetti Live <xref:System.Windows.Media.Visual>, ad esempio un <xref:System.Windows.Controls.Button> o <xref:System.Windows.Controls.TextBox>. L'elaborazione dei pixel viene applicata e sottoposta a rendering in fase di esecuzione. In questo caso, al momento del rendering, un <xref:System.Windows.Media.Visual> viene convertito automaticamente nel <xref:System.Windows.Media.Imaging.BitmapSource> equivalente e viene alimentato come input per il <xref:System.Windows.Media.Effects.BitmapEffect>. L'output sostituisce il comportamento di rendering predefinito dell'oggetto <xref:System.Windows.Media.Visual>. Questo è il motivo per cui <xref:System.Windows.Media.Effects.BitmapEffect> oggetti forzano il rendering degli oggetti visivi nel software solo, ad esempio l'accelerazione hardware sugli oggetti visivi quando vengono applicati gli effetti.  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect> simula un oggetto che risulta non attivo.  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> crea un alone di colore intorno al perimetro di un oggetto.  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> crea un'ombreggiatura dietro un oggetto.  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect> crea una smussatura che solleva la superficie di un'immagine in base a una curva specificata.  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect> crea un bump mapping di un <xref:System.Windows.Media.Visual> per dare l'impressione di profondità e trama da una sorgente di luce artificiale.  
  
> [!NOTE]
> Il rendering degli effetti bitmap WPF viene eseguito in modalità software. e anche qualsiasi oggetto che applica un effetto verrà sottoposto a rendering in modalità software. Le prestazioni diminuiscono in modo più sensibile quando si usano effetti bitmap su elementi visivi di grandi dimensioni o quando si animano le proprietà di un effetto bitmap. Ciò non significa che gli effetti bitmap non debbano mai essere usati in questo modo, ma che è necessario prestare attenzione ed eseguire numerosi test affinché gli utenti acquisiscano l'esperienza necessaria.  
  
> [!NOTE]
> Gli effetti bitmap WPF non supportano l'esecuzione parzialmente attendibile. Per l'uso degli effetti bitmap, un'applicazione deve disporre di autorizzazioni di attendibilità completa.  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>Come applicare un effetto  
 <xref:System.Windows.Media.Effects.BitmapEffect> è una proprietà <xref:System.Windows.Media.Visual>. Applicare gli effetti agli oggetti visivi, ad esempio un <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>o <xref:System.Windows.UIElement>, è quindi semplice come impostare una proprietà. <xref:System.Windows.UIElement.BitmapEffect%2A> può essere impostato su un singolo oggetto <xref:System.Windows.Media.Effects.BitmapEffect> oppure è possibile concatenare più effetti utilizzando l'oggetto <xref:System.Windows.Media.Effects.BitmapEffectGroup>.  
  
 Nell'esempio seguente viene illustrato come applicare un <xref:System.Windows.Media.Effects.BitmapEffect> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 Nell'esempio seguente viene illustrato come applicare una <xref:System.Windows.Media.Effects.BitmapEffect> nel codice.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> Quando un <xref:System.Windows.Media.Effects.BitmapEffect> viene applicato a un contenitore di layout, ad esempio <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.Canvas>, l'effetto viene applicato alla struttura ad albero visuale dell'elemento o dell'oggetto visivo, inclusi tutti i relativi elementi figlio.  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>Creazione di effetti personalizzati  
 WPF fornisce inoltre interfacce non gestite per creare effetti personalizzati che possono essere utilizzati nelle applicazioni WPF gestite. Per materiale di riferimento aggiuntivo per la creazione di effetti bitmap personalizzati, vedere la documentazione [Unmanaged WPF Bitmap Effect](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh) (Effetto bitmap WPF non gestito).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [Effetto bitmap WPF non gestito](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
- [Security](../security-wpf.md)
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
- [Grafica bidimensionale e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)

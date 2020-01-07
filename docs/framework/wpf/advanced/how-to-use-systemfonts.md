---
title: 'Procedura: Usare la classe SystemFonts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 157565ceb9057049aef8b2bf274847d58c6b8dc8
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559963"
---
# <a name="how-to-use-systemfonts"></a>Procedura: Usare la classe SystemFonts
Questo esempio illustra come usare le risorse statiche della classe <xref:System.Windows.SystemFonts> per applicare uno stile a un pulsante o personalizzarlo.  
  
## <a name="example"></a>Esempio  
 Le risorse di sistema espongono diversi valori determinati dal sistema come risorse e proprietà per consentire la creazione di oggetti visivi coerenti con le impostazioni del sistema. <xref:System.Windows.SystemFonts> è una classe che contiene sia i valori dei tipi di carattere di sistema come proprietà statiche che le proprietà che fanno riferimento a chiavi di risorsa che possono essere usate per accedere dinamicamente a tali valori in fase di esecuzione. Ad esempio, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> è un valore <xref:System.Windows.SystemFonts> e <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> è una chiave di risorsa corrispondente.  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile usare i membri di <xref:System.Windows.SystemFonts> come proprietà statiche o riferimenti a risorse dinamiche (con il valore della proprietà statica come chiave). Usare un riferimento alla risorsa dinamica per aggiornare automaticamente la metrica del tipo di carattere durante l'esecuzione dell'applicazione; in caso contrario, usare un riferimento a un valore statico.  
  
> [!NOTE]
> Nelle chiavi di risorsa il suffisso "Key" viene aggiunto al nome della proprietà.  
  
 Nell'esempio seguente viene illustrato come accedere e utilizzare le proprietà di <xref:System.Windows.SystemFonts> come valori statici per applicare uno stile a un pulsante o personalizzarlo. Questo esempio di markup assegna i valori <xref:System.Windows.SystemFonts> a un pulsante.  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Per usare i valori di <xref:System.Windows.SystemFonts> nel codice, non è necessario usare un valore statico o un riferimento a una risorsa dinamica. Usare invece le proprietà non chiave della classe <xref:System.Windows.SystemFonts>. Anche se le proprietà non chiave sono apparentemente definite come proprietà statiche, il comportamento in fase di esecuzione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] come ospitato dal sistema rivaluterà le proprietà in tempo reale e configurerà correttamente le modifiche guidate dall'utente ai valori di sistema. L'esempio seguente illustra come specificare le impostazioni del tipo di carattere di un pulsante.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.SystemFonts>
- [Disegnare un'area con un pennello di sistema](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Utilizzare SystemParameters](how-to-use-systemparameters.md)
- [Usare chiavi di caratteri del sistema](how-to-use-system-fonts-keys.md)
- [Procedure relative alle proprietà](resources-how-to-topics.md)
- [Estensione del markup x:Static](../../../desktop-wpf/xaml-services/xstatic-markup-extension.md)
- [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Estensione del markup DynamicResource](dynamicresource-markup-extension.md)

---
title: 'Procedura: Utilizzare la classe SystemFonts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: bf99d716c5c41b7604244022d2e58423594a9cf3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674872"
---
# <a name="how-to-use-systemfonts"></a>Procedura: Utilizzare la classe SystemFonts
Questo esempio illustra come usare le risorse statiche del <xref:System.Windows.SystemFonts> classe per poter applicare uno stile a un pulsante o personalizzarlo.  
  
## <a name="example"></a>Esempio  
 Le risorse di sistema espongono diversi valori determinati dal sistema come risorse e proprietà per consentire la creazione di oggetti visivi coerenti con le impostazioni del sistema. <xref:System.Windows.SystemFonts> è una classe che contiene entrambi i valori del tipo di carattere di sistema come proprietà statiche e proprietà che fanno riferimento le chiavi di risorsa che possono essere utilizzate per accedere a tali valori in modo dinamico in fase di esecuzione. Ad esempio, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> è un <xref:System.Windows.SystemFonts> valore, e <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> è una chiave di risorsa corrispondente.  
  
 Nelle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile usare i membri di <xref:System.Windows.SystemFonts> come proprietà statiche o riferimenti a risorse dinamiche (con il valore della proprietà statica come chiave). Usare un riferimento alla risorsa dinamica per aggiornare automaticamente la metrica del tipo di carattere durante l'esecuzione dell'applicazione; in caso contrario, usare un riferimento a un valore statico.  
  
> [!NOTE]
>  Nelle chiavi di risorsa il suffisso "Key" viene aggiunto al nome della proprietà.  
  
 Nell'esempio seguente viene illustrato come accedere e usare le proprietà di <xref:System.Windows.SystemFonts> come valori statici per applicare uno stile a un pulsante o personalizzarlo. Questo esempio di markup assegna <xref:System.Windows.SystemFonts> valori a un pulsante.  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Per usare i valori di <xref:System.Windows.SystemFonts> nel codice, non è necessario utilizzare un valore statico o un riferimento di risorsa dinamica. In alternativa, usare le proprietà non chiave della <xref:System.Windows.SystemFonts> classe. Anche se le proprietà non chiave sono apparentemente definite come proprietà statiche, il comportamento di runtime di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitato dal sistema rivaluterà le proprietà in tempo reale e risponderà correttamente per le modifiche dall'utente ai valori di sistema. L'esempio seguente illustra come specificare le impostazioni del tipo di carattere di un pulsante.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.SystemFonts>
- [Disegnare un'area con un pennello di sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Utilizzare SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)
- [Usare chiavi di caratteri del sistema](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
- [Estensione del markup x:Static](../../../../docs/framework/xaml-services/x-static-markup-extension.md)
- [Risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [Estensione del markup DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)

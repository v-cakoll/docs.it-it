---
title: Estensione del markup DynamicResource
ms.date: 03/30/2017
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
ms.openlocfilehash: d07816718ebee2507f1888cffb70e6f8037bb996
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010397"
---
# <a name="dynamicresource-markup-extension"></a>Estensione del markup DynamicResource
Fornisce un valore per qualsiasi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributo della proprietà rinviando il valore per indicare un riferimento a una risorsa definita. Il comportamento di ricerca per tale risorsa è analogo alla ricerca in fase di esecuzione.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>Utilizzo della sintassi XAML per elementi proprietà  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`key`|Chiave per la risorsa richiesta. Questa chiave è stata inizialmente assegnata per il [direttiva X:Key](../../xaml-services/x-key-directive.md) se una risorsa è stata creata nel markup, o è stata specificata come il `key` parametro quando si chiama <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> se la risorsa è stata creata nel codice.|  
  
## <a name="remarks"></a>Note  
 Oggetto `DynamicResource` creare un'espressione temporanea durante la compilazione iniziale, pertanto viene rinviata ricerca per le risorse fino a quando il valore della risorsa richiesta è effettivamente necessario per costruire un oggetto. Questa situazione potrebbe verificarsi dopo il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina viene caricata. Il valore della risorsa verrà trovato basato su ricerca della chiave in tutti i dizionari di risorse attivo a partire dall'ambito corrente della pagina e verrà sostituito con l'espressione del segnaposto dalla compilazione.  
  
> [!IMPORTANT]
>  In termini di precedenza delle proprietà di dipendenza, un `DynamicResource` espressione è equivalente alla posizione in cui viene applicato il riferimento di risorsa dinamica. Se si imposta un valore locale per una proprietà che in precedenza era necessario un `DynamicResource` espressione come valore locale, il `DynamicResource` venga completamente rimossa. Per altri dettagli, vedere [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md).  
  
 Sono particolarmente appropriati per determinati scenari di accesso di risorse `DynamicResource` rispetto a un [estensione di Markup StaticResource](staticresource-markup-extension.md). Visualizzare [risorse XAML](xaml-resources.md) per una discussione sui vantaggi e implicazioni delle prestazioni `DynamicResource` e `StaticResource`.  
  
 L'oggetto specificato <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> deve corrispondere a una risorsa esistente, determinata dal [direttiva X:Key](../../xaml-services/x-key-directive.md) a un certo livello di pagina, applicazione, temi dei controlli disponibili e le risorse esterne o risorse di sistema e il ricerca delle risorse verrà eseguito nell'ordine indicato. Per altre informazioni sulla ricerca delle risorse per le risorse statiche e dinamiche, vedere [risorse XAML](xaml-resources.md).  
  
 Una chiave di risorsa può essere qualsiasi stringa definita nel [grammatica XamlName](../../xaml-services/xamlname-grammar.md). Una chiave di risorsa può anche essere altri tipi di oggetto, ad esempio un <xref:System.Type>. Oggetto <xref:System.Type> chiave è di fondamentale importanza per come controlli possono essere personalizzati con stili dai temi. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] per la ricerca di valori della risorsa, ad esempio <xref:System.Windows.FrameworkElement.FindResource%2A>, seguire la stessa logica di ricerca di risorse utilizzata dal `DynamicResource`.  
  
 Un modo alternativo per fare riferimento a una risorsa è come una [estensione di Markup StaticResource](staticresource-markup-extension.md).  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `DynamicResource` viene assegnato come valore <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> della classe dell'estensione <xref:System.Windows.DynamicResourceExtension> sottostante.  
  
 `DynamicResource` può essere utilizzata nella sintassi degli elementi oggetto. In questo caso, specificando il valore di <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> proprietà è obbligatoria.  
  
 L'oggetto `DynamicResource` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> come coppia proprietà=valore:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative. Poiché `DynamicResource` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.  
  
 Nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] l'implementazione del processore, la gestione di questa estensione di markup viene definita per il <xref:System.Windows.DynamicResourceExtension> classe.  
  
 `DynamicResource` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- [Risorse XAML](xaml-resources.md)
- [Risorse e codice](resources-and-code.md)
- [Direttiva x:Key](../../xaml-services/x-key-directive.md)
- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Estensione di markup StaticResource](staticresource-markup-extension.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)

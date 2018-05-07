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
ms.openlocfilehash: c09d009a8cc90e050f6cfb1a8d2abd5c61c5b19f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="dynamicresource-markup-extension"></a>Estensione del markup DynamicResource
Fornisce un valore per uno [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributo proprietà passando tale valore un riferimento a una risorsa definita. Il comportamento di ricerca per tale risorsa è analogo alla ricerca in fase di esecuzione.  
  
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
|`key`|Chiave per la risorsa richiesta. Questa chiave è stata inizialmente assegnata dal [direttiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md) se una risorsa è stata creata nel markup o è stata fornita come il `key` parametro quando si chiama <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> se la risorsa è stata creata nel codice.|  
  
## <a name="remarks"></a>Note  
 Oggetto `DynamicResource` crea un'espressione temporanea durante la compilazione iniziale, pertanto viene rinviata ricerca per le risorse fino a quando il valore della risorsa richiesta è effettivamente necessario per costruire un oggetto. Questa situazione potrebbe verificarsi dopo il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] caricamento della pagina. Il valore della risorsa verrà trovato in base alla ricerca della chiave a tutti i dizionari di risorse attivo a partire dall'ambito corrente della pagina e verrà sostituito con l'espressione del segnaposto dalla compilazione.  
  
> [!IMPORTANT]
>  In termini di precedenza di proprietà di dipendenza, un `DynamicResource` espressione è equivalente alla posizione in cui viene applicato il riferimento alla risorsa dinamica. Se si imposta un valore locale per una proprietà che in precedenza era un `DynamicResource` espressione come valore locale, il `DynamicResource` è stata completamente rimossa. Per altri dettagli, vedere [Precedenza del valore della proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Alcuni scenari di accesso della risorsa sono particolarmente indicati per `DynamicResource` rispetto a un [estensione di Markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md). Vedere [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) per una discussione sui vantaggi e implicazioni sulle prestazioni di `DynamicResource` e `StaticResource`.  
  
 Specificato <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> deve corrispondere a una risorsa esistente determinata da [direttiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md) qualche livello nella pagina, applicazione, i temi di controllo disponibile e risorse esterne o risorse di sistema e ricerca delle risorse verrà eseguito in tale ordine. Per ulteriori informazioni sulla ricerca di risorse per le risorse statiche e dinamiche, vedere [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Una chiave di risorsa può essere qualsiasi stringa definita nel [grammatica XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md). Una chiave di risorsa può essere anche altri tipi di oggetto, ad esempio un <xref:System.Type>. Oggetto <xref:System.Type> chiave è fondamentale per la modalità possono applicare stili controlli i temi. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] per la ricerca dei valori delle risorse, ad esempio <xref:System.Windows.FrameworkElement.FindResource%2A>, seguire la stessa logica di ricerca di risorsa utilizzata da `DynamicResource`.  
  
 Un modo alternativo per fare riferimento a una risorsa è un [estensione di Markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `DynamicResource` viene assegnato come valore <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> della classe dell'estensione <xref:System.Windows.DynamicResourceExtension> sottostante.  
  
 `DynamicResource` può essere utilizzato nella sintassi dell'elemento oggetto. In questo caso, se si specifica il valore di <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> proprietà è obbligatoria.  
  
 L'oggetto `DynamicResource` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> come coppia proprietà=valore:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative. Poiché `DynamicResource` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.  
  
 Nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] l'implementazione del processore, la gestione di questa estensione di markup viene definita per la <xref:System.Windows.DynamicResourceExtension> classe.  
  
 `DynamicResource` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Risorse e codice](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [Direttiva x:Key](../../../../docs/framework/xaml-services/x-key-directive.md)  
 [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Estensione di markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)  
 [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)

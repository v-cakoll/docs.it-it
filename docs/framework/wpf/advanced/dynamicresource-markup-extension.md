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
ms.openlocfilehash: f8b05f314be84e6104f1a9c7fe2edfdf826e51da
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559448"
---
# <a name="dynamicresource-markup-extension"></a>Estensione del markup DynamicResource
Fornisce un valore per qualsiasi attributo di proprietà [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] rinviando tale valore in modo che sia un riferimento a una risorsa definita. Il comportamento di ricerca per tale risorsa è analogo alla ricerca in fase di esecuzione.  
  
## <a name="xaml-attribute-usage"></a>Utilizzo della sintassi XAML per attributi  
  
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
  
## <a name="xaml-values"></a>Valor XAML  
  
|||  
|-|-|  
|`key`|Chiave per la risorsa richiesta. Questa chiave è stata inizialmente assegnata dalla [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) se una risorsa è stata creata nel markup oppure è stata fornita come parametro di `key` quando viene chiamata <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> se la risorsa è stata creata nel codice.|  
  
## <a name="remarks"></a>Note  
 Un `DynamicResource` creerà un'espressione temporanea durante la compilazione iniziale e quindi rinvia la ricerca delle risorse finché il valore della risorsa richiesta non è effettivamente necessario per costruire un oggetto. Questo problema potrebbe essere dovuto al caricamento della pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Il valore della risorsa verrà trovato in base alla ricerca chiave eseguita su tutti i dizionari risorse attivi a partire dall'ambito della pagina corrente e sostituisce l'espressione segnaposto dalla compilazione.  
  
> [!IMPORTANT]
> In termini di precedenza delle proprietà di dipendenza, un'espressione `DynamicResource` equivale alla posizione in cui viene applicato il riferimento a una risorsa dinamica. Se si imposta un valore locale per una proprietà che in precedenza aveva un'espressione `DynamicResource` come valore locale, il `DynamicResource` verrà completamente rimosso. Per altri dettagli, vedere [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md).  
  
 Alcuni scenari di accesso alle risorse sono particolarmente appropriati per `DynamicResource` anziché un' [estensione di markup StaticResource](staticresource-markup-extension.md). Vedere [risorse XAML](xaml-resources.md) per una discussione sui meriti relativi e sulle implicazioni relative alle prestazioni di `DynamicResource` e `StaticResource`.  
  
 Il <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> specificato deve corrispondere a una risorsa esistente determinata dalla [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) a un certo livello nella pagina, applicazione, i temi di controllo disponibili e le risorse esterne, o risorse di sistema, e la ricerca delle risorse verrà eseguita in tale ordine. Per altre informazioni sulla ricerca di risorse per le risorse statiche e dinamiche, vedere [risorse XAML](xaml-resources.md).  
  
 Una chiave di risorsa può essere qualsiasi stringa definita nella [Grammatica XamlName](../../../desktop-wpf/xaml-services/xamlname-grammar.md). Una chiave di risorsa può essere anche altri tipi di oggetto, ad esempio un <xref:System.Type>. Una chiave <xref:System.Type> è fondamentale per il modo in cui i controlli possono essere disegnati in base ai temi. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).  
  
 Le API per la ricerca dei valori delle risorse, ad esempio <xref:System.Windows.FrameworkElement.FindResource%2A>, seguono la stessa logica di ricerca delle risorse usata da `DynamicResource`.  
  
 Il mezzo dichiarativo alternativo per fare riferimento a una risorsa è come [estensione di markup StaticResource](staticresource-markup-extension.md).  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `DynamicResource` viene assegnato come valore <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> della classe dell'estensione <xref:System.Windows.DynamicResourceExtension> sottostante.  
  
 `DynamicResource` possibile utilizzare la sintassi dell'elemento oggetto. In questo caso, è necessario specificare il valore della proprietà <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>.  
  
 L'oggetto `DynamicResource` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> come coppia proprietà=valore:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative. Poiché `DynamicResource` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.  
  
 Nell'implementazione del processore [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], la gestione di questa estensione di markup viene definita dalla classe <xref:System.Windows.DynamicResourceExtension>.  
  
 `DynamicResource` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- [Risorse XAML](xaml-resources.md)
- [Risorse e codice](resources-and-code.md)
- [Direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md)
- [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Estensione di markup StaticResource](staticresource-markup-extension.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)

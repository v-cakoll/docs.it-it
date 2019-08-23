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
ms.openlocfilehash: 06355c64d36d2688ef027c1940688d4c87e51ec8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964791"
---
# <a name="dynamicresource-markup-extension"></a>Estensione del markup DynamicResource
Fornisce un valore per qualsiasi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributo Property rinviando tale valore in modo che sia un riferimento a una risorsa definita. Il comportamento di ricerca per tale risorsa è analogo alla ricerca in fase di esecuzione.  
  
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
|`key`|Chiave per la risorsa richiesta. Questa chiave è stata inizialmente assegnata dalla [direttiva x:Key](../../xaml-services/x-key-directive.md) se una risorsa è stata creata nel markup oppure è stata fornita `key` come parametro quando <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> si chiama se la risorsa è stata creata nel codice.|  
  
## <a name="remarks"></a>Note  
 Un `DynamicResource` creerà un'espressione temporanea durante la compilazione iniziale e quindi rinvia la ricerca delle risorse finché il valore della risorsa richiesta non è effettivamente necessario per costruire un oggetto. Questo potrebbe essere probabilmente dopo il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] caricamento della pagina. Il valore della risorsa verrà trovato in base alla ricerca chiave eseguita su tutti i dizionari risorse attivi a partire dall'ambito della pagina corrente e sostituisce l'espressione segnaposto dalla compilazione.  
  
> [!IMPORTANT]
> In termini di precedenza delle proprietà di dipendenza `DynamicResource` , un'espressione equivale alla posizione in cui viene applicato il riferimento a una risorsa dinamica. Se si imposta un valore locale per una proprietà che in precedenza aveva `DynamicResource` un'espressione come valore locale `DynamicResource` , viene rimossa completamente. Per altri dettagli, vedere [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md).  
  
 Alcuni scenari di accesso alle risorse sono particolarmente `DynamicResource` appropriati per invece di un' [estensione di markup StaticResource](staticresource-markup-extension.md). Vedere [risorse XAML](xaml-resources.md) per una discussione sui meriti relativi e sulle implicazioni relative alle `DynamicResource` prestazioni `StaticResource`di e.  
  
 Il parametro <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> specificato deve corrispondere a una risorsa esistente determinata dalla [direttiva x:Key](../../xaml-services/x-key-directive.md) a un certo livello della pagina, dell'applicazione, dei temi di controllo disponibili e delle risorse esterne o delle risorse di sistema e la ricerca delle risorse verrà eseguita in questo ordine. Per altre informazioni sulla ricerca di risorse per le risorse statiche e dinamiche, vedere [risorse XAML](xaml-resources.md).  
  
 Una chiave di risorsa può essere qualsiasi stringa definita nella [Grammatica XamlName](../../xaml-services/xamlname-grammar.md). Una chiave di risorsa può anche essere altri tipi di oggetto, ad <xref:System.Type>esempio. Una <xref:System.Type> chiave è fondamentale per il modo in cui i controlli possono essere disegnati in base ai temi. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).  
  
 Le API per la ricerca dei valori delle risorse <xref:System.Windows.FrameworkElement.FindResource%2A>, ad esempio, seguono la stessa logica di ricerca `DynamicResource`delle risorse usata da.  
  
 Il mezzo dichiarativo alternativo per fare riferimento a una risorsa è come [estensione di markup StaticResource](staticresource-markup-extension.md).  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `DynamicResource` viene assegnato come valore <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> della classe dell'estensione <xref:System.Windows.DynamicResourceExtension> sottostante.  
  
 `DynamicResource`può essere utilizzato nella sintassi dell'elemento oggetto. In questo caso, è necessario specificare il valore <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> della proprietà.  
  
 L'oggetto `DynamicResource` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> come coppia proprietà=valore:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative. Poiché `DynamicResource` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.  
  
 Nell'implementazione del <xref:System.Windows.DynamicResourceExtension> processore, la gestione di questa estensione di markup viene definita dalla classe. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
 `DynamicResource` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- [Risorse XAML](xaml-resources.md)
- [Risorse e codice](resources-and-code.md)
- [Direttiva x:Key](../../xaml-services/x-key-directive.md)
- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Estensione di markup StaticResource](staticresource-markup-extension.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)

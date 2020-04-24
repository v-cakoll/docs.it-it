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
ms.openlocfilehash: 5ccda8ba8f41a30e0ce1c832a6d3176b7fb8e8c2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646267"
---
# <a name="dynamicresource-markup-extension"></a>Estensione del markup DynamicResource
Fornisce un valore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per qualsiasi attributo di proprietà rinviando tale valore come riferimento a una risorsa definita. Il comportamento di ricerca per tale risorsa è analogo alla ricerca in fase di esecuzione.  
  
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
|`key`|Chiave per la risorsa richiesta. Questa chiave è stata inizialmente assegnata dalla [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) se una `key` risorsa <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> è stata creata nel markup o è stata fornita come parametro quando si chiama se la risorsa è stata creata nel codice.|  
  
## <a name="remarks"></a>Osservazioni  
 Un `DynamicResource` oggetto creerà un'espressione temporanea durante la compilazione iniziale e quindi rinvia la ricerca delle risorse fino a quando il valore della risorsa richiesta non è effettivamente necessario per costruire un oggetto. Questo può essere dopo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] il caricamento della pagina. Il valore della risorsa verrà trovato in base alla ricerca di chiavi in tutti i dizionari risorse attivi a partire dall'ambito della pagina corrente e viene sostituito con l'espressione segnaposto dalla compilazione.  
  
> [!IMPORTANT]
> In termini di precedenza della `DynamicResource` proprietà di dipendenza, un'espressione equivale alla posizione in cui viene applicato il riferimento alla risorsa dinamica. Se si imposta un valore locale per `DynamicResource` una proprietà che `DynamicResource` in precedenza aveva un'espressione come valore locale, l'oggetto viene completamente rimosso. Per altri dettagli, vedere [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md).  
  
 Alcuni scenari di accesso `DynamicResource` alle risorse sono particolarmente appropriati per invece di [un'estensione](staticresource-markup-extension.md)di markup StaticResource . Vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) per una discussione sui `DynamicResource` vantaggi `StaticResource`relativi e sulle implicazioni sulle prestazioni di e .  
  
 L'oggetto specificato <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> deve corrispondere a una risorsa esistente determinata dalla [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) a un certo livello nella pagina, nell'applicazione, nei temi di controllo disponibili e nelle risorse esterne o nelle risorse di sistema e la ricerca delle risorse verrà eseguita in tale ordine. Per altre informazioni sulla ricerca di risorse per le risorse statiche e dinamiche, vedere [Risorse XAML.](../../../desktop-wpf/fundamentals/xaml-resources-define.md)  
  
 Una chiave di risorsa può essere qualsiasi stringa definita nella grammatica [XamlName](../../../desktop-wpf/xaml-services/xamlname-grammar.md). Una chiave di risorsa può anche essere <xref:System.Type>altri tipi di oggetto, ad esempio un file . Una <xref:System.Type> chiave è fondamentale per il modo in cui i controlli possono essere modellati in base ai temi. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).  
  
 Le API per la ricerca di <xref:System.Windows.FrameworkElement.FindResource%2A>valori di risorsa, ad `DynamicResource`esempio , seguono la stessa logica di ricerca delle risorse utilizzata da .  
  
 Il metodo dichiarativo alternativo per fare riferimento a una risorsa è come [un StaticResource Markup Extension](staticresource-markup-extension.md).  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `DynamicResource` viene assegnato come valore <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> della classe dell'estensione <xref:System.Windows.DynamicResourceExtension> sottostante.  
  
 `DynamicResource`può essere utilizzato nella sintassi degli elementi oggetto. In questo caso, è necessario <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> specificare il valore della proprietà.  
  
 L'oggetto `DynamicResource` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> come coppia proprietà=valore:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative. Poiché `DynamicResource` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.  
  
 Nell'implementazione del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore, la gestione per <xref:System.Windows.DynamicResourceExtension> questa estensione di markup è definita dalla classe .  
  
 `DynamicResource` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Risorse e codice](resources-and-code.md)
- [Direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Estensione del markup StaticResource](staticresource-markup-extension.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)

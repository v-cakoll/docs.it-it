---
title: Estensione del markup StaticResource
ms.date: 03/30/2017
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
ms.openlocfilehash: 5c0bb247bae525658d89d53f1672e57b87aba7bc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646217"
---
# <a name="staticresource-markup-extension"></a>Estensione del markup StaticResource
Fornisce un valore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per qualsiasi attributo di proprietà cercando un riferimento a una risorsa già definita. Il comportamento di ricerca per tale risorsa è analogo alla ricerca in fase di caricamento, che cercherà le risorse caricate in precedenza dal markup della pagina corrente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e da altre origini dell'applicazione e genererà il valore della risorsa come valore della proprietà negli oggetti di runtime.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`key`|Chiave per la risorsa richiesta. Questa chiave è stata inizialmente assegnata dalla [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) se una `key` risorsa <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> è stata creata nel markup o è stata fornita come parametro quando si chiama se la risorsa è stata creata nel codice.|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!IMPORTANT]
> Un `StaticResource` oggetto non deve tentare di fare un riferimento in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] avanti a una risorsa definita a livello lessicale all'interno del file. Il tentativo di eseguire questa operazione non è supportato e, anche se tale riferimento non ha esito negativo, <xref:System.Windows.ResourceDictionary> il tentativo di riferimento in avanti comporterà una riduzione delle prestazioni in fase di caricamento quando vengono cercate le tabelle hash interne che rappresentano un. Per ottenere risultati ottimali, regolare la composizione dei dizionari risorse in modo da evitare riferimenti in avanti. Se non è possibile evitare un riferimento in avanti, usare invece [DynamicResource Markup Extension.If](dynamicresource-markup-extension.md) you cannot avoid a forward reference, use DynamicResource Markup Extension instead.  
  
 L'oggetto specificato <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> deve corrispondere a una risorsa esistente, identificata con una [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) a un certo livello nella pagina, nell'applicazione, nei temi di controllo disponibili e nelle risorse esterne o nelle risorse di sistema. La ricerca della risorsa viene eseguita in questo ordine. Per altre informazioni sul comportamento di ricerca delle risorse per le risorse statiche e dinamiche, vedere [Risorse XAML.](../../../desktop-wpf/fundamentals/xaml-resources-define.md)  
  
 Una chiave di risorsa può essere qualsiasi stringa definita nella grammatica [XamlName](../../../desktop-wpf/xaml-services/xamlname-grammar.md). Una chiave di risorsa può essere anche <xref:System.Type>altri tipi di oggetto, ad esempio un file . Una <xref:System.Type> chiave è fondamentale per il modo in cui i controlli possono essere modellati in base ai temi, tramite una chiave di stile implicita. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).  
  
 Il metodo dichiarativo alternativo per fare riferimento a una risorsa è come [DynamicResource Markup Extension](dynamicresource-markup-extension.md).  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `StaticResource` viene assegnato come valore <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> della classe dell'estensione <xref:System.Windows.StaticResourceExtension> sottostante.  
  
 `StaticResource`può essere utilizzato nella sintassi degli elementi oggetto. In questo caso, è necessario <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> specificare il valore della proprietà.  
  
 L'oggetto `StaticResource` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> come coppia proprietà=valore:  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative. Poiché `StaticResource` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.  
  
 Nell'implementazione del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore, la gestione per <xref:System.Windows.StaticResourceExtension> questa estensione di markup è definita dalla classe .  
  
 `StaticResource` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Risorse e codice](resources-and-code.md)

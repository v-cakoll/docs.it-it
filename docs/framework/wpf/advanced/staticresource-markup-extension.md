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
ms.openlocfilehash: 5d6c660dba1a351df4dafd756bcabd484b9afad6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554933"
---
# <a name="staticresource-markup-extension"></a>Estensione del markup StaticResource
Fornisce un valore per qualsiasi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributo della proprietà eseguendo la ricerca di un riferimento a una risorsa già definita. Il comportamento di ricerca per tale risorsa è analogo alla ricerca in fase di caricamento, che cerca le risorse che sono state caricate in precedenza dal markup del controllo corrente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina, nonché altre origini di applicazione e genererà il valore di risorse come la valore della proprietà negli oggetti in fase di esecuzione.  
  
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
|`key`|Chiave per la risorsa richiesta. Questa chiave è stata inizialmente assegnata per il [direttiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md) se una risorsa è stata creata nel markup, o è stata specificata come il `key` parametro quando si chiama <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> se la risorsa è stata creata nel codice.|  
  
## <a name="remarks"></a>Note  
  
> [!IMPORTANT]
>  Oggetto `StaticResource` non deve tentare di eseguire un riferimento diretto a una risorsa che viene definito lessicalmente ulteriore all'interno di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file. Tentativo di eseguire questa operazione non è supportato, e anche se tale riferimento ha esito positivo, il tentativo di riferimento in avanti comporteranno una riduzione delle prestazioni tempo di carico quando le tabelle hash interno che rappresenta un <xref:System.Windows.ResourceDictionary> viene effettuata la ricerca. Per ottenere risultati ottimali, modificare la composizione dei dizionari di risorse in modo che è possibile evitare i riferimenti in avanti. Se non è possibile evitare un riferimento in avanti, usare [estensione di Markup DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) invece.  
  
 L'oggetto specificato <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> deve corrispondere a una risorsa esistente, identificata con un [direttiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md) a un certo livello di pagina, applicazione, temi dei controlli disponibili e le risorse esterne o le risorse di sistema. In questo ordine viene eseguita la ricerca di risorse. Per altre informazioni sul comportamento di ricerca delle risorse per le risorse statiche e dinamiche, vedere [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Una chiave di risorsa può essere qualsiasi stringa definita nel [grammatica XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md). Una chiave di risorsa può anche essere altri tipi di oggetto, ad esempio un <xref:System.Type>. Oggetto <xref:System.Type> chiave è di fondamentale importanza per come controlli possono essere personalizzati con stili dai temi, tramite una chiave di stile implicito. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Un modo alternativo per fare riferimento a una risorsa è come una [estensione di Markup DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `StaticResource` viene assegnato come valore <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> della classe dell'estensione <xref:System.Windows.StaticResourceExtension> sottostante.  
  
 `StaticResource` può essere utilizzata nella sintassi degli elementi oggetto. In questo caso, specificando il valore di <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> proprietà è obbligatoria.  
  
 L'oggetto `StaticResource` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> come coppia proprietà=valore:  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative. Poiché `StaticResource` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.  
  
 Nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] l'implementazione del processore, la gestione di questa estensione di markup viene definita per il <xref:System.Windows.StaticResourceExtension> classe.  
  
 `StaticResource` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche
- [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [Risorse e codice](../../../../docs/framework/wpf/advanced/resources-and-code.md)

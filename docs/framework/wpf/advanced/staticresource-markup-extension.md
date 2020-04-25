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
ms.openlocfilehash: c160322fb3834fcd705c0482f5e55c8da32d143b
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141245"
---
# <a name="staticresource-markup-extension"></a>Estensione del markup StaticResource
Fornisce un valore per qualsiasi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributo di proprietà cercando un riferimento a una risorsa già definita. Il comportamento di ricerca per tale risorsa è analogo alla ricerca in fase di caricamento, che cercherà le risorse caricate in precedenza dal markup [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] della pagina corrente, nonché altre origini applicazione, e genererà il valore di tale risorsa come valore della proprietà negli oggetti Run-Time.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xml  
<object property="{StaticResource key}" ... />  
```  
  
## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" ... />  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`key`|Chiave per la risorsa richiesta. Questa chiave è stata inizialmente assegnata dalla [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) se una risorsa è stata creata nel markup oppure è stata fornita `key` come parametro quando <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> si chiama se la risorsa è stata creata nel codice.|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!IMPORTANT]
> Un `StaticResource` oggetto non deve tentare di creare un riferimento in avanti a una risorsa definita in modo lessicale all' [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] interno del file. Il tentativo di eseguire questa operazione non è supportato e anche se un riferimento di questo tipo non ha esito negativo, il tentativo di eseguire il riferimento in diretta comporterà un calo delle prestazioni <xref:System.Windows.ResourceDictionary> del tempo di caricamento quando viene eseguita la ricerca nelle tabelle hash interne che rappresentano. Per ottenere risultati ottimali, modificare la composizione dei dizionari risorse in modo che i riferimenti in diretta possano essere evitati. Se non è possibile evitare un riferimento in diretta, usare invece l' [estensione di markup DynamicResource](dynamicresource-markup-extension.md) .  
  
 L'oggetto <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> specificato deve corrispondere a una risorsa esistente, identificata con una [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) a un certo livello nella pagina, applicazione, i temi di controllo disponibili e le risorse esterne o le risorse di sistema. La ricerca di risorse viene eseguita nell'ordine specificato. Per altre informazioni sul comportamento di ricerca delle risorse per le risorse statiche e dinamiche, vedere [risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 Una chiave di risorsa può essere qualsiasi stringa definita nella [Grammatica XamlName](../../../desktop-wpf/xaml-services/xamlname-grammar.md). Una chiave di risorsa può anche essere altri tipi di oggetto, ad <xref:System.Type>esempio. Una <xref:System.Type> chiave è fondamentale per il modo in cui i controlli possono essere disegnati in base ai temi, tramite una chiave di stile implicito. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).  
  
 Il mezzo dichiarativo alternativo per fare riferimento a una risorsa è come [estensione di markup DynamicResource](dynamicresource-markup-extension.md).  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `StaticResource` viene assegnato come valore <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> della classe dell'estensione <xref:System.Windows.StaticResourceExtension> sottostante.  
  
 `StaticResource`può essere utilizzato nella sintassi dell'elemento oggetto. In questo caso, è necessario specificare il valore <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> della proprietà.  
  
 L'oggetto `StaticResource` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> come coppia proprietà=valore:  
  
```xml  
<object property="{StaticResource ResourceKey=key}" ... />  
```  
  
 L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative. Poiché `StaticResource` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Nell'implementazione del processore, la gestione di questa estensione di markup viene definita dalla <xref:System.Windows.StaticResourceExtension> classe.  
  
 `StaticResource` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedi anche

- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Risorse e codice](resources-and-code.md)

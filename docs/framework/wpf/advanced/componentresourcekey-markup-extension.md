---
title: Estensione del markup ComponentResourceKey
ms.date: 03/30/2017
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
ms.openlocfilehash: d11c26add084165eaa9fd0b319a375c4b98c7fb9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="componentresourcekey-markup-extension"></a>Estensione del markup ComponentResourceKey
Definisce e fa riferimento a chiavi per le risorse che vengono caricate dagli assembly esterni. In questo modo una ricerca di risorse specificare un tipo di destinazione in un assembly, anziché un dizionario risorse esplicito in un assembly o in una classe.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>Utilizzo della sintassi XAML per gli attributi (chiave di impostazione, compact)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>Utilizzo della sintassi XAML per gli attributi (impostazione chiave, dettagliata)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>Utilizzo della sintassi XAML per gli attributi (richiesta risorsa, compact)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>Utilizzo della sintassi XAML per gli attributi (richiesta risorsa, dettagliata)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`targetTypeName`|Il nome del pubblico [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] tipo definito nell'assembly di risorse.|  
|`targetID`|La chiave per la risorsa. Quando le risorse vengono ricercate `targetID` sarà analoga al [direttiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md) della risorsa.|  
  
## <a name="remarks"></a>Note  
 Come illustrato negli utilizzi sopra, un {`ComponentResourceKey`} utilizzo dell'estensione di markup è presente in due posizioni:  
  
-   La definizione di una chiave all'interno di un dizionario, come previsto dall'autore di un controllo.  
  
-   L'accesso a una risorsa del tema dall'assembly, quando si è applicare nuovamente i modelli del controllo, ma desidera utilizzare valori di proprietà che provengono da risorse fornite da temi del controllo.  
  
 Per fare riferimento a risorse del componente che provengono da temi, è consigliabile utilizzare `{DynamicResource}` anziché `{StaticResource}`. Come illustrato negli utilizzi. `{DynamicResource}` è consigliabile in quanto il tema stesso può essere modificato dall'utente. Se si desidera la risorsa del componente che corrisponde maggiormente l'intenzione dell'autore per supportare un tema, è consigliabile abilitare il riferimento di risorsa componente a essere anche dinamico.  
  
 Il <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifica un tipo presente nell'assembly di destinazione in cui la risorsa viene effettivamente definita. A `ComponentResourceKey` possono essere definite e utilizzate in modo indipendente da sapere esattamente dove le <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> è definito, ma deve essere risolto al tipo tramite assembly di riferimento.  
  
 Un utilizzo comune per <xref:System.Windows.ComponentResourceKey> consiste nel definire le chiavi che vengono quindi esposti come membri di una classe. A tal fine, utilizza il <xref:System.Windows.ComponentResourceKey> costruttore della classe, non l'estensione di markup. Per ulteriori informazioni, vedere <xref:System.Windows.ComponentResourceKey>, o la sezione "Definizione e riferimento a chiavi per le risorse del tema" dell'argomento [Cenni preliminari sul controllo creazione](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Per le chiavi di definizione e riferimento a risorse con chiave, la sintassi degli attributi viene comunemente utilizzato per il `ComponentResourceKey` estensione di markup.  
  
 La sintassi abbreviata mostrata si basa sul <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> firma del costruttore e l'utilizzo di parametri posizionali di un'estensione di markup. L'ordine in cui il `targetTypeName` e `targetID` figurano è importante. La sintassi dettagliata si basa sul <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> costruttore predefinito e quindi viene impostato il <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> e <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in modo analogo a una sintassi di attributo true su un elemento oggetto. Nella sintassi dettagliata, l'ordine in cui vengono impostate le proprietà non è importante. La relazione e i meccanismi di queste due alternative (compact e dettagliate) descritto in dettaglio nell'argomento [le estensioni di Markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 Tecnicamente, il valore per `targetID` può essere qualsiasi oggetto, non deve essere una stringa. Tuttavia, l'utilizzo più comune in WPF è per allineare il `targetID` valore con i moduli che sono stringhe e in cui tali stringhe sono valide nel [grammatica XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey` può essere utilizzato nella sintassi dell'elemento oggetto. In questo caso, che specifica il valore di entrambe le <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> e <xref:System.Windows.ComponentResourceKey.ResourceId%2A> proprietà è necessario inizializzare correttamente l'estensione.  
  
 Nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementazione lettore, la gestione di questa estensione di markup viene definita per la <xref:System.Windows.ComponentResourceKey> classe.  
  
 `ComponentResourceKey` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.ComponentResourceKey>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Cenni preliminari sulla modifica di controlli](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)

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
ms.openlocfilehash: 4cdba2a61be4e9686cd2120fd90a213534c222c8
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243362"
---
# <a name="componentresourcekey-markup-extension"></a>Estensione del markup ComponentResourceKey
Definisce e fa riferimento alle chiavi per le risorse caricate da assembly esterni. Ciò consente a una ricerca di risorse di specificare un tipo di destinazione in un assembly, anziché un dizionario risorse esplicito in un assembly o in una classe.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>Utilizzo degli attributi XAML (impostazione chiave, compatta)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>Utilizzo degli attributi XAML (impostazione chiave, verbose)XAML Attribute Usage (setting key, verbose)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>Utilizzo degli attributi XAML (richiesta di risorse, compattazione)XAML Attribute Usage (requesting resource, compact)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>Utilizzo degli attributi XAML (richiesta di risorse, dettaglio)XAML Attribute Usage (requesting resource, verbose)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`targetTypeName`|Nome del tipo CLR (Common Language Runtime) pubblico definito nell'assembly di risorse.|  
|`targetID`|Chiave per la risorsa. Quando le risorse `targetID` vengono cercate, sarà analogo alla [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) della risorsa.|  
  
## <a name="remarks"></a>Osservazioni  
 Come illustrato negli utilizzi precedenti,`ComponentResourceKey`l'utilizzo dell'estensione di markup di , ovvero in due posizioni, si trova in due posizioni:  
  
- Definizione di una chiave all'interno di un dizionario risorse del tema, come fornito da un autore di controllo.  
  
- Accesso a una risorsa tema dall'assembly, quando si rimodella il controllo ma si desidera utilizzare i valori delle proprietà che provengono dalle risorse fornite dai temi del controllo.  
  
 Per fare riferimento alle risorse dei componenti che provengono `{DynamicResource}` da `{StaticResource}`temi, è in genere consigliabile utilizzare anziché . Questo è mostrato negli usi. `{DynamicResource}`è consigliato perché il tema stesso può essere modificato dall'utente. Se si desidera che la risorsa del componente che corrisponde maggiormente alla finalità dell'autore del controllo per il supporto di un tema, è necessario abilitare il riferimento alla risorsa componente per essere dinamico anche.  
  
 Identifica <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> un tipo presente nell'assembly di destinazione in cui la risorsa è effettivamente definita. Un `ComponentResourceKey` oggetto può essere definito e <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> utilizzato indipendentemente dal sapere esattamente dove è definito l'oggetto , ma alla fine è necessario risolvere il tipo tramite assembly a cui si fa riferimento.  
  
 Un utilizzo <xref:System.Windows.ComponentResourceKey> comune di è quello di definire le chiavi che vengono quindi esposte come membri di una classe. Per questo utilizzo, <xref:System.Windows.ComponentResourceKey> si usa il costruttore della classe, non l'estensione di markup. Per ulteriori informazioni, vedere <xref:System.Windows.ComponentResourceKey>o la sezione "Definizione e riferimento alle chiavi per le risorse del tema" dell'argomento [Cenni](../controls/control-authoring-overview.md)preliminari sulla creazione di controlli .  
  
 Sia per stabilire chiavi che per fare riferimento alle risorse `ComponentResourceKey` con chiave, la sintassi degli attributi viene comunemente utilizzata per l'estensione di markup.  
  
 La sintassi compatta illustrata si basa sulla firma del <xref:System.Windows.ComponentResourceKey.%23ctor%2A> costruttore e sull'utilizzo dei parametri posizionali di un'estensione di markup. L'ordine in `targetTypeName` `targetID` cui vengono forniti gli elementi e sono indicati è importante. La sintassi dettagliata si <xref:System.Windows.ComponentResourceKey.%23ctor%2A> basa sul costruttore senza <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> <xref:System.Windows.ComponentResourceKey.ResourceId%2A> parametri e quindi imposta e in modo analogo a una sintassi di attributo true in un elemento oggetto. Nella sintassi dettagliata, l'ordine in cui vengono impostate le proprietà non è importante. La relazione e i meccanismi di queste due alternative (compact e verbose) sono descritti in modo più dettagliato nell'argomento [Estensioni](markup-extensions-and-wpf-xaml.md)di markup e XAML WPF .  
  
 Tecnicamente, il `targetID` valore per può essere qualsiasi oggetto, non deve essere una stringa. Tuttavia, l'utilizzo più comune `targetID` in WPFWPF consiste nell'allineare il valore con i form che sono stringhe e in cui tali stringhe sono valide in [XamlName Grammatica](../../../desktop-wpf/xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey`può essere utilizzato nella sintassi degli elementi oggetto. In questo caso, è necessario <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> specificare il valore delle proprietà e per <xref:System.Windows.ComponentResourceKey.ResourceId%2A> inizializzare correttamente l'estensione.  
  
 Nell'implementazione del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] lettore, la gestione per <xref:System.Windows.ComponentResourceKey> questa estensione di markup è definita dalla classe .  
  
 `ComponentResourceKey` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Panoramica della creazione di controlli](../controls/control-authoring-overview.md)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)

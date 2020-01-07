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
ms.openlocfilehash: 2ccc4f3154996a4e442a4092833f5c9ed9c8938a
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559461"
---
# <a name="componentresourcekey-markup-extension"></a>Estensione del markup ComponentResourceKey
Definisce e fa riferimento alle chiavi per le risorse caricate da assembly esterni. Ciò consente a una ricerca di risorse di specificare un tipo di destinazione in un assembly, anziché un dizionario risorse esplicito in un assembly o in una classe.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>Utilizzo degli attributi XAML (impostazione chiave, compatta)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>Utilizzo degli attributi XAML (impostazione della chiave, verbose)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>Utilizzo degli attributi XAML (risorsa richiesta, compatta)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>Utilizzo degli attributi XAML (richiesta di risorse, verbose)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>Valor XAML  
  
|||  
|-|-|  
|`targetTypeName`|Nome del tipo di Common Language Runtime pubblico (CLR) definito nell'assembly di risorse.|  
|`targetID`|Chiave per la risorsa. Quando le risorse vengono cercate, `targetID` sarà analogo alla [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) della risorsa.|  
  
## <a name="remarks"></a>Note  
 Come illustrato negli usi precedenti, un utilizzo dell'estensione di markup {`ComponentResourceKey`} si trova in due posizioni:  
  
- Definizione di una chiave all'interno di un dizionario risorse del tema, fornita da un autore del controllo.  
  
- Accesso a una risorsa del tema dall'assembly, quando si crea il modello del controllo, ma si desidera utilizzare i valori delle proprietà provenienti dalle risorse fornite dai temi del controllo.  
  
 Per fare riferimento alle risorse dei componenti che provengono dai temi, è in genere consigliabile usare `{DynamicResource}` anziché `{StaticResource}`. Questa operazione viene illustrata negli utilizzi. è consigliabile `{DynamicResource}` perché il tema stesso può essere modificato dall'utente. Se si vuole che la risorsa componente che corrisponda maggiormente alla finalità dell'autore del controllo per il supporto di un tema, è necessario abilitare anche il riferimento a una risorsa di componente dinamica.  
  
 Il <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifica un tipo esistente nell'assembly di destinazione in cui la risorsa è effettivamente definita. Un `ComponentResourceKey` può essere definito e utilizzato indipendentemente dal modo in cui viene definita l'<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>, ma è necessario risolvere il tipo tramite assembly a cui si fa riferimento.  
  
 Un utilizzo comune per <xref:System.Windows.ComponentResourceKey> consiste nel definire le chiavi che vengono quindi esposte come membri di una classe. Per questo utilizzo si usa il costruttore della classe <xref:System.Windows.ComponentResourceKey>, non l'estensione di markup. Per ulteriori informazioni, vedere <xref:System.Windows.ComponentResourceKey>o la sezione "definizione e riferimento alle chiavi per le risorse del tema" dell'argomento [Cenni preliminari sulla creazione di controlli](../controls/control-authoring-overview.md).  
  
 Per la creazione di chiavi e per il riferimento a risorse con chiave, la sintassi degli attributi viene comunemente utilizzata per l'estensione di markup `ComponentResourceKey`.  
  
 La sintassi Compact illustrata si basa sulla firma del costruttore <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> e sull'utilizzo dei parametri posizionali di un'estensione di markup. L'ordine in cui vengono forniti i `targetTypeName` e `targetID` è importante. La sintassi dettagliata si basa sul <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> costruttore senza parametri, quindi imposta le <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> e <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in modo analogo a una sintassi di attributo true su un elemento oggetto. Nella sintassi Verbose, l'ordine in cui le proprietà sono impostate non è importante. La relazione e i meccanismi di queste due alternative (Compact e Verbose) vengono descritti in modo più dettagliato nell'argomento [estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
 Tecnicamente, il valore per `targetID` può essere qualsiasi oggetto, non è necessario che sia una stringa. Tuttavia, l'utilizzo più comune in WPF consiste nell'allineare il valore `targetID` con i form che sono stringhe e in cui tali stringhe sono valide nella [Grammatica XamlName](../../../desktop-wpf/xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey` possibile utilizzare la sintassi dell'elemento oggetto. In questo caso, è necessario specificare il valore delle proprietà <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> e <xref:System.Windows.ComponentResourceKey.ResourceId%2A> per inizializzare correttamente l'estensione.  
  
 Nell'implementazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Reader, la gestione di questa estensione di markup viene definita dalla classe <xref:System.Windows.ComponentResourceKey>.  
  
 `ComponentResourceKey` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md)
- [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)

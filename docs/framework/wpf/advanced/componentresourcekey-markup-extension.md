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
ms.openlocfilehash: 78fddd65099d5f6bfc4796d5fa353a92171bda5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531002"
---
# <a name="componentresourcekey-markup-extension"></a>Estensione del markup ComponentResourceKey
Definisce e fa riferimento a chiavi per le risorse che vengono caricate da assembly esterni. In questo modo una ricerca delle risorse specificare un tipo di destinazione in un assembly, anziché un dizionario risorse esplicita in un assembly o in una classe.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>Utilizzo degli attributi XAML (impostazione della chiave compact)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>Utilizzo degli attributi XAML (impostazione di chiave, dettagliato)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>Utilizzo degli attributi XAML (risorsa richiedente, compact)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>Utilizzo degli attributi XAML (risorsa richiedente, dettagliato)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`targetTypeName`|Il nome del pubblico [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] tipo definito nell'assembly di risorse.|  
|`targetID`|La chiave per la risorsa. Quando le risorse vengono ricercate `targetID` sarà analoga al [direttiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md) della risorsa.|  
  
## <a name="remarks"></a>Note  
 Come illustrato nel precedenti, gli utilizzi un {`ComponentResourceKey`} utilizzo dell'estensione di markup viene trovato in due posizioni:  
  
-   La definizione di una chiave all'interno di un dizionario risorse, come fornito da un autore di controlli.  
  
-   Accede a una risorsa di tema dell'assembly, quando si è applicare nuovamente i modelli del controllo, ma desidera utilizzare i valori delle proprietà che provengono da risorse fornite da temi del controllo.  
  
 Per fare riferimento a risorse del componente che provengono dai temi, è consigliabile usare `{DynamicResource}` anziché `{StaticResource}`. Come illustrato negli utilizzi. `{DynamicResource}` è consigliato perché il tema stesso può essere modificato dall'utente. Se si desidera che la risorsa del componente che corrisponde maggiormente alla finalità dell'autore per supportare un tema, è consigliabile abilitare il riferimento di risorsa componente anche essere dinamico.  
  
 Il <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifica un tipo presente nell'assembly di destinazione in cui la risorsa viene effettivamente definita. Oggetto `ComponentResourceKey` può essere definito e utilizzato indipendentemente da conoscere esattamente dove il <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> è definito, ma deve essere risolto al tipo tramite assembly di riferimento.  
  
 Un utilizzo comune per <xref:System.Windows.ComponentResourceKey> consiste nel definire le chiavi che vengono quindi esposti come membri di una classe. A tal fine, utilizza il <xref:System.Windows.ComponentResourceKey> costruttore di classe, non l'estensione di markup. Per altre informazioni, vedere <xref:System.Windows.ComponentResourceKey>, o nella sezione "Definizione e riferimento a chiavi per le risorse del tema" dell'argomento [Cenni preliminari sulla modifica controllo](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Per le chiavi di definizione e riferimento a risorse con chiave, la sintassi degli attributi viene comunemente usato per il `ComponentResourceKey` estensione di markup.  
  
 La sintassi compatta illustrata si basa sul <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> firma del costruttore e utilizzo dei parametri posizionali di un'estensione di markup. L'ordine in cui il `targetTypeName` e `targetID` vengono forniti è importante. La sintassi dettagliata si basa sul <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> costruttore predefinito e quindi viene impostato il <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> e <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in modo analogo a una sintassi di attributo true in un elemento oggetto. Nella sintassi dettagliata, l'ordine in cui vengono impostate le proprietà non è importante. I meccanismi di questi due alternative (compact e verbose) e la relazione è descritto in dettaglio nell'argomento [estensioni di Markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 Tecnicamente, il valore per `targetID` può essere qualsiasi oggetto, non deve essere una stringa. Tuttavia, l'uso più comune in WPF è sufficiente allineare i `targetID` valore con i moduli che sono stringhe, e in cui tali stringhe sono validi nel [grammatica XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey` può essere utilizzata nella sintassi degli elementi oggetto. In questo caso, che specifica il valore di entrambi i <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> e <xref:System.Windows.ComponentResourceKey.ResourceId%2A> proprietà necessaria per inizializzare correttamente l'estensione.  
  
 Nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementazione del reader, la gestione di questa estensione di markup viene definita per il <xref:System.Windows.ComponentResourceKey> classe.  
  
 `ComponentResourceKey` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Cenni preliminari sulla modifica di controlli](../../../../docs/framework/wpf/controls/control-authoring-overview.md)
- [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)

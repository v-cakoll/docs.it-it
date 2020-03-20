---
title: Estensione del markup TemplateBinding
ms.date: 03/30/2017
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
ms.openlocfilehash: 8cebbf717f66b072bc84b2068193ff2fe76ea87b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187286"
---
# <a name="templatebinding-markup-extension"></a>Estensione del markup TemplateBinding
Collega il valore di una proprietà in un modello di controllo come valore di un'altra proprietà sul controllo basato su modelli.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a>Utilizzo dell'attributo XAML (per proprietà Set in modelli o stili)  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`propertyName`|<xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> della proprietà impostata nella sintassi del setter.|  
|`sourceProperty`|Altra proprietà di dipendenza esistente nel tipo basato su modelli, specificata da <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.<br /><br /> - oppure -<br /><br /> Nome della proprietà puntato definito da un tipo diverso rispetto al tipo di destinazione basato su modelli. Si tratta in effetti di un oggetto <xref:System.Windows.PropertyPath>. Vedere [Sintassi XAML PropertyPath](propertypath-xaml-syntax.md).|  
  
## <a name="remarks"></a>Osservazioni  
 A `TemplateBinding` è una forma ottimizzata di [un'associazione](binding-markup-extension.md) `Binding` per `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`gli scenari di modello, analoga a un oggetto costruito con . `TemplateBinding` è sempre un'associazione unidirezionale, anche se le proprietà implicano come impostazione predefinita l'associazione bidirezionale. Entrambe le proprietà in questione devono essere proprietà di dipendenza. Per ottenere l'associazione bidirezionale a un elemento padre `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`basato su modelli, utilizzare invece l'istruzione binding seguente.
  
 [RelativeSource](relativesource-markupextension.md) è un'altra estensione di markup che `TemplateBinding` viene talvolta utilizzata in combinazione con o anziché per eseguire l'associazione di proprietà relative all'interno di un modello.  
  
 La descrizione dei modelli di controllo come concetto non è trattata in questo caso; Per ulteriori informazioni, consultate Stili e modelli di [controllo.](../controls/control-styles-and-templates.md)  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `TemplateBinding` viene assegnato come valore <xref:System.Windows.TemplateBindingExtension.Property%2A> della classe dell'estensione <xref:System.Windows.TemplateBindingExtension> sottostante.  
  
 La sintassi di elementi oggetto è possibile, ma non viene mostrata poiché non ha applicazioni realistiche. `TemplateBinding` viene utilizzato per inserire valori all'interno dei setter, tramite espressioni valutate e l'utilizzo della sintassi dell'elemento oggetto per `TemplateBinding` per riempire la sintassi dell'elemento di proprietà `<Setter.Property>` è inutilmente dettagliata.  
  
 L'oggetto `TemplateBinding` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.TemplateBindingExtension.Property%2A> come coppia proprietà=valore:  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative. Poiché `TemplateBinding` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.  
  
 Nell'implementazione del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] processore XAML, la gestione <xref:System.Windows.TemplateBindingExtension> per questa estensione di markup è definita dalla classe .  
  
 `TemplateBinding` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni `{` di `}` markup in XAML usano i caratteri e nella sintassi degli attributi, ovvero la convenzione in base alla quale un processore XAML riconosce che un'estensione di markup deve elaborare l'attributo. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.ControlTemplate>
- [Applicazione di stili e modelli](../controls/styling-and-templating.md)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Estensione del markup RelativeSource](relativesource-markupextension.md)
- [Associazione dell'estensione di markup](binding-markup-extension.md)

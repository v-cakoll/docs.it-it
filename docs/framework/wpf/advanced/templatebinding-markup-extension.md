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
ms.openlocfilehash: 3ae17dc98137bd417d2468fb0415fb2078acf20f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686023"
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
|`sourceProperty`|Altra proprietà di dipendenza esistente nel tipo basato su modelli, specificata da <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.<br /><br /> -oppure-<br /><br /> Nome della proprietà puntato definito da un tipo diverso rispetto al tipo di destinazione basato su modelli. Si tratta in effetti di un oggetto <xref:System.Windows.PropertyPath>. Visualizzare [sintassi XAML di PropertyPath](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## <a name="remarks"></a>Note  
 Oggetto `TemplateBinding` è una forma ottimizzata di un [associazione](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) per gli scenari di modelli, analoghi a un `Binding` costruito con `{Binding RelativeSource={RelativeSource TemplatedParent}}`. `TemplateBinding` è sempre un'associazione unidirezionale, anche se le proprietà implicano come impostazione predefinita l'associazione bidirezionale. Entrambe le proprietà in questione devono essere proprietà di dipendenza. Per ottenere associazione bidirezionale a un elemento padre basato su modelli usare invece la seguente istruzione di associazione `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`. 
  
 [RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) è un'altra estensione di markup che talvolta viene usata in combinazione con o instead of `TemplateBinding` per eseguire l'associazione di proprietà all'interno di un modello.  
  
 Che descrive modelli di controllo come concetto non viene trattata in questo contesto. per altre informazioni, vedere [modelli e stili del controllo](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `TemplateBinding` viene assegnato come valore <xref:System.Windows.TemplateBindingExtension.Property%2A> della classe dell'estensione <xref:System.Windows.TemplateBindingExtension> sottostante.  
  
 La sintassi di elementi oggetto è possibile, ma non viene mostrata poiché non ha applicazioni realistiche. `TemplateBinding` viene utilizzato per inserire valori all'interno dei setter, tramite espressioni valutate e l'utilizzo della sintassi dell'elemento oggetto per `TemplateBinding` per riempire la sintassi dell'elemento di proprietà `<Setter.Property>` è inutilmente dettagliata.  
  
 L'oggetto `TemplateBinding` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.TemplateBindingExtension.Property%2A> come coppia proprietà=valore:  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative. Poiché `TemplateBinding` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.  
  
 Nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] l'implementazione del processore XAML, la gestione di questa estensione di markup viene definita per il <xref:System.Windows.TemplateBindingExtension> classe.  
  
 `TemplateBinding` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in uso XAML il `{` e `}` caratteri nella sintassi degli attributi, vale a dire la convenzione mediante il quale un processore XAML riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.ControlTemplate>
- [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Estensione di markup RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)
- [Estensione di markup Binding](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)

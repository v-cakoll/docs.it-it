---
title: Associazione dell'estensione di markup
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: 616e405e191cb264a002e903bed60cf04559a675
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964906"
---
# <a name="binding-markup-extension"></a>Associazione dell'estensione di markup
Rinvia un valore di proprietà a un valore associato a dati, creando un oggetto espressione intermedia e interpretando il contesto dei dati che si applica all'elemento e la relativa associazione in fase di esecuzione.  
  
## <a name="binding-expression-usage"></a>Utilizzo delle espressioni di binding  
  
```  
<object property="{Binding}" .../>  
-or-  
<object property="{Binding  bindProp1=value1[, bindPropN=valueN]*}" ...  
/>  
-or-  
<object property="{Binding path}" .../>  
-or  
<object property="{Binding path[, bindPropN=valueN]*}" .../>  
```  
  
## <a name="syntax-notes"></a>Note sulla sintassi  
 In queste sintassi, `[]` e `*` non sono valori letterali. Sono parte di una notazione per indicare che è possibile usare zero`=`o più coppie di*valori* bindProp, con un `,` separatore tra di essi e le coppie*valore* *bindProp*`=`precedenti.  
  
 Una delle proprietà elencate nella sezione "proprietà di binding che è possibile impostare con l'estensione di binding" può invece essere impostata utilizzando gli attributi di <xref:System.Windows.Data.Binding> un elemento oggetto. Tuttavia, questo non è realmente l'utilizzo dell'estensione di <xref:System.Windows.Data.Binding>markup di, ma è solo l'elaborazione XAML generale degli attributi che impostano <xref:System.Windows.Data.Binding> le proprietà della classe CLR. In altre parole, `<Binding` *bindProp1*`="`*value1* `"[` <xref:System.Windows.Data.Binding> *bindPropN* valuenèunasintassiequivalentepergliattributidiutilizzodeglielementi`"]*/>`oggetto `="` anziché l'utilizzo `Binding` di un'espressione. Per informazioni sull'utilizzo degli attributi XAML di proprietà specifiche di <xref:System.Windows.Data.Binding>, vedere la sezione "utilizzo degli attributi XAML" della proprietà pertinente <xref:System.Windows.Data.Binding> di nella libreria di classi .NET Framework.  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Nome della <xref:System.Windows.Data.Binding> proprietà o <xref:System.Windows.Data.BindingBase> da impostare. Non tutte <xref:System.Windows.Data.Binding> le proprietà possono essere impostate con `Binding` l'estensione e alcune proprietà possono essere impostate all' `Binding` interno di un'espressione solo utilizzando altre estensioni di markup nidificate. Vedere la sezione relativa alle proprietà di binding che possono essere impostate con l'estensione di binding.|  
|`value1, valueN`|Valore su cui impostare la proprietà. La gestione del valore dell'attributo è in definitiva specifica per il tipo e la logica della proprietà <xref:System.Windows.Data.Binding> specifica da impostare.|  
|`path`|Stringa di percorso che imposta la proprietà <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> implicita. Vedere anche [sintassi XAML di PropertyPath](propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>{Binding} non qualificato  
 L' `{Binding}` utilizzo illustrato in "binding espressione utilizzo" crea un <xref:System.Windows.Data.Binding> oggetto con i valori predefiniti, che include un <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> iniziale `null`di. Questa operazione è ancora utile in molti scenari, perché il <xref:System.Windows.Data.Binding> creato può basarsi sulle proprietà della data binding chiave, <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> ad <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> esempio e in fase di impostazione nel contesto dei dati di run-time. Per ulteriori informazioni sul concetto di contesto dati, vedere [Data Binding](../data/data-binding-wpf.md).  
  
## <a name="implicit-path"></a>Percorso implicito  
 L' `Binding` estensione di markup <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> utilizza come proprietà predefinita concettuale, in cui `Path=` non è necessario che venga visualizzata nell'espressione. Se si specifica un' `Binding` espressione con un percorso implicito, il percorso implicito deve essere visualizzato per primo nell'espressione, prima `bindProp` di qualsiasi altra <xref:System.Windows.Data.Binding> = `value` coppia in cui la proprietà viene specificata in base al nome. Ad esempio: `{Binding PathString}`, dove `PathString` è una stringa che viene valutata come il valore di <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> nell'oggetto <xref:System.Windows.Data.Binding> creato dall'utilizzo dell'estensione di markup. È possibile aggiungere un percorso implicito con altre proprietà denominate dopo il separatore virgola, ad esempio `{Binding LastName, Mode=TwoWay}`.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Proprietà di binding che possono essere impostate con l'estensione di binding  
 La sintassi illustrata in questo argomento usa l' `bindProp` approssimazione generica <xref:System.Windows.Data.Binding> = `value` , perché sono disponibili molte proprietà di <xref:System.Windows.Data.BindingBase> lettura/scrittura di o che possono `Binding` essere impostate tramite l'estensione di markup/ sintassi dell'espressione. Possono essere impostate in qualsiasi ordine, ad eccezione di un implicito <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>. È possibile specificare `Path=`in modo esplicito, nel qual caso è possibile impostarlo in qualsiasi ordine. Fondamentalmente, è possibile impostare zero o più proprietà nell'elenco seguente, usando `bindProp` = `value` le coppie separate da virgole.  
  
 Molti di questi valori di proprietà richiedono tipi di oggetto che non supportano la conversione di tipi nativi da una sintassi di testo in XAML e pertanto richiedono le estensioni di markup per essere impostate come valore di attributo. Per ulteriori informazioni, controllare la sezione Utilizzo degli attributi XAML nella libreria di classi .NET Framework per ogni proprietà. la stringa usata per la sintassi dell'attributo XAML con o senza ulteriore utilizzo dell'estensione di markup è fondamentalmente uguale al valore specificato in un' `Binding` espressione, ad eccezione del fatto che non si inseriscono le virgolette intorno a ciascuna `bindProp` =nell'espressione. `value` `Binding`  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: stringa che identifica un possibile gruppo di associazioni. Si tratta di un concetto di associazione relativamente avanzato. vedere la pagina di <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>riferimento per.  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.Converter%2A>: può essere `bindProp` impostato come = `value` stringa nell'espressione, ma a tale scopo è necessario un riferimento a un oggetto per il valore, ad esempio un'estensione di [markup StaticResource](staticresource-markup-extension.md). Il valore in questo caso è un'istanza di una classe Converter personalizzata.  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>: impostabile nell'espressione come identificatore basato su standard. vedere l'argomento di riferimento <xref:System.Windows.Data.Binding.ConverterCulture%2A>per.  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>: può essere impostato come `bindProp` = `value` stringa nell'espressione, ma dipende dal tipo del parametro passato. Se si passa un tipo riferimento per il valore, questo utilizzo richiede un riferimento a un oggetto, ad esempio un' [estensione di markup StaticResource](staticresource-markup-extension.md)annidata.  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>: si escludono a <xref:System.Windows.Data.Binding.RelativeSource%2A> vicenda <xref:System.Windows.Data.Binding.Source%2A>rispetto a e; ognuna di queste proprietà di associazione rappresenta una particolare metodologia di associazione. Vedere [Cenni preliminari sul data binding](../data/data-binding-overview.md).  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: può essere impostato come `bindProp` = `value` stringa nell'espressione, ma dipende dal tipo del valore passato. Se si passa un tipo riferimento, richiede un riferimento a un oggetto, ad esempio un' [estensione di markup StaticResource](staticresource-markup-extension.md)annidata.  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>: Booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.Mode%2A>: *value* è un nome di costante dall' <xref:System.Windows.Data.BindingMode> enumerazione. Ad esempio `{Binding Mode=OneWay}`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.Path%2A>: stringa che descrive un percorso in un oggetto dati o in un modello a oggetti generale. Il formato fornisce diverse convenzioni per l'attraversamento di un modello a oggetti che non può essere descritto in modo adeguato in questo argomento. Vedere [sintassi XAML di PropertyPath](propertypath-xaml-syntax.md).  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>: si escludono a vicenda <xref:System.Windows.Data.Binding.ElementName%2A> rispetto <xref:System.Windows.Data.Binding.Source%2A>a e; ognuna di queste proprietà di associazione rappresenta una particolare metodologia di associazione. Vedere [Cenni preliminari sul data binding](../data/data-binding-overview.md). Richiede un utilizzo [MarkupExtension di RelativeSource](relativesource-markupextension.md) annidato per specificare il valore.  
  
- <xref:System.Windows.Data.Binding.Source%2A>: si escludono a <xref:System.Windows.Data.Binding.RelativeSource%2A> vicenda <xref:System.Windows.Data.Binding.ElementName%2A>rispetto a e; ognuna di queste proprietà di associazione rappresenta una particolare metodologia di associazione. Vedere [Cenni preliminari sul data binding](../data/data-binding-overview.md). Richiede un utilizzo dell'estensione annidato, in genere un' [estensione di markup StaticResource](staticresource-markup-extension.md) che fa riferimento a un'origine dati oggetto da un dizionario risorse con chiave.  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>: stringa che descrive una convenzione di formato stringa per i dati associati. Si tratta di un concetto di associazione relativamente avanzato. vedere la pagina di <xref:System.Windows.Data.BindingBase.StringFormat%2A>riferimento per.  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: può essere impostato come `bindProp` = `value` stringa nell'espressione, ma dipende dal tipo del parametro passato. Se si passa un tipo riferimento per il valore, richiede un riferimento a un oggetto, ad esempio un' [estensione di markup StaticResource](staticresource-markup-extension.md)annidata.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *value* è un nome di costante dall' <xref:System.Windows.Data.UpdateSourceTrigger> enumerazione. Ad esempio `{Binding UpdateSourceTrigger=LostFocus}`. I controlli specifici hanno potenzialmente valori predefiniti diversi per questa proprietà di associazione. Vedere <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Booleano, può essere `true` o `false`. Il valore predefinito è `false`. Vedere la sezione Osservazioni.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Booleano, può essere `true` o `false`. Il valore predefinito è `false`. Vedere la sezione Osservazioni.  
  
- <xref:System.Windows.Data.Binding.XPath%2A>: stringa che descrive un percorso in XMLDOM di un'origine dati XML. Vedere [eseguire l'associazione a dati XML tramite un oggetto XmlDataProvider e query XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Di seguito sono riportate le proprietà di che non possono essere impostate`{Binding}` utilizzando il form dell'espressione o dell' `Binding` estensione di <xref:System.Windows.Data.Binding> markup.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: questa proprietà prevede un riferimento a un'implementazione di callback. Non è possibile fare riferimento a callback/metodi diversi dai gestori eventi nella sintassi XAML.  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>: la proprietà accetta una raccolta generica <xref:System.Windows.Controls.ValidationRule> di oggetti. Questo può essere espresso come elemento proprietà in un <xref:System.Windows.Data.Binding> elemento oggetto, ma non dispone di una tecnica di analisi degli attributi prontamente disponibile per l'utilizzo in un' `Binding` espressione. Vedere l'argomento di <xref:System.Windows.Data.Binding.ValidationRules%2A>riferimento per.  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Note  
  
> [!IMPORTANT]
> In termini di precedenza delle proprietà di dipendenza `Binding` , un'espressione equivale a un valore impostato localmente. Se si imposta un valore locale per una proprietà che in precedenza aveva `Binding` un'espressione `Binding` , viene rimossa completamente. Per altri dettagli, vedere [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md).  
  
 La descrizione di data binding a un livello di base non è descritta in questo argomento. Vedere [Cenni preliminari sul data binding](../data/data-binding-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding>e <xref:System.Windows.Data.PriorityBinding> non supportano una sintassi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di estensione. Si utilizzeranno invece gli elementi Property. Vedere gli argomenti di <xref:System.Windows.Data.MultiBinding> riferimento <xref:System.Windows.Data.PriorityBinding>per e.  
  
 I valori booleani per XAML non fanno distinzione tra maiuscole e minuscole. Ad esempio, è possibile specificare `{Binding NotifyOnValidationError=true}` o `{Binding NotifyOnValidationError=True}`.  
  
 Le associazioni che coinvolgono la convalida dei dati vengono in genere specificate `Binding` da un elemento esplicito `{Binding ...}` anziché come un'espressione <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> e <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> l'impostazione o in un'espressione non è comune. Ciò è dovuto al fatto che <xref:System.Windows.Data.Binding.ValidationRules%2A> la proprietà complementare non può essere impostata immediatamente nel form dell'espressione. Per altre informazioni, vedere [implementare la convalida dell'associazione](../data/how-to-implement-binding-validation.md).  
  
 `Binding` è un'estensione di markup. Le estensioni di markup vengono in genere implementate quando è necessario eseguire l'escape dei valori di attributo in modo che non siano valori letterali o nomi di gestori e il requisito è più globale rispetto ai convertitori di tipi attribuiti a determinati tipi o proprietà. Tutte le estensioni di markup in XAML `{` usano `}` i caratteri e nella relativa sintassi degli attributi, ovvero la convenzione con cui un processore XAML riconosce che un'estensione di markup deve elaborare il contenuto della stringa. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
 `Binding`è un'estensione di markup atipica in quanto <xref:System.Windows.Data.Binding> la classe che implementa la funzionalità di estensione per l'implementazione XAML di WPF implementa anche diversi altri metodi e proprietà non correlati a XAML. Gli altri membri hanno lo scopo di <xref:System.Windows.Data.Binding> creare una classe più versatile e autonoma in grado di risolvere molti scenari di data binding, oltre a funzionare come estensione di markup XAML.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.Binding>
- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)

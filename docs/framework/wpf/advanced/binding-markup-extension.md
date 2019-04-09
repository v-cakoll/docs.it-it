---
title: Associazione dell'estensione di markup
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: 3455c7ccdedb432fc05c7dc9e80f0f7509f4fa0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170313"
---
# <a name="binding-markup-extension"></a>Associazione dell'estensione di markup
Rinvia un valore della proprietà in un valore associato a dati, creazione di un oggetto di espressione intermedia e interpretando il contesto dati che si applica all'elemento e i relativi binding in fase di esecuzione.  
  
## <a name="binding-expression-usage"></a>Utilizzo dell'espressione di associazione  
  
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
 In questi tipi di sintassi, il `[]` e `*` non sono valori letterali. Fanno parte di una notazione per indicare che zero o più *bindProp*`=`*valore* coppie possono essere usate, con un `,` separatore tra e precede *bindProp*  `=` *valore* coppie.  
  
 Le proprietà elencate nella sezione "Associazione di proprietà che può essere impostato con l'estensione Binding" possono essere impostate utilizzando gli attributi di un <xref:System.Windows.Data.Binding> elemento oggetto. Tuttavia, che non è realmente l'utilizzo dell'estensione di markup della <xref:System.Windows.Data.Binding>, è sufficiente l'elaborazione XAML generale di attributi di cui impostare le proprietà di CLR <xref:System.Windows.Data.Binding> classe. In altre parole, `<Binding` *Propass1*`="`*value1* `"[` *propAssN*`="`*valoreN* `"]*/>` è una sintassi equivalente per gli attributi del <xref:System.Windows.Data.Binding> oggetto utilizzo dell'elemento anziché un `Binding` utilizzo dell'espressione. Per informazioni sull'utilizzo di proprietà specifiche dell'attributo XAML <xref:System.Windows.Data.Binding>, vedere la sezione "Utilizzo dell'attributo XAML" della proprietà pertinente del <xref:System.Windows.Data.Binding> nella libreria di classi .NET Framework.  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Il nome del <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.BindingBase> proprietà da impostare. Non tutti i <xref:System.Windows.Data.Binding> proprietà possono essere impostate con il `Binding` estensione e alcune proprietà possono essere impostate all'interno di un `Binding` espressione solo utilizzando ulteriormente annidati le estensioni di markup. Vedere la sezione "Associazione di proprietà che può essere impostato con l'estensione Binding".|  
|`value1, valueN`|Il valore su cui impostare la proprietà. La gestione del valore dell'attributo è in definitiva specifica del tipo e per la logica delle specifiche <xref:System.Windows.Data.Binding> proprietà da impostare.|  
|`path`|La stringa di percorso che imposta l'oggetto implicito <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> proprietà. Vedere anche [sintassi XAML di PropertyPath](propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>Non qualificato {Binding}  
 Il `{Binding}` utilizzo sono visualizzati in "Utilizzo dell'espressione di Binding" consente di creare un <xref:System.Windows.Data.Binding> dell'oggetto con valori predefiniti, che include un'iniziale <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> di `null`. Si tratta comunque utile in molti scenari, perché l'oggetto creato <xref:System.Windows.Data.Binding> potrebbe basarsi sulle proprietà di associazione di dati della chiave, ad esempio <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> e <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> impostato nel contesto dei dati in fase di esecuzione. Per altre informazioni sul concetto di contesto dei dati, vedere [Data Binding](../data/data-binding-wpf.md).  
  
## <a name="implicit-path"></a>Implicit Path  
 Il `Binding` utilizzi di estensione di markup <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> come concettuale "proprietà predefinita", dove `Path=` non necessario nell'espressione. Se si specifica un `Binding` espressione con un percorso implicito, il percorso implicito deve essere visualizzato innanzitutto nell'espressione, prima di qualsiasi altro `bindProp` = `value` coppie posizione in cui il <xref:System.Windows.Data.Binding> proprietà viene specificata in base al nome. Ad esempio: `{Binding PathString}`, dove `PathString` è una stringa che restituisce il valore di <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> nel <xref:System.Windows.Data.Binding> creato per l'utilizzo dell'estensione di markup. È possibile aggiungere un percorso implicito con altre proprietà denominate dopo il virgola come separatore, ad esempio, `{Binding LastName, Mode=TwoWay}`.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Proprietà di associazione che può essere impostata con l'estensione di Binding  
 La sintassi illustrata in questo argomento Usa il tipo generico `bindProp` = `value` approssimazione, poiché esistono molte proprietà di lettura/scrittura del <xref:System.Windows.Data.BindingBase> oppure <xref:System.Windows.Data.Binding> che può essere impostata tramite il `Binding` estensione di markup / sintassi delle espressioni. Possono essere impostate in qualsiasi ordine, fatta eccezione per implicita <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>. (È possibile specificare in modo esplicito `Path=`, nel qual caso può essere impostata in qualsiasi ordine). In pratica, è possibile impostare zero o più delle proprietà nell'elenco riportato di seguito, usando `bindProp` = `value` coppie separati da virgole.  
  
 Molti di questi valori di proprietà richiedono tipi di oggetto non supporta una conversione di tipo nativo da una sintassi del testo in XAML e pertanto richiedono le estensioni di markup per poter essere impostato come valore di attributo. Controllare la sezione Utilizzo dell'attributo XAML nella libreria di classi .NET Framework per ogni proprietà per altre informazioni, la stringa utilizzata per la sintassi di attributo XAML con o senza ulteriore estensione di markup dell'utilizzo è fondamentalmente lo stesso come il valore specificato in un `Binding` espressione, con l'eccezione che è necessario racchiudere tra virgolette intorno a ogni `bindProp` = `value` nel `Binding` espressione.  
  
-   <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: stringa che identifica un gruppo di associazione possibili. Questo è un concetto di associazione relativamente avanzato; vedere la pagina di riferimento per <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>.  
  
-   <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
-   <xref:System.Windows.Data.Binding.Converter%2A>: può essere impostato come una `bindProp` = `value` stringa nell'espressione, ma per eseguire questa operazione richiede un riferimento all'oggetto per il valore, ad esempio un [estensione di Markup StaticResource](staticresource-markup-extension.md). In questo caso, il valore è un'istanza di una classe di convertitore personalizzato.  
  
-   <xref:System.Windows.Data.Binding.ConverterCulture%2A>: impostabili nell'espressione come un identificatore basato su standard. vedere l'argomento di riferimento per <xref:System.Windows.Data.Binding.ConverterCulture%2A>.  
  
-   <xref:System.Windows.Data.Binding.ConverterParameter%2A>: può essere impostato come una `bindProp` = `value` stringa nell'espressione, ma ciò è dipende dal tipo del parametro passato. Se si passa un tipo di riferimento per valore, questo tipo di utilizzo richiede un riferimento all'oggetto, ad esempio nidificate [estensione di Markup StaticResource](staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.ElementName%2A>: si esclude reciprocamente <xref:System.Windows.Data.Binding.RelativeSource%2A> e <xref:System.Windows.Data.Binding.Source%2A>; ciascuna di queste proprietà di associazione rappresenta una metodologia di associazione specifica. Visualizzare [Panoramica sul Data Binding](../data/data-binding-overview.md).  
  
-   <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: può essere impostato come una `bindProp` = `value` stringa nell'espressione, ma ciò è dipende dal tipo del valore passato. Se il passaggio di un tipo riferimento, è necessario un riferimento all'oggetto, ad esempio nidificate [estensione di Markup StaticResource](staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.IsAsync%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
-   <xref:System.Windows.Data.Binding.Mode%2A>: *valore* è un nome di costante dal <xref:System.Windows.Data.BindingMode> enumerazione. Ad esempio `{Binding Mode=OneWay}`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
-   <xref:System.Windows.Data.Binding.Path%2A>: stringa che descrive il percorso in un oggetto dati o un modello a oggetti generale. Il formato fornisce numerose convenzioni per attraversare un modello a oggetti che non può essere adeguatamente descritta in questo argomento. Visualizzare [sintassi XAML di PropertyPath](propertypath-xaml-syntax.md).  
  
-   <xref:System.Windows.Data.Binding.RelativeSource%2A>: si esclude reciprocamente con <xref:System.Windows.Data.Binding.ElementName%2A> e <xref:System.Windows.Data.Binding.Source%2A>; ciascuna di queste proprietà di associazione rappresenta una metodologia di associazione specifica. Visualizzare [Panoramica sul Data Binding](../data/data-binding-overview.md). Richiede un annidato [RelativeSource MarkupExtension](relativesource-markupextension.md) utilizzo per specificare il valore.  
  
-   <xref:System.Windows.Data.Binding.Source%2A>: si esclude reciprocamente <xref:System.Windows.Data.Binding.RelativeSource%2A> e <xref:System.Windows.Data.Binding.ElementName%2A>; ciascuna di queste proprietà di associazione rappresenta una metodologia di associazione specifica. Visualizzare [Panoramica sul Data Binding](../data/data-binding-overview.md). Richiede un utilizzo dell'estensione annidata, in genere un [estensione di Markup StaticResource](staticresource-markup-extension.md) che fa riferimento a un'origine dati oggetto da un dizionario risorse con chiave.  
  
-   <xref:System.Windows.Data.BindingBase.StringFormat%2A>: una stringa che descrive una convenzione di formato di stringa per i dati associati. Questo è un concetto di associazione relativamente avanzato; vedere la pagina di riferimento per <xref:System.Windows.Data.BindingBase.StringFormat%2A>.  
  
-   <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: può essere impostato come una `bindProp` = `value` stringa nell'espressione, ma ciò è dipende dal tipo del parametro passato. Se viene passato un tipo di riferimento per il valore, richiede un riferimento all'oggetto, ad esempio nidificate [estensione di Markup StaticResource](staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *valore* è un nome di costante dal <xref:System.Windows.Data.UpdateSourceTrigger> enumerazione. Ad esempio `{Binding UpdateSourceTrigger=LostFocus}`. Controlli specifici possono presentare valori predefiniti diversi per questa proprietà di associazione. Vedere <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`. Vedere la sezione Osservazioni.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`. Vedere la sezione Osservazioni.  
  
-   <xref:System.Windows.Data.Binding.XPath%2A>: stringa che descrive il percorso nell'oggetto XMLDOM di un'origine dati XML. Visualizzare [associati a dati XML mediante un oggetto XMLDataProvider e query XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Di seguito sono le proprietà della <xref:System.Windows.Data.Binding> che non possono essere impostate tramite il `Binding` estensione di markup /`{Binding}` formato dell'espressione.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: questa proprietà richiede un riferimento a un'implementazione del callback. Non è possibile farvi riferimento/metodi di callback diversi dai gestori eventi nella sintassi XAML.  
  
-   <xref:System.Windows.Data.Binding.ValidationRules%2A>: la proprietà accetta una raccolta generica di <xref:System.Windows.Controls.ValidationRule> oggetti. Ciò potrebbe essere espresso come un elemento di proprietà in un <xref:System.Windows.Data.Binding> elemento oggetto, ma non dispone di alcuna tecnica di analisi degli attributi disponibile per l'uso in un `Binding` espressione. Vedere l'argomento di riferimento per <xref:System.Windows.Data.Binding.ValidationRules%2A>.  
  
-   <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Note  
  
> [!IMPORTANT]
>  In termini di precedenza delle proprietà di dipendenza, un `Binding` è equivalente a impostato localmente espressione valore. Se si imposta un valore locale per una proprietà che in precedenza era necessario un `Binding` espressione, il `Binding` venga completamente rimossa. Per altri dettagli, vedere [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md).  
  
 Descrizione dell'associazione dati a livello di base non è trattata in questo argomento. Visualizzare [Panoramica sul Data Binding](../data/data-binding-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Data.MultiBinding> e <xref:System.Windows.Data.PriorityBinding> non supportano un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintassi dell'estensione. Usare invece gli elementi di proprietà. Vedere gli argomenti di riferimento per <xref:System.Windows.Data.MultiBinding> e <xref:System.Windows.Data.PriorityBinding>.  
  
 I valori booleani per XAML sono maiuscole e minuscole. Ad esempio è possibile specificare `{Binding NotifyOnValidationError=true}` o `{Binding NotifyOnValidationError=True}`.  
  
 Le associazioni che comportano la convalida dei dati sono in genere specificate dalle esplicita `Binding` elemento anziché come un `{Binding ...}` espressione e impostazione <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> o <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> in un'espressione è insolito. Infatti, la proprietà complementare <xref:System.Windows.Data.Binding.ValidationRules%2A> non è possibile impostare facilmente nella forma espressione. Per altre informazioni, vedere [Implement Binding Validation](../data/how-to-implement-binding-validation.md).  
  
 `Binding` è un'estensione di markup. Le estensioni di markup vengono implementate in genere quando è necessario per eseguire l'escape dei valori di attributo devono essere valori letterali o gestore nomi e il requisito è più globale convertitori di tipi con attributi su alcuni tipi o proprietà. Tutte le estensioni di markup in uso XAML il `{` e `}` caratteri nella sintassi degli attributi, vale a dire la convenzione mediante il quale un processore XAML riconosce che il contenuto della stringa deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
 `Binding` è un'estensione di markup atipica in quanto il <xref:System.Windows.Data.Binding> classe che implementa la funzionalità di estensione per l'implementazione XAML di WPF implementa anche diversi altri metodi e proprietà che non sono correlate a XAML. Gli altri membri vengono utilizzati per rendere <xref:System.Windows.Data.Binding> una classe più versatile e indipendente che consentono di risolvere molti scenari di associazione di dati oltre a funzionare come un'estensione di markup XAML.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.Binding>
- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Panoramica di XAML (WPF)](xaml-overview-wpf.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)

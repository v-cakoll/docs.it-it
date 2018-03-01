---
title: Associazione dell'estensione di markup
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cc6a0616c6b462ffe6aca0a9adf27ac2ac7b7828
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="binding-markup-extension"></a>Associazione dell'estensione di markup
Rinvia un valore della proprietà in un valore associato a dati, creazione di un oggetto di espressione intermedia e interpretare il contesto dei dati che si applica all'elemento e l'associazione in fase di esecuzione.  
  
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
 In questi tipi di sintassi di `[]` e `*` non sono valori letterali. Parte di una notazione per indicare che sono zero o più *bindProp*`=`*valore* coppie possono essere usate, con un `,` separatore e precede *bindProp*  `=` *valore* coppie.  
  
 Le proprietà elencate nella sezione "Associazione di proprietà che può essere impostato con l'estensione Binding" possono essere impostate utilizzando gli attributi di un <xref:System.Windows.Data.Binding> elemento oggetto. Tuttavia, che non è realmente l'utilizzo dell'estensione di markup di <xref:System.Windows.Data.Binding>, è sufficiente l'elaborazione XAML generale di attributi che impostano le proprietà di CLR <xref:System.Windows.Data.Binding> classe. In altre parole, `<Binding` *Propass1*`="`*value1* `"[` *propAssN*`="`*valoreN* `"]*/>` è una sintassi equivalente per gli attributi di <xref:System.Windows.Data.Binding> oggetto utilizzo dell'elemento anziché di un `Binding` utilizzo dell'espressione. Per informazioni sull'utilizzo di proprietà specifiche di attributo XAML <xref:System.Windows.Data.Binding>, vedere la sezione "Utilizzo della sintassi XAML per gli attributi" della proprietà pertinente di <xref:System.Windows.Data.Binding> nella libreria di classi .NET Framework.  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Il nome del <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.BindingBase> proprietà da impostare. Non tutti i <xref:System.Windows.Data.Binding> proprietà possono essere impostate con i `Binding` estensione e alcune proprietà possono essere impostate all'interno di un `Binding` espressione solo utilizzando ulteriori estensioni di markup annidate. Vedere la sezione "Associazione di proprietà che può essere impostato con l'estensione Binding".|  
|`value1, valueN`|Il valore su cui impostare la proprietà. La gestione del valore dell'attributo è essenzialmente specifica per il tipo e la logica delle specifiche <xref:System.Windows.Data.Binding> proprietà impostata.|  
|`path`|La stringa di percorso che imposta il flag implicito <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> proprietà. Vedere anche [sintassi di PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>{Binding} non qualificato  
 Il `{Binding}` utilizzo come illustrato in "Utilizzo dell'espressione Binding" Crea un <xref:System.Windows.Data.Binding> dell'oggetto con valori predefiniti, che include un iniziale <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> di `null`. Questo è tuttavia utile in molti scenari, perché l'oggetto creato <xref:System.Windows.Data.Binding> potrebbe basarsi sulle proprietà di associazione di dati della chiave, ad esempio <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> e <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> viene impostata nel contesto dei dati in fase di esecuzione. Per ulteriori informazioni sul concetto di contesto dei dati, vedere [Data Binding](../../../../docs/framework/wpf/data/data-binding-wpf.md).  
  
## <a name="implicit-path"></a>Percorso implicito  
 Il `Binding` utilizza estensioni di markup <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> come concettuale "proprietà predefinita", dove `Path=` non deve essere visualizzato nell'espressione. Se si specifica un `Binding` espressione con un percorso implicito, il percorso implicito deve essere visualizzato innanzitutto nell'espressione, prima di qualsiasi altro `bindProp` = `value` coppie dove il <xref:System.Windows.Data.Binding> proprietà specificata dal nome. Ad esempio: `{Binding PathString}`, dove `PathString` è una stringa che viene valutata il valore di <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> nel <xref:System.Windows.Data.Binding> creato per l'utilizzo dell'estensione di markup. È possibile aggiungere un percorso implicito con altre proprietà denominate dopo il separatore virgola, ad esempio, `{Binding LastName, Mode=TwoWay}`.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Proprietà di associazione che può essere impostata con l'estensione di Binding  
 La sintassi illustrata in questo argomento viene utilizzato il generico `bindProp` = `value` approssimativo, perché sono presenti molte proprietà di lettura/scrittura di <xref:System.Windows.Data.BindingBase> o <xref:System.Windows.Data.Binding> che può essere impostata tramite il `Binding` estensione di markup / sintassi delle espressioni. Possono essere impostate in qualsiasi ordine, fatta eccezione per implicita <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>. (È possibile specificare in modo esplicito `Path=`, nel qual caso è possibile impostare in qualsiasi ordine). In pratica, è possibile impostare zero o più delle proprietà nell'elenco riportato di seguito, utilizzando `bindProp` = `value` coppie separate da virgole.  
  
 Alcuni valori di queste proprietà richiedono tipi di oggetto non supporta una conversione di tipo nativo da una sintassi del testo in XAML e pertanto richiedono le estensioni di markup per impostare come valore dell'attributo. Controllare la sezione di attributo XAML nella libreria di classi .NET Framework per ogni proprietà per altre informazioni, la stringa utilizzata per la sintassi di attributo XAML con o senza estensione di markup ulteriore utilizzo è fondamentalmente identico al valore specificato in un `Binding` espressione, con l'eccezione che non viene inserito tra virgolette ogni `bindProp` = `value` nel `Binding` espressione.  
  
-   <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: stringa che identifica un gruppo di associazione possibili. Questo è un concetto di associazione relativamente avanzato; vedere la pagina di riferimento per <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>.  
  
-   <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
-   <xref:System.Windows.Data.Binding.Converter%2A>: è possibile impostare come un `bindProp` = `value` stringa nell'espressione, ma a tale scopo è necessario un riferimento all'oggetto per il valore, ad esempio un [estensione di Markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md). In questo caso, il valore è un'istanza di una classe di convertitore personalizzato.  
  
-   <xref:System.Windows.Data.Binding.ConverterCulture%2A>: impostabile nell'espressione come un identificatore standard. vedere l'argomento di riferimento per <xref:System.Windows.Data.Binding.ConverterCulture%2A>.  
  
-   <xref:System.Windows.Data.Binding.ConverterParameter%2A>: è possibile impostare come un `bindProp` = `value` stringa nell'espressione, ma questo è dipende dal tipo del parametro viene passato. Se si passa un tipo di riferimento per il valore, è necessario un riferimento all'oggetto, ad esempio nidificate [estensione di Markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.ElementName%2A>: si escludono a vicenda e <xref:System.Windows.Data.Binding.RelativeSource%2A> e <xref:System.Windows.Data.Binding.Source%2A>; ciascuna di queste proprietà di associazione rappresenta una metodologia di associazione specifica. Vedere [panoramica sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: è possibile impostare come un `bindProp` = `value` stringa nell'espressione, ma questo è dipende dal tipo di valore passato. Se il passaggio di un tipo riferimento, richiede un riferimento all'oggetto, ad esempio nidificate [estensione di Markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.IsAsync%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
-   <xref:System.Windows.Data.Binding.Mode%2A>: *valore* è un nome di costante dal <xref:System.Windows.Data.BindingMode> enumerazione. Ad esempio `{Binding Mode=OneWay}`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
-   <xref:System.Windows.Data.Binding.Path%2A>: stringa che descrive un percorso in un oggetto dati o un modello a oggetti generale. Il formato fornisce numerose convenzioni per l'attraversamento di un modello a oggetti che non può essere adeguatamente descritte in questo argomento. Vedere [sintassi di PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).  
  
-   <xref:System.Windows.Data.Binding.RelativeSource%2A>: si esclude reciprocamente con <xref:System.Windows.Data.Binding.ElementName%2A> e <xref:System.Windows.Data.Binding.Source%2A>; ciascuna di queste proprietà di associazione rappresenta una metodologia di associazione specifica. Vedere [panoramica sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md). Richiede un nidificata [RelativeSource MarkupExtension](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) utilizzo per specificare il valore.  
  
-   <xref:System.Windows.Data.Binding.Source%2A>: si escludono a vicenda e <xref:System.Windows.Data.Binding.RelativeSource%2A> e <xref:System.Windows.Data.Binding.ElementName%2A>; ciascuna di queste proprietà di associazione rappresenta una metodologia di associazione specifica. Vedere [panoramica sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md). Richiede un utilizzo dell'estensione annidata, in genere un [estensione di Markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) che fa riferimento a un'origine dati oggetto da un dizionario risorse con chiave.  
  
-   <xref:System.Windows.Data.BindingBase.StringFormat%2A>: stringa che descrive una convenzione del formato di stringa per i dati associati. Questo è un concetto di associazione relativamente avanzato; vedere la pagina di riferimento per <xref:System.Windows.Data.BindingBase.StringFormat%2A>.  
  
-   <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: è possibile impostare come un `bindProp` = `value` stringa nell'espressione, ma questo è dipende dal tipo del parametro viene passato. Se il passaggio di un tipo di riferimento per valore, richiede un riferimento all'oggetto, ad esempio nidificate [estensione di Markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *valore* è un nome di costante dal <xref:System.Windows.Data.UpdateSourceTrigger> enumerazione. Ad esempio `{Binding UpdateSourceTrigger=LostFocus}`. Controlli specifici possono presentare valori predefiniti diversi per la proprietà di associazione. Vedere <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`. Vedere la sezione Osservazioni.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Valore booleano, può essere `true` o `false`. Il valore predefinito è `false`. Vedere la sezione Osservazioni.  
  
-   <xref:System.Windows.Data.Binding.XPath%2A>: stringa che descrive un percorso nell'oggetto XMLDOM di un'origine dati XML. Vedere [associare ai dati XML utilizzando un oggetto XMLDataProvider e query XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Di seguito sono proprietà di <xref:System.Windows.Data.Binding> che non possono essere impostate utilizzando il `Binding` estensione di markup /`{Binding}` formato di espressione.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: questa proprietà richiede un riferimento a un'implementazione del callback. Callback/metodi diversi da gestori di eventi non può fare riferimento nella sintassi XAML.  
  
-   <xref:System.Windows.Data.Binding.ValidationRules%2A>: la proprietà accetta una raccolta generica di <xref:System.Windows.Controls.ValidationRule> oggetti. Questo può essere espressa come elemento proprietà in un <xref:System.Windows.Data.Binding> elemento oggetto, ma non dispone di alcuna tecnica di analisi degli attributi disponibile per l'utilizzo in un `Binding` espressione. Vedere l'argomento di riferimento per <xref:System.Windows.Data.Binding.ValidationRules%2A>.  
  
-   <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Note  
  
> [!IMPORTANT]
>  In termini di precedenza di proprietà di dipendenza, un `Binding` è equivalente a impostato localmente espressione valore. Se si imposta un valore locale per una proprietà che in precedenza era un `Binding` espressione, il `Binding` è stata completamente rimossa. Per altri dettagli, vedere [Precedenza del valore della proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 La descrizione dell'associazione dati a un livello di base non viene descritta in questo argomento. Vedere [panoramica sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Data.MultiBinding>e <xref:System.Windows.Data.PriorityBinding> non supportano un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintassi dell'estensione. È necessario utilizzare gli elementi di proprietà. Vedere gli argomenti di riferimento per <xref:System.Windows.Data.MultiBinding> e <xref:System.Windows.Data.PriorityBinding>.  
  
 I valori booleani per XAML sono la distinzione tra maiuscole e minuscole. Ad esempio è possibile specificare `{Binding NotifyOnValidationError=true}` o `{Binding NotifyOnValidationError=True}`.  
  
 Le associazioni che comportano la convalida dei dati sono in genere specificate dalle esplicita `Binding` elemento anziché come un `{Binding ...}` espressione e impostazione <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> o <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> in un'espressione non è comune. Infatti, la proprietà complementare <xref:System.Windows.Data.Binding.ValidationRules%2A> non può essere facilmente impostato nel formato di espressione. Per ulteriori informazioni, vedere [Implement Binding Validation](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md).  
  
 `Binding` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando è necessario per eseguire l'escape dei valori di attributo devono essere valori letterali o gestore nomi e il requisito è più globale del convertitori di tipi con attributi su alcuni tipi o proprietà. Tutte le estensioni di markup in XAML utilizzano il `{` e `}` caratteri nella relativa sintassi degli attributi, che corrisponde alla convenzione mediante il quale il processore XAML riconosce che il contenuto della stringa deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 `Binding`è un'estensione di markup atipici in quanto la <xref:System.Windows.Data.Binding> classe che implementa la funzionalità di estensione per l'implementazione XAML di WPF implementa anche numerosi altri metodi e proprietà che non sono correlate a XAML. Gli altri membri vengono utilizzati per rendere <xref:System.Windows.Data.Binding> una classe più versatile e indipendente per poter gestire molti scenari di associazione dati oltre a funzionare come estensione di markup XAML.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Data.Binding>  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)

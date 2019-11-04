---
title: Associazione dell'estensione di markup
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: d0a437e756da16db978d8074c4355fd83d211b67
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453606"
---
# <a name="binding-markup-extension"></a>Associazione dell'estensione di markup
Rinvia un valore di proprietà a un valore associato a dati, creando un oggetto espressione intermedia e interpretando il contesto dei dati che si applica all'elemento e la relativa associazione in fase di esecuzione.  
  
## <a name="binding-expression-usage"></a>Utilizzo delle espressioni di binding  
  
```xaml  
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
 In queste sintassi, il `[]` e il `*` non sono valori letterali. Sono parte di una notazione per indicare che è possibile usare zero o più coppie`=`*valore* *bindProp* , con un separatore di `,` tra di essi e le coppie di *valori*`=`*bindProp* precedenti.  
  
 Una delle proprietà elencate nella sezione "proprietà di binding che è possibile impostare con l'estensione di binding" può invece essere impostata utilizzando gli attributi di un <xref:System.Windows.Data.Binding> elemento oggetto. Tuttavia, non si tratta effettivamente dell'utilizzo dell'estensione di markup di <xref:System.Windows.Data.Binding>, ma è solo l'elaborazione XAML generale degli attributi che impostano le proprietà della classe <xref:System.Windows.Data.Binding> CLR. In altre parole, `<Binding` *bindProp1*`="`*value1*`"[` *bindPropN*`="`*valore*`"]*/>` è una sintassi equivalente per gli attributi di <xref:System.Windows.Data.Binding> utilizzo dell'elemento oggetto invece di un utilizzo di espressione `Binding`. Per informazioni sull'utilizzo degli attributi XAML di proprietà specifiche di <xref:System.Windows.Data.Binding>, vedere la sezione "utilizzo degli attributi XAML" della proprietà pertinente di <xref:System.Windows.Data.Binding> nella libreria di classi di .NET Framework.  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Nome della proprietà <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.BindingBase> da impostare. Non tutte le proprietà di <xref:System.Windows.Data.Binding> possono essere impostate con l'estensione `Binding` e alcune proprietà possono essere impostate all'interno di un'espressione `Binding` solo utilizzando altre estensioni di markup nidificate. Vedere la sezione relativa alle proprietà di binding che possono essere impostate con l'estensione di binding.|  
|`value1, valueN`|Valore su cui impostare la proprietà. La gestione del valore dell'attributo è in definitiva specifica per il tipo e la logica della proprietà <xref:System.Windows.Data.Binding> specifica da impostare.|  
|`path`|Stringa di percorso che imposta la proprietà <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> implicita. Vedere anche [sintassi XAML di PropertyPath](propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>{Binding} non qualificato  
 Il `{Binding}` utilizzo illustrato in "binding espressione utilizzo" crea un oggetto <xref:System.Windows.Data.Binding> con i valori predefiniti, che include un <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> iniziale di `null`. Questo è ancora utile in molti scenari, perché il <xref:System.Windows.Data.Binding> creato potrebbe basarsi sulle proprietà data binding chiave, ad esempio <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> e <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> essere impostate nel contesto dei dati di run-time. Per ulteriori informazioni sul concetto di contesto dati, vedere [Data Binding](../data/data-binding-wpf.md).  
  
## <a name="implicit-path"></a>Percorso implicito  
 L'estensione di markup `Binding` utilizza <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> come proprietà predefinita concettuale, in cui non è necessario che `Path=` venga visualizzata nell'espressione. Se si specifica un'espressione di `Binding` con un percorso implicito, il percorso implicito deve essere visualizzato per primo nell'espressione, prima di qualsiasi altra `bindProp`=`value` coppie in cui la proprietà <xref:System.Windows.Data.Binding> viene specificata in base al nome. Ad esempio: `{Binding PathString}`, dove `PathString` è una stringa che viene valutata come il valore di <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> nel <xref:System.Windows.Data.Binding> creato dall'utilizzo dell'estensione di markup. È possibile aggiungere un percorso implicito con altre proprietà denominate dopo il separatore virgola, ad esempio `{Binding LastName, Mode=TwoWay}`.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Proprietà di binding che possono essere impostate con l'estensione di binding  
 La sintassi illustrata in questo argomento usa l'`bindProp`generica =`value` approssimazione, perché sono disponibili molte proprietà di lettura/scrittura di <xref:System.Windows.Data.BindingBase> o <xref:System.Windows.Data.Binding> che possono essere impostate tramite la sintassi dell'espressione o dell'estensione di markup `Binding`. Possono essere impostate in qualsiasi ordine, ad eccezione di un <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>implicito. È possibile specificare in modo esplicito `Path=`, nel qual caso è possibile impostarlo in qualsiasi ordine. Fondamentalmente, è possibile impostare zero o più proprietà nell'elenco seguente, usando `bindProp`=coppie di `value` separate da virgole.  
  
 Molti di questi valori di proprietà richiedono tipi di oggetto che non supportano la conversione di tipi nativi da una sintassi di testo in XAML e pertanto richiedono le estensioni di markup per essere impostate come valore di attributo. Per ulteriori informazioni, controllare la sezione Utilizzo degli attributi XAML nella libreria di classi .NET Framework per ogni proprietà. la stringa usata per la sintassi dell'attributo XAML con o senza ulteriore utilizzo dell'estensione di markup è fondamentalmente uguale al valore specificato in un'espressione di `Binding`, con l'eccezione che non si inseriscono le virgolette intorno a ogni `bindProp`=`value` espressione `Binding`.  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: stringa che identifica un possibile gruppo di associazioni. Si tratta di un concetto di associazione relativamente avanzato. vedere la pagina di riferimento per <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>.  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.Converter%2A>: può essere impostato come `bindProp`=stringa `value` nell'espressione, ma a tale scopo è necessario un riferimento a un oggetto per il valore, ad esempio un' [estensione di markup StaticResource](staticresource-markup-extension.md). Il valore in questo caso è un'istanza di una classe Converter personalizzata.  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>: impostabile nell'espressione come identificatore basato su standard; per <xref:System.Windows.Data.Binding.ConverterCulture%2A>, vedere l'argomento di riferimento.  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>: può essere impostato come `bindProp`=stringa `value` nell'espressione, ma dipende dal tipo di parametro passato. Se si passa un tipo riferimento per il valore, questo utilizzo richiede un riferimento a un oggetto, ad esempio un' [estensione di markup StaticResource](staticresource-markup-extension.md)annidata.  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>: si escludono a vicenda rispetto a <xref:System.Windows.Data.Binding.RelativeSource%2A> e <xref:System.Windows.Data.Binding.Source%2A>; ognuna di queste proprietà di associazione rappresenta una particolare metodologia di associazione. Vedere [Cenni preliminari sul data binding](../data/data-binding-overview.md).  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: può essere impostato come `bindProp`=stringa `value` nell'espressione, ma dipende dal tipo del valore passato. Se si passa un tipo riferimento, richiede un riferimento a un oggetto, ad esempio un' [estensione di markup StaticResource](staticresource-markup-extension.md)annidata.  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>: booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.Mode%2A>: *value* è un nome di costante dell'enumerazione <xref:System.Windows.Data.BindingMode>. Ad esempio `{Binding Mode=OneWay}`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: booleano, può essere `true` o `false`. Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.Path%2A>: stringa che descrive un percorso in un oggetto dati o in un modello a oggetti generale. Il formato fornisce diverse convenzioni per l'attraversamento di un modello a oggetti che non può essere descritto in modo adeguato in questo argomento. Vedere [sintassi XAML di PropertyPath](propertypath-xaml-syntax.md).  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>: si escludono a vicenda rispetto a <xref:System.Windows.Data.Binding.ElementName%2A> e <xref:System.Windows.Data.Binding.Source%2A>; ognuna di queste proprietà di associazione rappresenta una particolare metodologia di associazione. Vedere [Cenni preliminari sul data binding](../data/data-binding-overview.md). Richiede un utilizzo [MarkupExtension di RelativeSource](relativesource-markupextension.md) annidato per specificare il valore.  
  
- <xref:System.Windows.Data.Binding.Source%2A>: si escludono a vicenda rispetto a <xref:System.Windows.Data.Binding.RelativeSource%2A> e <xref:System.Windows.Data.Binding.ElementName%2A>; ognuna di queste proprietà di associazione rappresenta una particolare metodologia di associazione. Vedere [Cenni preliminari sul data binding](../data/data-binding-overview.md). Richiede un utilizzo dell'estensione annidato, in genere un' [estensione di markup StaticResource](staticresource-markup-extension.md) che fa riferimento a un'origine dati oggetto da un dizionario risorse con chiave.  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>: stringa che descrive una convenzione di formato stringa per i dati associati. Si tratta di un concetto di associazione relativamente avanzato. vedere la pagina di riferimento per <xref:System.Windows.Data.BindingBase.StringFormat%2A>.  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: può essere impostato come `bindProp`=stringa `value` nell'espressione, ma dipende dal tipo di parametro passato. Se si passa un tipo riferimento per il valore, richiede un riferimento a un oggetto, ad esempio un' [estensione di markup StaticResource](staticresource-markup-extension.md)annidata.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *value* è un nome di costante dell'enumerazione <xref:System.Windows.Data.UpdateSourceTrigger>. Ad esempio `{Binding UpdateSourceTrigger=LostFocus}`. I controlli specifici hanno potenzialmente valori predefiniti diversi per questa proprietà di associazione. Vedere <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: booleano, può essere `true` o `false`. Il valore predefinito è `false`. Vedere la sezione Osservazioni.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: booleano, può essere `true` o `false`. Il valore predefinito è `false`. Vedere la sezione Osservazioni.  
  
- <xref:System.Windows.Data.Binding.XPath%2A>: stringa che descrive un percorso in XMLDOM di un'origine dati XML. Vedere [eseguire l'associazione a dati XML tramite un oggetto XmlDataProvider e query XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Di seguito sono riportate le proprietà di <xref:System.Windows.Data.Binding> che non è possibile impostare utilizzando il form `Binding` Markup Extension/`{Binding}` Expression.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: questa proprietà prevede un riferimento a un'implementazione di callback. Non è possibile fare riferimento a callback/metodi diversi dai gestori eventi nella sintassi XAML.  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>: la proprietà accetta una raccolta generica di oggetti <xref:System.Windows.Controls.ValidationRule>. Questo può essere espresso come elemento proprietà in un elemento <xref:System.Windows.Data.Binding> oggetto, ma non dispone di una tecnica di analisi degli attributi prontamente disponibile per l'utilizzo in un'espressione `Binding`. Per <xref:System.Windows.Data.Binding.ValidationRules%2A>, vedere l'argomento di riferimento.  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Note  
  
> [!IMPORTANT]
> In termini di precedenza delle proprietà di dipendenza, un'espressione `Binding` è equivalente a un valore impostato localmente. Se si imposta un valore locale per una proprietà che in precedenza aveva un'espressione `Binding`, il `Binding` viene completamente rimosso. Per altri dettagli, vedere [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md).  
  
 La descrizione di data binding a un livello di base non è descritta in questo argomento. Vedere [Cenni preliminari sul data binding](../data/data-binding-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding> e <xref:System.Windows.Data.PriorityBinding> non supportano una sintassi dell'estensione di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Si utilizzeranno invece gli elementi Property. Per <xref:System.Windows.Data.MultiBinding> e <xref:System.Windows.Data.PriorityBinding>, vedere gli argomenti di riferimento.  
  
 I valori booleani per XAML non fanno distinzione tra maiuscole e minuscole. È ad esempio possibile specificare `{Binding NotifyOnValidationError=true}` o `{Binding NotifyOnValidationError=True}`.  
  
 Le associazioni che coinvolgono la convalida dei dati vengono in genere specificate da un elemento `Binding` esplicito anziché come espressione `{Binding ...}` e l'impostazione di <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> o <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> in un'espressione non è comune. Ciò è dovuto al fatto che la proprietà complementare <xref:System.Windows.Data.Binding.ValidationRules%2A> non può essere impostata immediatamente nel formato di espressione. Per altre informazioni, vedere [implementare la convalida dell'associazione](../data/how-to-implement-binding-validation.md).  
  
 `Binding` è un'estensione di markup. Le estensioni di markup vengono in genere implementate quando è necessario eseguire l'escape dei valori di attributo in modo che non siano valori letterali o nomi di gestori e il requisito è più globale rispetto ai convertitori di tipi attribuiti a determinati tipi o proprietà. Tutte le estensioni di markup in XAML usano i caratteri `{` e `}` nella sintassi degli attributi, ovvero la convenzione con cui un processore XAML riconosce che un'estensione di markup deve elaborare il contenuto della stringa. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
 `Binding` è un'estensione di markup atipica in quanto la classe <xref:System.Windows.Data.Binding> che implementa la funzionalità di estensione per l'implementazione XAML di WPF implementa anche diversi altri metodi e proprietà non correlati a XAML. Gli altri membri hanno lo scopo di creare <xref:System.Windows.Data.Binding> una classe più versatile e autonoma in grado di risolvere molti scenari di data binding, oltre a funzionare come estensione di markup XAML.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.Binding>
- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)

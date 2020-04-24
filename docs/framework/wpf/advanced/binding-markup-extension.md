---
title: Associazione dell'estensione di markup
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: c6a424e085c7499db08d0a7e6b652f45fb2cdd70
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644077"
---
# <a name="binding-markup-extension"></a>Associazione dell'estensione di markup
Rinvia un valore della proprietà a un valore associato a dati, creando un oggetto espressione intermedio e interpretando il contesto dati che si applica all'elemento e alla relativa associazione in fase di esecuzione.  
  
## <a name="binding-expression-usage"></a>Utilizzo delle espressioni di associazioneBinding Expression Usage  
  
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
 In queste sintassi, `[]` `*` e non sono valori letterali. Fanno parte di una notazione per indicare che è possibile utilizzare `,` zero o più coppie di*valori* *bindProp,*`=`con un separatore tra di esse e le coppie di*valori* *bindProp*`=`precedenti.  
  
 Qualsiasi proprietà elencata nella sezione "Proprietà di associazione che possono essere impostate <xref:System.Windows.Data.Binding> con l'estensione di associazione" potrebbe invece essere impostata utilizzando gli attributi di un elemento oggetto. Tuttavia, questo non è realmente l'utilizzo dell'estensione di markup di <xref:System.Windows.Data.Binding> <xref:System.Windows.Data.Binding> , è solo l'elaborazione XAML generale degli attributi che impostano le proprietà della classe CLR. In altre `<Binding` parole, *bindProp1*`="`*value1* `"[` *bindPropN*`="`*valueN* `"]*/>` <xref:System.Windows.Data.Binding> è una sintassi `Binding` equivalente per gli attributi di utilizzo degli elementi oggetto anziché l'utilizzo di un'espressione. Per informazioni sull'utilizzo dell'attributo XAML di proprietà specifiche di <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.Binding> vedere la sezione "Utilizzo degli attributi XAML" della proprietà pertinente di nella libreria di classi .NET Framework.  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Nome della <xref:System.Windows.Data.Binding> proprietà <xref:System.Windows.Data.BindingBase> o da impostare. Non <xref:System.Windows.Data.Binding> tutte le proprietà `Binding` possono essere impostate con l'estensione e alcune proprietà sono impostabili all'interno di un'espressione `Binding` solo utilizzando ulteriori estensioni di markup annidate. Vedere la sezione "Proprietà di associazione che possono essere impostate con l'estensione di associazione".|  
|`value1, valueN`|Valore su cui impostare la proprietà. La gestione del valore dell'attributo è in definitiva <xref:System.Windows.Data.Binding> specifica per il tipo e la logica della proprietà specifica da impostare.|  
|`path`|Stringa di percorso che <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> imposta la proprietà implicita. Vedere anche [Sintassi XAML PropertyPath](propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>Unqualified : Binding  
 L'utilizzo `{Binding}` illustrato in "Utilizzo <xref:System.Windows.Data.Binding> dell'espressione di associazione" <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> `null`crea un oggetto con valori predefiniti, che include un'iniziale di . Ciò è ancora utile in <xref:System.Windows.Data.Binding> molti scenari, perché il creato <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> potrebbe <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> basarsi su proprietà di associazione dati chiave, ad esempio e impostato nel contesto dati di runtime. Per ulteriori informazioni sul concetto di contesto dati, vedere [Data Binding](../../../desktop-wpf/data/data-binding-overview.md).  
  
## <a name="implicit-path"></a>Percorso implicito  
 L'estensione `Binding` <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> di markup utilizza come una `Path=` "proprietà predefinita" concettuale, in cui non è necessario essere visualizzati nell'espressione. Se si `Binding` specifica un'espressione con un percorso implicito, il percorso `bindProp` = `value` implicito <xref:System.Windows.Data.Binding> deve essere visualizzato per primo nell'espressione, prima di qualsiasi altra coppia in cui la proprietà è specificata dal nome. Ad `{Binding PathString}`esempio: `PathString` , dove è una stringa che <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> viene <xref:System.Windows.Data.Binding> valutata come valore di nel creato dall'utilizzo dell'estensione di markup. È possibile aggiungere un percorso implicito con altre proprietà `{Binding LastName, Mode=TwoWay}`denominate dopo il separatore della virgola, ad esempio .  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Binding Properties That Can Be Set with the Binding Extension  
 La sintassi illustrata in `bindProp` = `value` questo argomento usa l'approssimazione generica, perché esistono molte proprietà di lettura/scrittura di o <xref:System.Windows.Data.BindingBase> <xref:System.Windows.Data.Binding> che possono essere impostate tramite la `Binding` sintassi di estensione/espressione di markup. Possono essere impostati in qualsiasi ordine, <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>ad eccezione di un file . (È possibile specificare `Path=`in modo esplicito , nel qual caso può essere impostato in qualsiasi ordine). Fondamentalmente, è possibile impostare zero o più `bindProp` = `value` delle proprietà nell'elenco sottostante, utilizzando coppie separate da virgole.  
  
 Molti di questi valori di proprietà richiedono tipi di oggetto che non supportano una conversione di tipo nativo da una sintassi di testo in XAML e pertanto richiedono estensioni di markup per essere impostati come valore di attributo. Controllare la sezione Utilizzo degli attributi XAML nella libreria di classi .NET Framework per ogni proprietà per ulteriori informazioni; la stringa utilizzata per la sintassi degli attributi XAML con o senza ulteriore utilizzo dell'estensione di markup è fondamentalmente la stessa del valore specificato in un'espressione, `Binding` con l'eccezione che non si inseriscono virgolette intorno a ciascuna `bindProp` = `value` nell'espressione. `Binding`  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: stringa che identifica un possibile gruppo di associazioni. Si tratta di un concetto vincolante relativamente avanzato; vedere la <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>pagina di riferimento per .  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: booleano, `true` può `false`essere o . Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.Converter%2A>: può essere `bindProp` = `value` impostato come stringa nell'espressione, ma per eseguire questa operazione è necessario un riferimento all'oggetto per il valore, ad esempio [un'estensione](staticresource-markup-extension.md)di markup StaticResource . Il valore in questo caso è un'istanza di una classe del convertitore personalizzata.  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>: impostabile nell'espressione come identificatore basato su standard; vedere l'argomento <xref:System.Windows.Data.Binding.ConverterCulture%2A>di riferimento per .  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>: può essere `bindProp` = `value` impostato come stringa nell'espressione, ma ciò dipende dal tipo del parametro passato. Se si passa un tipo di riferimento per il valore, questo utilizzo richiede un riferimento all'oggetto, ad esempio un'estensione di [markup StaticResource](staticresource-markup-extension.md)annidata.  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>: si escludono a vicenda rispetto a <xref:System.Windows.Data.Binding.RelativeSource%2A> e <xref:System.Windows.Data.Binding.Source%2A>; ognuna di queste proprietà di associazione rappresenta una particolare metodologia di associazione. Vedere [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: può essere `bindProp` = `value` impostato come stringa nell'espressione, ma ciò dipende dal tipo del valore passato. Se si passa un tipo di riferimento, è necessario un riferimento all'oggetto, ad esempio un'estensione di [markup StaticResource](staticresource-markup-extension.md)annidata.  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>: booleano, `true` può `false`essere o . Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.Mode%2A>: *valore* è un <xref:System.Windows.Data.BindingMode> nome costante dell'enumerazione. Ad esempio: `{Binding Mode=OneWay}`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: booleano, `true` può `false`essere o . Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: booleano, `true` può `false`essere o . Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: booleano, `true` può `false`essere o . Il valore predefinito è `false`.  
  
- <xref:System.Windows.Data.Binding.Path%2A>: stringa che descrive un percorso in un oggetto dati o in un modello a oggetti generale. Il formato fornisce diverse convenzioni diverse per l'attraversamento di un modello a oggetti che non può essere adeguatamente descritto in questo argomento. Vedere [Sintassi XAML PropertyPath](propertypath-xaml-syntax.md).  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>: si escludono a vicenda rispetto a con <xref:System.Windows.Data.Binding.ElementName%2A> e ; <xref:System.Windows.Data.Binding.Source%2A> ognuna di queste proprietà di associazione rappresenta una particolare metodologia di associazione. Vedere [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md). Richiede un utilizzo annidato [relativeA MarkupExtension](relativesource-markupextension.md) per specificare il valore.  
  
- <xref:System.Windows.Data.Binding.Source%2A>: si escludono a vicenda rispetto a <xref:System.Windows.Data.Binding.RelativeSource%2A> e <xref:System.Windows.Data.Binding.ElementName%2A>; ognuna di queste proprietà di associazione rappresenta una particolare metodologia di associazione. Vedere [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md). Richiede un utilizzo dell'estensione annidata, in genere [un'estensione](staticresource-markup-extension.md) di markup StaticResource che fa riferimento a un'origine dati oggetto da un dizionario risorse con chiave.  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>: stringa che descrive una convenzione di formato stringa per i dati associati. Si tratta di un concetto vincolante relativamente avanzato; vedere la <xref:System.Windows.Data.BindingBase.StringFormat%2A>pagina di riferimento per .  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: può essere `bindProp` = `value` impostato come stringa nell'espressione, ma ciò dipende dal tipo del parametro passato. Se si passa un tipo di riferimento per il valore, richiede un riferimento all'oggetto, ad esempio un'estensione di [markup StaticResource](staticresource-markup-extension.md)annidata .  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *valore* è un <xref:System.Windows.Data.UpdateSourceTrigger> nome costante dell'enumerazione. Ad esempio: `{Binding UpdateSourceTrigger=LostFocus}`. Controlli specifici hanno potenzialmente valori predefiniti diversi per questa proprietà di associazione. Vedere <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: booleano, `true` può `false`essere o . Il valore predefinito è `false`. Vedere la sezione Osservazioni.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: booleano, `true` può `false`essere o . Il valore predefinito è `false`. Vedere la sezione Osservazioni.  
  
- <xref:System.Windows.Data.Binding.XPath%2A>: stringa che descrive un percorso nel codice XMLDOM di un'origine dati XML. Vedere [Associazione a dati XML mediante xmlDataProvider e query XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Di seguito sono <xref:System.Windows.Data.Binding> riportate le `Binding` proprietà di`{Binding}` che non possono essere impostate utilizzando il modulo estensione/espressione di markup.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: questa proprietà prevede un riferimento a un'implementazione di callback. Non è possibile fare riferimento a callback/metodi diversi dai gestori eventi nella sintassi XAML.  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>: la proprietà accetta <xref:System.Windows.Controls.ValidationRule> una raccolta generica di oggetti. Questo potrebbe essere espresso come <xref:System.Windows.Data.Binding> elemento proprietà in un elemento oggetto, ma non ha `Binding` alcuna tecnica di analisi degli attributi prontamente disponibile per l'utilizzo in un'espressione. Vedere l'argomento di riferimento relativo <xref:System.Windows.Data.Binding.ValidationRules%2A>a .  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Osservazioni  
  
> [!IMPORTANT]
> In termini di precedenza della `Binding` proprietà di dipendenza, un'espressione è equivalente a un valore impostato localmente. Se si imposta un valore locale per `Binding` una `Binding` proprietà che in precedenza aveva un'espressione, l'oggetto viene completamente rimosso. Per altri dettagli, vedere [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md).  
  
 La descrizione dell'associazione dati a livello di base non viene trattata in questo argomento. Vedere [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding>e <xref:System.Windows.Data.PriorityBinding> non supportano una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintassi di estensione. È invece necessario utilizzare gli elementi di proprietà. Vedere gli <xref:System.Windows.Data.MultiBinding> argomenti <xref:System.Windows.Data.PriorityBinding>di riferimento per e .  
  
 I valori booleani per XAML non fanno distinzione tra maiuscole e minuscole. Ad esempio, è `{Binding NotifyOnValidationError=true}` `{Binding NotifyOnValidationError=True}`possibile specificare o .  
  
 Le associazioni che implicano la convalida `Binding` dei dati `{Binding ...}` sono in <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> genere <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> specificate da un elemento esplicito anziché come espressione e l'impostazione o in un'espressione non è comune. Ciò è dovuto <xref:System.Windows.Data.Binding.ValidationRules%2A> al fatto che la proprietà complementare non può essere impostata facilmente nel formato di espressione. Per ulteriori informazioni, vedere [Implementare la convalida dell'associazione](../data/how-to-implement-binding-validation.md).  
  
 `Binding` è un'estensione di markup. Le estensioni di markup vengono in genere implementate quando è necessario eseguire l'escape di valori di attributo diversi dai valori letterali o dai nomi dei gestori e il requisito è più globale rispetto ai convertitori di tipi attribuiti a determinati tipi o proprietà. Tutte le estensioni `{` di `}` markup in XAML usano i caratteri e nella sintassi degli attributi, ovvero la convenzione in base alla quale un processore XAML riconosce che un'estensione di markup deve elaborare il contenuto della stringa. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
 `Binding`è un'estensione di markup <xref:System.Windows.Data.Binding> atipica in quanto la classe che implementa la funzionalità di estensione per l'implementazione XAML di WPFWPF implementa anche diversi altri metodi e proprietà non correlati a XAML. Gli altri membri hanno <xref:System.Windows.Data.Binding> lo scopo di rendere una classe più versatile e indipendente in grado di risolvere molti scenari di associazione dati oltre a funzionare come estensione di markup XAML.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.Binding>
- [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)

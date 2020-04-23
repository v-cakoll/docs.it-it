---
title: Estensione del markup x:Type
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: f75d4e30dc41bbce995e466466c96c1a2830949b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071360"
---
# <a name="xtype-markup-extension"></a>Estensione del markup x:Type

Fornisce l'oggetto CLR <xref:System.Type> che è il tipo sottostante per un tipo XAML specificato.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object property="{x:Type prefix:typeNameValue}" .../>
```

## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto

```xaml
<x:Type TypeName="prefix:typeNameValue"/>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`prefix`|Facoltativa. Prefisso che esegue il mapping di uno spazio dei nomi XAML non predefinito. Specificare un prefisso spesso non è necessario. Vedere la sezione Osservazioni.|
|`typeNameValue`|Obbligatorio. Un nome di tipo resobile allo spazio dei nomi XAML predefinito corrente; o il prefisso `prefix` mappato specificato, se specificato, viene fornito.|

## <a name="remarks"></a>Osservazioni

L'estensione `x:Type` di markup ha `typeof()` una funzione simile `GetType` all'operatore in C , o l'operatore in Microsoft Visual Basic.

L'estensione `x:Type` di markup fornisce un comportamento di conversione from-string per le proprietà che accettano il tipo <xref:System.Type>. L'input è un tipo XAML. La relazione tra il tipo XAML <xref:System.Type> di input <xref:System.Type> e <xref:System.Xaml.XamlType.UnderlyingType%2A> CLR <xref:System.Xaml.XamlType>di output è <xref:System.Xaml.XamlType> che l'output è <xref:System.Windows.Markup.IXamlTypeResolver> l'input , dopo aver cercato la necessaria in base al contesto dello schema XAML e al servizio fornito dal contesto.

Nei servizi XAML .NET, la gestione di <xref:System.Windows.Markup.TypeExtension> questa estensione di markup è definita dalla classe .

Nelle implementazioni specifiche del framework, alcune proprietà che accettano <xref:System.Type> come valore possono accettare `Name`direttamente il nome del tipo (il valore stringa del tipo ). Tuttavia, l'implementazione di questo comportamento è uno scenario complesso. Per esempi, vedere la sezione "Note sull'utilizzo di WPF" di seguito.

La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `x:Type` viene assegnato come valore <xref:System.Windows.Markup.TypeExtension.TypeName%2A> della classe dell'estensione <xref:System.Windows.Markup.TypeExtension> sottostante. Nel contesto dello schema XAML predefinito per i servizi XAML .NET, basato <xref:System.Reflection.MemberInfo.Name%2A> sui tipi CLR, <xref:System.Reflection.MemberInfo.Name%2A> il valore di questo attributo è il tipo desiderato o contiene quello preceduto da un prefisso per un mapping dello spazio dei nomi XAML non predefinito.

L'estensione `x:Type` di markup può essere utilizzata nella sintassi degli elementi oggetto. In questo caso, è necessario <xref:System.Windows.Markup.TypeExtension.TypeName%2A> specificare il valore della proprietà per inizializzare correttamente l'estensione.

L'estensione `x:Type` di markup può essere utilizzata anche come un attributo dettagliato; tuttavia questo utilizzo non è tipico:`<object property="{x:Type TypeName=typeNameValue}" .../>`

## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF

### <a name="default-xaml-namespace-and-type-mapping"></a>Spazio dei nomi XAML predefinito e mapping dei tipiDefault XAML Namespace and Type Mapping

Lo spazio dei nomi XAML predefinito per la programmazione WPF contiene la maggior parte dei tipi XAML necessari per scenari XAML tipici; pertanto, è spesso possibile evitare i prefissi quando si fa riferimento a valori di tipo XAML. Potrebbe essere necessario eseguire il mapping di un prefisso se si fa riferimento a un tipo da un assembly personalizzato o per i tipi presenti in un assembly WPFWPF ma provengono da uno spazio dei nomi CLR che non è stato mappato allo spazio dei nomi XAML predefinito. Per altre informazioni sui prefissi, gli spazi dei nomi XAML e il mapping degli spazi dei nomi CLR, vedere [Spazi dei nomi XAML e Mapping degli spazi dei nomi per XAML WPF.](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)

### <a name="type-properties-that-support-typename-as-string"></a>Proprietà del tipo che supportano Typename-as-StringType Properties That Support Typename as-String

WPFWPF supporta le tecniche che consentono di <xref:System.Type> specificare `x:Type` il valore di alcune proprietà del tipo senza richiedere l'utilizzo di un'estensione di markup. È invece possibile specificare il valore come stringa che denomina il tipo. Esempi di <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> questo <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>sono e . Il supporto per questo comportamento non viene fornito tramite convertitori di tipi o estensioni di markup. Si tratta invece di un <xref:System.Windows.FrameworkElementFactory>comportamento di differimento implementato tramite .

Silverlight supporta una convenzione simile. Infatti, Silverlight attualmente `{x:Type}` non supporta nel supporto del `{x:Type}` linguaggio XAML e non accetta utilizzi al di fuori di alcune circostanze che hanno lo scopo di supportare la migrazione XAML WPF-Silverlight. Pertanto, il comportamento typename-as-string è incorporato in tutte <xref:System.Type> le valutazioni delle proprietà native di Silverlight in cui a è il valore.

## <a name="xaml-2009"></a>XAML 2009

XAML 2009 fornisce supporto aggiuntivo per i tipi generici e modifica il comportamento della funzionalità di `x:TypeArguments` e `x:Type` per fornire questo supporto.

- `x:TypeArguments`e l'elemento oggetto associato per la creazione di un oggetto generico può trovarsi su elementi diversi dalla radice. Per ulteriori informazioni, vedere la sezione "XAML 2009" della [direttiva x:TypeArguments](xtypearguments-directive.md).

- XAML 2009 supporta una sintassi per specificare il vincolo di un tipo generico nel markup. Questo può essere `x:TypeArguments`utilizzato `x:Type`da , da , o dalle due funzioni in combinazione.

- L'implementazione XAML WPF durante l'elaborazione di XAML 2009 per il caricamento <xref:System.Type>aggiunge anche questa funzionalità al comportamento di conversione dei tipi impliciti per determinate proprietà del framework che utilizzano il tipo .

In WPF, è possibile utilizzare le funzionalità di XAML 2009, ma solo per XAML separato (XAML che non è compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Style>
- [Applicazione di stili e modelli](../fundamentals/styles-templates-overview.md)
- [Panoramica di XAML (WPF)](../fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)

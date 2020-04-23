---
title: Direttiva x:TypeArguments
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 69da9329f140121b66c71d4cf2e99e9d14a1b207
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071353"
---
# <a name="xtypearguments-directive"></a>Direttiva x:TypeArguments

Passa gli argomenti di tipo vincolanti di un generico al costruttore del tipo generico.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`object`|Dichiarazione di elemento oggetto di un tipo XAML, supportata da un tipo generico CLR. Se `object` fa riferimento a un tipo XAML che `object` non proviene dallo spazio `object` dei nomi XAML predefinito, richiede un prefisso per indicare lo spazio dei nomi XAML laddove è presente.|
|`typeString`|Stringa che dichiara uno o più nomi di tipo XAML come stringhe, che fornisce gli argomenti di tipo per il tipo generico CLR. Vedere Osservazioni per ulteriori note sulla sintassi.|

## <a name="remarks"></a>Osservazioni

Nella maggior parte dei casi, i tipi XAML `typeString` utilizzati come elemento di informazioni in una stringa sono preceduti dal prefisso. Tipi tipici di vincoli <xref:System.Int32> generici CLR (ad esempio, e <xref:System.String>) provengono da librerie di classi base CLR. Tali librerie non sono mappate a tipici spazi dei nomi XAML predefiniti specifici del framework e pertanto richiedono un mapping del prefisso per l'utilizzo di XAML.

È possibile specificare più di un nome di tipo XAML utilizzando un delimitatore virgola.

Se i vincoli generici stessi utilizzano tipi generici, gli argomenti di tipo del vincolo annidato possono essere contenuti tra parentesi ().

Si noti `x:TypeArguments` che questa definizione di è specifica dei servizi XAML .NET e l'utilizzo del backup CLR. Una definizione a livello di linguaggio è disponibile nella [ \[sezione 5.3.11 di MS-XAML.\] ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))

## <a name="usage-examples"></a>Esempi di uso

Per questi esempi, si supponga che siano dichiarate le definizioni dello spazio dei nomi XAML seguenti:For these examples, assume that the following XAML namespace definitions are declared:

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a>Stringa\<elenco>

`<scg:List x:TypeArguments="sys:String" ...>`crea un'istanza di una nuova <xref:System.Collections.Generic.List%601> con un <xref:System.String> argomento di tipo.

### <a name="dictionarystringstring"></a>Stringa\<dizionario,> stringa

`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`crea un'istanza di una nuova <xref:System.Collections.Generic.Dictionary%602> con due <xref:System.String> argomenti di tipo.

### <a name="queuekeyvaluepairstringstring"></a>Coda<Stringa\<KeyValuePair,>> String

`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`crea un'istanza di <xref:System.Collections.Generic.Queue%601> un <xref:System.Collections.Generic.KeyValuePair%602> nuovo che ha <xref:System.String> <xref:System.String>un vincolo di con gli argomenti di tipo vincolo interno e .

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 e gli utilizzi XAML generici WPF

Per l'utilizzo di XAML 2006 e XAML utilizzato per `x:TypeArguments` le applicazioni WPFWPF, esistono le restrizioni seguenti per gli utilizzi di tipi generici da XAML in generale:

- Solo l'elemento radice di un file XAML può supportare un utilizzo XAML generico che fa riferimento a un tipo generico.

- L'elemento radice deve eseguire il mapping a un tipo generico con almeno un argomento di tipo. Un esempio è <xref:System.Windows.Navigation.PageFunction%601>. Le funzioni di pagina sono lo scenario principale per il supporto dell'utilizzo generico XAML in WPFWPF.

- L'elemento oggetto XAML dell'elemento radice per `x:Class`il generico deve inoltre dichiarare una classe parziale utilizzando . Questo vale anche se si definisce un'azione di compilazione WPFWPF.

- `x:TypeArguments`impossibile fare riferimento a vincoli generici annidati.

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 o XAML 2006 senza dipendenza WPF 3.0 o WPF 3.5

Nei servizi XAML .NET per XAML 2006 o XAML 2009, le restrizioni relative a WPF sull'utilizzo di XAML generico sono rilassate. È possibile creare un'istanza di un elemento oggetto generico in qualsiasi posizione nel markup XAML che il sistema di tipi di supporto e il modello a oggetti possono supportare.

Se si utilizza XAML 2009 anziché eseguire il mapping dei tipi di base CLR per ottenere tipi XAML per primitive di linguaggio comuni, è possibile utilizzare [tipi incorporati per le primitive](types-for-primitives.md) del linguaggio XAML comuni come elementi di informazioni in un `typeString`oggetto . Ad esempio, è possibile dichiarare quanto segue (mapping di prefisso non illustrato, ma x è lo spazio dei nomi XAML del linguaggio XAML per XAML 2009):For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

In WPF wpf e quando la destinazione di .NET Framework 4 o .NET Core 3.0 (o versione successiva), è possibile utilizzare le funzionalità di XAML 2009 con `x:TypeArguments` ma solo per XAML separato (XAML che non è compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009. Se è necessario compilare il codice XAML, è necessario operare in base alle restrizioni indicate nella sezione [XAML 2006 e in XAML generico.](#xaml-2006-and-wpf-generic-xaml-usages) BAML è supportato solo in .NET Framework.

## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](xclass-directive.md)
- [Estensione del markup x:Type](xtype-markup-extension.md)
- [Tipi incorporati per primitive del linguaggio XAML comuni](types-for-primitives.md)
- [Generics in XAML](generics.md)

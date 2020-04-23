---
title: Generics in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9354f74b978652c36df28a91a6b9db5cfff4bb1e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071738"
---
# <a name="generics-in-xaml"></a>Generics in XAML

I servizi XAML .NET implementati in <xref:System.Xaml?displayProperty=fullName> fornisce supporto per l'utilizzo di tipi CLR generici. Questo supporto include la specifica dei vincoli dei generics come argomento `Add` di tipo e l'applicazione del vincolo chiamando il metodo appropriato per i casi di raccolta generici. In questo argomento vengono descritti gli aspetti dell'uso e del riferimento a tipi generici in XAML.

## <a name="xtypearguments"></a>X:TypeArguments

`x:TypeArguments`è una direttiva definita dal linguaggio XAML. Quando viene utilizzato come membro di un tipo XAML supportato da un tipo generico, `x:TypeArguments` passa gli argomenti di tipo vincolante del generico al costruttore di supporto. Per la sintassi di riferimento relativa all'utilizzo `x:TypeArguments`di , che include esempi di sintassi da parte dei servizi XAML .NET, vedere [Direttiva x:TypeArguments](xtypearguments-directive.md).

Poiché `x:TypeArguments` accetta una stringa e dispone di supporto del convertitore di tipi, viene in genere dichiarato nell'utilizzo di XAML come attributo.

Nel flusso del nodo XAML, `x:TypeArguments` le informazioni <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> dichiarate da possono essere ottenute in una `StartObject` posizione nel flusso del nodo. Il valore <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> restituito di <xref:System.Xaml.XamlType> è un elenco di valori. Determinare se un tipo XAML rappresenta un tipo <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>generico può essere effettuata chiamando .

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>Regole e convenzioni di sintassi per i generics in XAMLRules and Syntax Conventions for Generics in XAML

In XAML, un tipo generico deve essere sempre rappresentato come un generico vincolato. Un generico non vincolato non è mai presente nel sistema di tipi XAML o in un flusso del nodo XAML e non può essere rappresentato nel markup XAML. È possibile fare riferimento a un generico all'interno della sintassi degli `x:TypeArguments`attributi XAML per `x:Type` i casi in cui è un vincolo di tipo annidato di un generico a cui fa riferimento o per i casi in cui fornisce un riferimento al tipo CLR per un tipo generico. I generics di riferimento <xref:System.Xaml.Schema.XamlTypeTypeConverter> sono supportati tramite la classe definita dai servizi XAML .NET.

La forma della sintassi degli attributi XAML abilitata modificando <xref:System.Xaml.Schema.XamlTypeTypeConverter> la convenzione di sintassi MSIL / CLR tipica che usa le parentesi angolari per i tipi e i vincoli dei generics e sostituisce invece le parentesi per il contenitore di vincoli. Per un esempio, vedere [X:TypeArguments (direttiva).](xtypearguments-directive.md)

## <a name="generics-and-xaml-2009-features"></a>Funzionalità generics e XAML 2009

Se si utilizza XAML 2009 anziché eseguire il mapping dei tipi di base CLR per ottenere tipi XAML per `x:TypeArguments`le primitive del linguaggio comuni, è possibile utilizzare i tipi incorporati XAML [2009](types-for-primitives.md) come elementi di informazioni in . Ad esempio, è possibile dichiarare quanto segue (mapping dei prefissi non visualizzati, ma è lo spazio dei nomi XAML del linguaggio XAML per XAML 2009):For example, you could declare the following (prefix mappings not shown, but `x` is the XAML language XAML namespace for XAML 2009):

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a>Generics Support in WPF

Per l'utilizzo di XAML 2006 quando si imposta specificamente come `x:TypeArguments`destinazione WPF, [x:Class](xclass-directive.md) deve essere fornito anche sullo stesso elemento di , e tale elemento deve essere l'elemento radice in un documento XAML. L'elemento radice deve eseguire il mapping a un tipo generico con almeno un argomento di tipo. Un esempio è <xref:System.Windows.Navigation.PageFunction%601>.

Le possibili soluzioni alternative per supportare gli utilizzi generici includono la definizione di un'estensione di markup personalizzata in grado di restituire tipi generici o fornire una definizione di classe di wrapping che deriva da un tipo generico ma appiattisce il vincolo generico nella propria definizione di classe.

In WPFWPF è possibile usare le `x:TypeArguments`funzionalità XAML 2009 con , ma solo per XAML separato (XAML che non è compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.

I flussi di lavoro personalizzati in Windows Workflow Foundation per .NET Framework 3.5 non supportano l'utilizzo di XAML generico.

## <a name="see-also"></a>Vedere anche

- [Direttiva x:TypeArguments](xtypearguments-directive.md)
- [Direttiva x:Class](xclass-directive.md)
- [Tipi incorporati per primitive del linguaggio XAML comuni](types-for-primitives.md)

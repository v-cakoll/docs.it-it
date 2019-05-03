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
ms.openlocfilehash: 1d1b10b4da1263843bdce5447f0716569c7700e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982592"
---
# <a name="xtypearguments-directive"></a>Direttiva x:TypeArguments
Passa vincoli di tipo generico per il costruttore del tipo generico.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`object`|Una dichiarazione di elemento oggetto di un tipo XAML, supportata da un tipo generico di CLR. Se `object` fa riferimento a un tipo XAML non dello spazio dei nomi XAML predefinito `object` richiede un prefisso per indicare lo spazio dei nomi XAML in cui `object` esiste.|  
|`typeString`|Stringa che dichiara uno o più XAML digitare nomi sotto forma di stringhe, che fornisce gli argomenti tipo per il tipo generico di CLR. Vedere la sezione Osservazioni per le note sulla sintassi aggiuntiva.|  
  
## <a name="remarks"></a>Note  
 Nella maggior parte dei casi, i tipi di XAML vengono usati come un elemento di informazione in un `typeString` stringa hanno il prefisso. I tipi tipici dei vincoli generici di Common Language Runtime (ad esempio, <xref:System.Int32> e <xref:System.String>) provengono da librerie di classi base di Common Language Runtime. Tali librerie non sono spazi dei nomi XAML predefinito specifico del framework mappate al tipico e pertanto, richiedono un mapping del prefisso per l'utilizzo XAML.  
  
 È possibile specificare più di un nome di tipo XAML usando una virgola di delimitazione.  
  
 Se i vincoli generici usano tipi generici, gli argomenti di tipo di vincolo annidata possono essere contenuti in parentesi ().  
  
 Si noti che questa definizione di `x:TypeArguments` è specifico di servizi XAML di .NET Framework e usando il supporto CLR. Una definizione a livello di linguaggio è reperibile nel [ \[MS-XAML\] sezione 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="usage-examples"></a>Esempi di utilizzo  
 Per questi esempi, si supponga che siano dichiarate per le definizioni dello spazio dei nomi XAML seguenti:  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a>Elenco\<stringa >  
 `<scg:List x:TypeArguments="sys:String" ...>` Crea un'istanza di una nuova <xref:System.Collections.Generic.List%601> con un <xref:System.String> argomento di tipo.  
  
### <a name="dictionarystringstring"></a>Dizionario\<String, String >  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` Crea un'istanza di una nuova <xref:System.Collections.Generic.Dictionary%602> con due <xref:System.String> gli argomenti di tipo.  
  
### <a name="queuekeyvaluepairstringstring"></a>Coda di < oggetto KeyValuePair\<String, String >>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` Crea un'istanza di una nuova <xref:System.Collections.Generic.Queue%601> che ha un vincolo <xref:System.Collections.Generic.KeyValuePair%602> con gli argomenti di tipo di vincolo interno <xref:System.String> e <xref:System.String>.  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>Utilizzi XAML generica di XAML 2006 e WPF  
 Per l'uso di XAML 2006 e XAML che viene usato per le applicazioni WPF, le limitazioni seguenti per `x:TypeArguments` e gli utilizzi di tipo generico da XAML in generale:  
  
- Solo l'elemento radice di un file XAML può supportare un utilizzo generico di XAML che fa riferimento a un tipo generico.  
  
- L'elemento radice deve eseguire il mapping a un tipo generico con almeno un argomento di tipo. Un esempio è <xref:System.Windows.Navigation.PageFunction%601>. Le funzioni di pagina sono lo scenario principale per il supporto di utilizzo generico di XAML in WPF.  
  
- L'elemento oggetto XAML elemento radice per il tipo generico debba anche dichiarare una classe parziale che usa `x:Class`. Questo vale anche se la definizione di un controllo WPF di azione di compilazione.  
  
- `x:TypeArguments` non è possibile fare riferimento a vincoli generici annidati.  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 o XAML 2006 senza WPF 3.0 o 3.5 WPF delle dipendenze  
 Nei servizi XAML di .NET Framework per XAML 2006 o XAML 2009, sono flessibili le restrizioni sull'utilizzo XAML generico basate su WPF. È possibile creare un'istanza di un elemento oggetto generico in qualsiasi posizione nel markup XAML in grado di supportare il modello di sistema e l'oggetto di tipo sottostante.  
  
 Se si utilizza XAML 2009, anziché eseguire il mapping di CLR di base dei tipi per ottenere i tipi XAML per primitive di linguaggio comuni, è possibile usare [i tipi nativi per primitive del linguaggio XAML comuni](built-in-types-for-common-xaml-language-primitives.md) come elementi di informazione in un `typeString`. Ad esempio, si potrebbe dichiarare seguenti (non illustrato mapping del prefisso, ma x è lo spazio dei nomi XAML del linguaggio XAML di XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 In WPF e quando la destinazione [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], è possibile usare le funzionalità di XAML 2009 con `x:TypeArguments` ma solo per XAML loose (XAML non è compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009. Se è necessario di una compilazione di markup di XAML, è necessario operare con le restrizioni indicate nella sezione "XAML 2006 e WPF XAML utilizzi generici".  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](x-class-directive.md)
- [Estensione di markup x:Type](x-type-markup-extension.md)
- [Tipi incorporati per primitive del linguaggio XAML comuni](built-in-types-for-common-xaml-language-primitives.md)
- [Generics in XAML](generics-in-xaml.md)

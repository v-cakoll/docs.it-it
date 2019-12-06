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
ms.openlocfilehash: 2e64c716ee85934bf02c016ee408b8e5f612a819
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837194"
---
# <a name="xtypearguments-directive"></a>Direttiva x:TypeArguments
Passa gli argomenti di tipo vincolante di un oggetto generico al costruttore del tipo generico.  
  
## <a name="xaml-attribute-usage"></a>Utilizzo della sintassi XAML per attributi  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a>Valor XAML  
  
|||  
|-|-|  
|`object`|Dichiarazione di elemento oggetto di un tipo XAML, supportata da un tipo generico CLR. Se `object` fa riferimento a un tipo XAML che non si trova nello spazio dei nomi XAML predefinito, `object` richiede un prefisso per indicare lo spazio dei nomi XAML in cui `object` esiste.|  
|`typeString`|Stringa che dichiara uno o più nomi di tipi XAML come stringhe, che fornisce gli argomenti di tipo per il tipo generico CLR. Per ulteriori note sulla sintassi, vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 Nella maggior parte dei casi, i tipi XAML usati come elemento informazioni in una stringa `typeString` sono preceduti dal prefisso. I tipi tipici di vincoli CLR generici (ad esempio <xref:System.Int32> e <xref:System.String>) provengono dalle librerie di classi di base CLR. Tali librerie non sono mappate a spazi dei nomi XAML predefiniti specifici del Framework e pertanto richiedono un mapping di prefisso per l'utilizzo di XAML.  
  
 È possibile specificare più di un nome di tipo XAML usando un delimitatore di virgola.  
  
 Se i vincoli generici usano tipi generici, gli argomenti del tipo di vincolo annidato possono essere racchiusi tra parentesi ().  
  
 Si noti che questa definizione di `x:TypeArguments` è specifica di .NET Framework servizi XAML e di utilizzo del supporto CLR. Una definizione a livello di linguaggio si trova nella [sezione\[MS-XAML\] 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
## <a name="usage-examples"></a>Esempi di uso  
 Per questi esempi, si supponga che siano dichiarate le seguenti definizioni dello spazio dei nomi XAML:  
  
```xaml  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a>Elenca\<stringa >  
 `<scg:List x:TypeArguments="sys:String" ...>` crea un'istanza di una nuova <xref:System.Collections.Generic.List%601> con un argomento di tipo <xref:System.String>.  
  
### <a name="dictionarystringstring"></a>Dictionary\<String, String >  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` crea un'istanza di una nuova <xref:System.Collections.Generic.Dictionary%602> con due argomenti di tipo <xref:System.String>.  
  
### <a name="queuekeyvaluepairstringstring"></a>Coda < KeyValuePair\<stringa, stringa > >  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` crea un'istanza di un nuovo <xref:System.Collections.Generic.Queue%601> con un vincolo di <xref:System.Collections.Generic.KeyValuePair%602> con gli argomenti di tipo di vincolo interno <xref:System.String> e <xref:System.String>.  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 e utilizzi XAML generici WPF  
 Per l'utilizzo di XAML 2006 e XAML usato per le applicazioni WPF, esistono le restrizioni seguenti per gli utilizzi di tipi `x:TypeArguments` e generici di XAML in generale:  
  
- Solo l'elemento radice di un file XAML può supportare un utilizzo generico di XAML che fa riferimento a un tipo generico.  
  
- L'elemento radice deve essere mappato a un tipo generico con almeno un argomento di tipo. Un esempio è <xref:System.Windows.Navigation.PageFunction%601>. Le funzioni di pagina rappresentano lo scenario principale per il supporto di utilizzo generico XAML in WPF.  
  
- L'elemento dell'oggetto XAML dell'elemento radice per il generico deve anche dichiarare una classe parziale usando `x:Class`. Questo vale anche se si definisce un'azione di compilazione WPF.  
  
- `x:TypeArguments` non può fare riferimento a vincoli generici annidati.  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 o XAML 2006 senza dipendenza WPF 3,0 o WPF 3,5  
 In .NET Framework i servizi XAML per XAML 2006 o XAML 2009, le restrizioni correlate a WPF sull'utilizzo generico di XAML sono rilassate. È possibile creare un'istanza di un elemento oggetto generico in qualsiasi posizione nel markup XAML in grado di supportare il sistema di tipi e il modello a oggetti supportati.  
  
 Se si usa XAML 2009 anziché eseguire il mapping dei tipi di base CLR per ottenere i tipi XAML per le primitive di linguaggio comuni, è possibile usare i [tipi incorporati per le primitive del linguaggio XAML comuni](built-in-types-for-common-xaml-language-primitives.md) come elementi informativi in una `typeString`. Ad esempio, è possibile dichiarare quanto segue (i mapping di prefisso non sono visualizzati, ma x è lo spazio dei nomi XAML del linguaggio XAML per XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 In WPF e quando la destinazione è .NET Framework 4, è possibile usare le funzionalità XAML 2009 insieme a `x:TypeArguments` ma solo per XAML separato (XAML non compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009. Se è necessario eseguire il markup per compilare il codice XAML, è necessario operare con le restrizioni indicate nella sezione "XAML 2006 e WPF Generic XAML usages".  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](x-class-directive.md)
- [Estensione di markup x:Type](x-type-markup-extension.md)
- [Tipi incorporati per primitive del linguaggio XAML comuni](built-in-types-for-common-xaml-language-primitives.md)
- [Generics in XAML](generics-in-xaml.md)

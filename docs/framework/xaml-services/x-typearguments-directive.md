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
ms.openlocfilehash: a2a960870d368e57272b3368e69eb38ebbe2ba5d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053709"
---
# <a name="xtypearguments-directive"></a>Direttiva x:TypeArguments
Passa gli argomenti di tipo vincolante di un oggetto generico al costruttore del tipo generico.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`object`|Dichiarazione di elemento oggetto di un tipo XAML, supportata da un tipo generico CLR. Se `object` fa riferimento a un tipo XAML che non si trova nello spazio dei nomi `object` XAML predefinito, richiede un prefisso per indicare lo `object` spazio dei nomi XAML in cui è presente.|  
|`typeString`|Stringa che dichiara uno o più nomi di tipi XAML come stringhe, che fornisce gli argomenti di tipo per il tipo generico CLR. Per ulteriori note sulla sintassi, vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 Nella maggior parte dei casi, i tipi XAML usati come elemento informazioni in una `typeString` stringa sono preceduti dal prefisso. I tipi tipici di vincoli CLR generici (ad <xref:System.Int32> esempio <xref:System.String>e) provengono dalle librerie di classi di base CLR. Tali librerie non sono mappate a spazi dei nomi XAML predefiniti specifici del Framework e pertanto richiedono un mapping di prefisso per l'utilizzo di XAML.  
  
 È possibile specificare più di un nome di tipo XAML usando un delimitatore di virgola.  
  
 Se i vincoli generici usano tipi generici, gli argomenti del tipo di vincolo annidato possono essere racchiusi tra parentesi ().  
  
 Si noti che questa definizione `x:TypeArguments` di è specifica per .NET Framework servizi XAML e per l'utilizzo del supporto CLR. Una definizione a livello di linguaggio si trova nella [ \[sezione MS-\] XAML 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="usage-examples"></a>Esempi di utilizzo  
 Per questi esempi, si supponga che siano dichiarate le seguenti definizioni dello spazio dei nomi XAML:  
  
```xaml  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a>>\<Stringa elenco  
 `<scg:List x:TypeArguments="sys:String" ...>`Crea un'istanza di <xref:System.Collections.Generic.List%601> un nuovo <xref:System.String> oggetto con un argomento di tipo.  
  
### <a name="dictionarystringstring"></a>Stringa\<del dizionario, stringa >  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`Crea un'istanza di <xref:System.Collections.Generic.Dictionary%602> un nuovo <xref:System.String> oggetto con due argomenti di tipo.  
  
### <a name="queuekeyvaluepairstringstring"></a>Queue < stringa\<KeyValuePair, stringa > >  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`Crea un'istanza di <xref:System.Collections.Generic.Queue%601> un nuovo oggetto con un <xref:System.Collections.Generic.KeyValuePair%602> vincolo con gli argomenti <xref:System.String> di tipo di <xref:System.String>vincolo interno e.  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 e utilizzi XAML generici WPF  
 Per l'utilizzo di XAML 2006 e XAML usato per le applicazioni WPF, esistono le restrizioni seguenti per `x:TypeArguments` gli utilizzi di tipi generici e di XAML in generale:  
  
- Solo l'elemento radice di un file XAML può supportare un utilizzo generico di XAML che fa riferimento a un tipo generico.  
  
- L'elemento radice deve essere mappato a un tipo generico con almeno un argomento di tipo. Un esempio è <xref:System.Windows.Navigation.PageFunction%601>. Le funzioni di pagina rappresentano lo scenario principale per il supporto di utilizzo generico XAML in WPF.  
  
- L'elemento dell'oggetto XAML dell'elemento radice per il generico deve anche dichiarare una classe `x:Class`parziale usando. Questo vale anche se si definisce un'azione di compilazione WPF.  
  
- `x:TypeArguments`non è possibile fare riferimento a vincoli generici annidati.  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 o XAML 2006 senza dipendenza WPF 3,0 o WPF 3,5  
 In .NET Framework i servizi XAML per XAML 2006 o XAML 2009, le restrizioni correlate a WPF sull'utilizzo generico di XAML sono rilassate. È possibile creare un'istanza di un elemento oggetto generico in qualsiasi posizione nel markup XAML in grado di supportare il sistema di tipi e il modello a oggetti supportati.  
  
 Se si usa XAML 2009 anziché eseguire il mapping dei tipi di base CLR per ottenere i tipi XAML per le primitive di linguaggio comuni, è possibile usare i [tipi incorporati per le primitive del linguaggio XAML comuni](built-in-types-for-common-xaml-language-primitives.md) come elementi informativi in un oggetto `typeString`. Ad esempio, è possibile dichiarare quanto segue (i mapping di prefisso non sono visualizzati, ma x è lo spazio dei nomi XAML del linguaggio XAML per XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 In WPF e quando la destinazione è .NET Framework 4, è possibile usare le funzionalità XAML 2009 `x:TypeArguments` insieme a, ma solo per XAML separato (XAML non compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009. Se è necessario eseguire il markup per compilare il codice XAML, è necessario operare con le restrizioni indicate nella sezione "XAML 2006 e WPF Generic XAML usages".  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](x-class-directive.md)
- [Estensione di markup x:Type](x-type-markup-extension.md)
- [Tipi incorporati per primitive del linguaggio XAML comuni](built-in-types-for-common-xaml-language-primitives.md)
- [Generics in XAML](generics-in-xaml.md)

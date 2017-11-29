---
title: Direttiva x:TypeArguments
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
caps.latest.revision: "18"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: a63a8080c71ad026664e2e14fc1762fcdd4bdb36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xtypearguments-directive"></a>Direttiva x:TypeArguments
Passa vincoli di tipo generico per il costruttore del tipo generico.  
  
## <a name="xaml-attribute-usage"></a>Utilizzo della sintassi XAML per gli attributi  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`object`|Una dichiarazione di elemento oggetto di un tipo XAML, supportato da un tipo generico di CLR. Se `object` fa riferimento a un tipo XAML non dallo spazio dei nomi XAML predefinito, `object` richiede un prefisso per indicare lo spazio dei nomi XAML in cui `object` esiste.|  
|`typeString`|Una stringa che dichiara uno o più XAML digitare i nomi sotto forma di stringhe, che fornisce gli argomenti di tipo per il tipo generico di CLR. Per le note sulla sintassi aggiuntiva, vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 Nella maggior parte dei casi, i tipi XAML che vengono utilizzati come un elemento di informazione in un `typeString` stringa sono precedute dal prefisso. I tipi tipici di vincoli generici (ad esempio, <xref:System.Int32> e <xref:System.String>) provengono dalle librerie di classe di base di Common Language Runtime. Tali librerie non sono spazi dei nomi XAML mappato al tipico specifiche del framework predefinito e pertanto richiedono un mapping del prefisso per l'utilizzo della sintassi XAML.  
  
 È possibile specificare più di un nome di tipo XAML con una virgola di delimitazione.  
  
 Se i vincoli generici utilizzano tipi generici, gli argomenti di tipo annidato vincolo possono essere contenuti in parentesi ().  
  
 Si noti che questa definizione di `x:TypeArguments` è specifico di servizi XAML di .NET Framework e utilizzando il supporto CLR. Una definizione a livello di linguaggio è reperibile [ \[MS-XAML\] sezione 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="usage-examples"></a>Esempi di utilizzo  
 Per questi esempi, si supponga che le seguenti definizioni dello spazio dei nomi XAML vengono dichiarate:  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a>Elenco\<stringa >  
 `<scg:List x:TypeArguments="sys:String" ...>`Crea un nuovo <xref:System.Collections.Generic.List%601> con un <xref:System.String> argomento di tipo.  
  
### <a name="dictionarystringstring"></a>Dizionario\<String, String >  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`Crea un nuovo <xref:System.Collections.Generic.Dictionary%602> con due <xref:System.String> gli argomenti di tipo.  
  
### <a name="queuekeyvaluepairstringstring"></a>Coda < KeyValuePair\<String, String >>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`Crea un nuovo <xref:System.Collections.Generic.Queue%601> che dispone di un vincolo di <xref:System.Collections.Generic.KeyValuePair%602> con gli argomenti di tipo di vincolo interna <xref:System.String> e <xref:System.String>.  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>Utilizzi XAML generico di XAML 2006 e WPF  
 Per l'utilizzo di XAML 2006 e XAML che viene utilizzato per le applicazioni WPF, le limitazioni seguenti per `x:TypeArguments` e dei relativi utilizzi di tipo generico da XAML in generale:  
  
-   Solo l'elemento radice di un file XAML può supportare un utilizzo di XAML generico che fa riferimento a un tipo generico.  
  
-   L'elemento radice deve eseguire il mapping a un tipo generico con almeno un argomento di tipo. Un esempio è <xref:System.Windows.Navigation.PageFunction%601>. Le funzioni di pagina sono lo scenario principale per il supporto di utilizzo generico di XAML in WPF.  
  
-   L'elemento oggetto XAML elemento radice per il tipo generico è inoltre necessario dichiarare una classe parziale utilizzando `x:Class`. Questo vale anche se la definizione di un controllo WPF di azione di compilazione.  
  
-   `x:TypeArguments`non è possibile fare riferimento a vincoli generici annidati.  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 o XAML 2006 senza WPF 3.0 o 3.5 WPF dipendenza  
 Nei servizi XAML di .NET Framework per XAML 2006 o XAML 2009, le restrizioni relative a WPF sull'utilizzo di XAML generico sono flessibili. È possibile creare un'istanza di un elemento oggetto generico in qualsiasi posizione nel markup XAML in grado di supportare il modello di sistema e l'oggetto di tipo sottostante.  
  
 Se si utilizza XAML 2009, anziché eseguire il mapping CLR tipi di base di ottenere tipi XAML per le primitive di linguaggio comune, è possibile utilizzare [tipi incorporati per primitive del linguaggio XAML comuni](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) come elementi di informazioni in un `typeString`. Ad esempio, è possibile dichiarare le operazioni seguenti (mapping del prefisso non visualizzati, ma x è lo spazio dei nomi XAML del linguaggio XAML per XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 In WPF e quando la destinazione [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], è possibile utilizzare le funzionalità di XAML 2009 con `x:TypeArguments` ma solo per XAML separato (XAML non compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009. Se è necessario di una compilazione di markup XAML, è necessario operare con le restrizioni indicate nella sezione "And WPF generica sintassi XAML per gli utilizzi di XAML 2006".  
  
## <a name="see-also"></a>Vedere anche  
 [Direttiva x:Class](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Estensione di markup x:Type](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [Tipi incorporati per primitive del linguaggio XAML comuni](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)  
 [Generics in XAML](../../../docs/framework/xaml-services/generics-in-xaml.md)

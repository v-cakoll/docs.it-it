---
title: Convenzioni per l'utilizzo di maiuscole e minuscole
description: Applicare le convenzioni di utilizzo delle maiuscole per identificatori, parole composte e termini comuni. Informazioni sul funzionamento della distinzione tra maiuscole e minuscole in .NET.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 4903dc587d84ef36bfaa641cfbda59484266c23c
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767793"
---
# <a name="capitalization-conventions"></a>Convenzioni per l'utilizzo di maiuscole e minuscole
Le linee guida in questo capitolo definiscono un metodo semplice per l'utilizzo di case che, quando vengono applicate in modo coerente, rendono facili da leggere gli identificatori di tipi, membri e parametri.

## <a name="capitalization-rules-for-identifiers"></a>Regole relative alle maiuscole per gli identificatori
 Per distinguere le parole in un identificatore, sfruttare la prima lettera di ogni parola nell'identificatore. Non usare caratteri di sottolineatura per distinguere le parole, o per tale importanza, in qualsiasi punto degli identificatori. Esistono due modi appropriati per capitalizzare gli identificatori, a seconda dell'utilizzo dell'identificatore:

- Sistema Pascal

- camelCasing

 La convenzione sistema Pascal, usata per tutti gli identificatori eccetto i nomi di parametro, converte in maiuscolo il primo carattere di ogni parola (inclusi gli acronimi per due lettere di lunghezza), come illustrato negli esempi seguenti:

 `PropertyDescriptor`
 `HtmlTag`

 Viene creato un caso speciale per gli acronimi di due lettere in cui entrambe le lettere sono in maiuscolo, come illustrato nell'identificatore seguente:

 `IOStream`

 La convenzione camelCasing, usata solo per i nomi dei parametri, converte in maiuscolo il primo carattere di ogni parola eccetto la prima parola, come illustrato negli esempi seguenti. Come illustrato nell'esempio, gli acronimi a due lettere che iniziano un identificatore con distinzione tra maiuscole e minuscole sono entrambi minuscoli.

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 ✔️ utilizzare sistema Pascal per tutti i nomi di membri, tipi e spazi dei nomi pubblici costituiti da più parole.

 ✔️ utilizzare camelCasing per i nomi dei parametri.

 Nella tabella seguente vengono descritte le regole di utilizzo delle maiuscole per diversi tipi di identificatori.

|Identificatore|Maiuscole/minuscole|Esempio|
|----------------|------------|-------------|
|Spazio dei nomi|Pascal|`namespace System.Security { ... }`|
|Type|Pascal|`public class StreamReader { ... }`|
|Interfaccia|Pascal|`public interface IEnumerable { ... }`|
|Metodo|Pascal|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|Proprietà|Pascal|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|Evento|Pascal|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|Campo|Pascal|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|Valore enum|Pascal|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|Parametro|notazione Camel|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a>Capitalizzazione di parole composte e termini comuni
 La maggior parte dei termini composti viene considerata come una singola parola per scopi di maiuscole.

 ❌NON capitalizzare ogni parola nelle parole composte a forma chiusa.

 Si tratta di parole composte scritte come una singola parola, ad esempio endpoint. Ai fini delle linee guida per l'utilizzo di maiuscole e minuscole, considerare una parola composta a forma chiusa come una singola parola. Usare un dizionario corrente per determinare se una parola composta viene scritta in formato chiuso.

|Pascal|notazione Camel|Not|
|------------|-----------|---------|
|`BitFlag`|`bitFlag`|`Bitflag`|
|`Callback`|`callback`|`CallBack`|
|`Canceled`|`canceled`|`Cancelled`|
|`DoNot`|`doNot`|`Don't`|
|`Email`|`email`|`EMail`|
|`Endpoint`|`endpoint`|`EndPoint`|
|`FileName`|`fileName`|`Filename`|
|`Gridline`|`gridline`|`GridLine`|
|`Hashtable`|`hashtable`|`HashTable`|
|`Id`|`id`|`ID`|
|`Indexes`|`indexes`|`Indices`|
|`LogOff`|`logOff`|`LogOut`|
|`LogOn`|`logOn`|`LogIn`|
|`Metadata`|`metadata`|`MetaData, metaData`|
|`Multipanel`|`multipanel`|`MultiPanel`|
|`Multiview`|`multiview`|`MultiView`|
|`Namespace`|`namespace`|`NameSpace`|
|`Ok`|`ok`|`OK`|
|`Pi`|`pi`|`PI`|
|`Placeholder`|`placeholder`|`PlaceHolder`|
|`SignIn`|`signIn`|`SignOn`|
|`SignOut`|`signOut`|`SignOff`|
|`UserName`|`userName`|`Username`|
|`WhiteSpace`|`whiteSpace`|`Whitespace`|
|`Writable`|`writable`|`Writeable`|

## <a name="case-sensitivity"></a>Maiuscole/minuscole
 Le lingue che possono essere eseguite su CLR non devono supportare la distinzione tra maiuscole e minuscole, sebbene alcune operazioni. Anche se il linguaggio lo supporta, altre lingue che potrebbero accedere al Framework non lo sono. Le API che sono accessibili esternamente, pertanto, non possono basarsi solo su case per distinguere tra due nomi nello stesso contesto.

 ❌Non presupporre che tutti i linguaggi di programmazione fanno distinzione tra maiuscole e minuscole. Ma non lo sono. I nomi non possono differire solo per caso.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](index.md)
- [Linee guida per la denominazione](naming-guidelines.md)

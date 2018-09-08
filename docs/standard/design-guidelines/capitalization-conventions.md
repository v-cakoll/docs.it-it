---
title: Convenzioni per l'utilizzo di maiuscole e minuscole
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 070fc69728c2cb38e465dab9f6f591a77a857531
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210351"
---
# <a name="capitalization-conventions"></a>Convenzioni per l'utilizzo di maiuscole e minuscole
Le linee guida in questo capitolo disporre un metodo semplice per l'utilizzo di case che, quando applicata in modo coerente, verificare gli identificatori per i tipi, membri e parametri di facile lettura.  
  
## <a name="capitalization-rules-for-identifiers"></a>Regole di maiuscole/minuscole per gli identificatori  
 Per differenziare le parole in un identificatore, converte in maiuscolo la prima lettera di ogni parola nell'identificatore. Non usare caratteri di sottolineatura per differenziare le parole o parimenti, in qualsiasi punto negli identificatori. Esistono due modi appropriati da convertire in maiuscolo identificatori, a seconda dell'utilizzo dell'identificatore:  
  
-   Sistema Pascal  
  
-   notazione camel  
  
 La convenzione, il sistema Pascal utilizzata per tutti gli identificatori, ad eccezione di nomi di parametro, converte in maiuscolo il primo carattere di ogni parola (inclusi gli acronimi su due lettere), come illustrato negli esempi seguenti:  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 Un caso speciale viene effettuato per due lettere acronimi in cui sia le lettere sono in maiuscolo, come illustrato nell'identificatore seguente:  
  
 `IOStream`  
  
 La convenzione camel, usata solo per i nomi dei parametri, converte in maiuscolo il primo carattere di ogni parola eccetto la prima parola, come illustrato negli esempi seguenti. Come illustrato anche nell'esempio, gli acronimi di due lettere che iniziano un identificatore di maiuscole/minuscole camel sono entrambi caratteri minuscoli.  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 **✓ DO** utilizzare il sistema Pascal per tutti i membri, tipo e spazio dei nomi nomi pubblici composta da più parole.  
  
 **✓ DO** utilizzare camel per i nomi dei parametri.  
  
 Nella tabella seguente vengono descritte le regole di maiuscole/minuscole per i diversi tipi di identificatori.  
  
|Identificatore|Maiuscole/minuscole|Esempio|  
|----------------|------------|-------------|  
|Spazio dei nomi|Convenzione Pascal|`namespace System.Security { ... }`|  
|Tipo|Convenzione Pascal|`public class StreamReader { ... }`|  
|Interfaccia|Convenzione Pascal|`public interface IEnumerable { ... }`|  
|Metodo|Convenzione Pascal|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|Proprietà|Convenzione Pascal|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|event|Convenzione Pascal|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|Campo|Convenzione Pascal|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|Valore enum|Convenzione Pascal|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|Parametro|Notazione camel|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a>Sfruttando le parole composte e termini comuni  
 La maggior parte dei termini composte vengono considerate come singole parole per scopi di maiuscole/minuscole.  
  
 **X DO NOT** tutte iniziali maiuscole in cosiddette parole composte forma chiusa.  
  
 Queste sono le parole composte scritte come una parola singola, come endpoint. Ai fini di linee guida per le maiuscole e minuscole, considerare una chiusura parola composta come una singola parola. Usare un dizionario corrente per determinare se una parola composta è scritto in forma chiusa.  
  
|Convenzione Pascal|Notazione camel|non|  
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
  
## <a name="case-sensitivity"></a>Distinzione fra maiuscole e minuscole  
 I linguaggi che è possano eseguirla in CLR non devono supportare distinzione maiuscole/minuscole, anche se alcune eseguire. Anche se il linguaggio la supporta, altri linguaggi che potrebbero accedere il framework non. Tutte le API che siano accessibili esternamente, pertanto, non si basano su case da solo per distinguere tra i due nomi nello stesso contesto.  
  
 **X DO NOT** presupporre che tutti i linguaggi di programmazione siano distinzione maiuscole / minuscole. Ma non lo sono. I nomi non può essere diversa di maiuscole/minuscole solo.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)

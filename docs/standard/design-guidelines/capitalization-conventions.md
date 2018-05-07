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
ms.openlocfilehash: 7ef7913a2601c3a791cb028b4074ce37b9e9421b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="capitalization-conventions"></a>Convenzioni per l'utilizzo di maiuscole e minuscole
Le linee guida fornite in questo capitolo disporre un metodo semplice per l'utilizzo di case che, quando applicato in modo coerente, verificare gli identificatori per i tipi, membri e parametri di facile lettura.  
  
## <a name="capitalization-rules-for-identifiers"></a>Regole per gli identificatori  
 Per differenziare le parole in un identificatore, converte in maiuscolo la prima lettera di ogni parola nell'identificatore. Non utilizzare caratteri di sottolineatura per differenziare le parole o a tale scopo, in qualsiasi punto negli identificatori. Esistono due modi appropriati in maiuscolo gli identificatori, a seconda dell'utilizzo dell'identificatore:  
  
-   Sistema Pascal  
  
-   Camel  
  
 La convenzione il sistema Pascal, utilizzata per tutti gli identificatori, ad eccezione di nomi di parametro, converte in maiuscolo il primo carattere di ogni parola (inclusi gli acronimi su due lettere), come illustrato negli esempi seguenti:  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 Un caso speciale viene effettuato per due lettere acronimi in cui sia le lettere sono in maiuscolo, come illustrato nella seguente identificatore:  
  
 `IOStream`  
  
 La convenzione camel, utilizzata solo per i nomi di parametro, converte in maiuscolo il primo carattere di ogni parola eccetto la prima parola, come illustrato negli esempi seguenti. Come nell'esempio viene inoltre, gli acronimi di due lettere che iniziano un identificatore di maiuscole/minuscole camel sono entrambi lettere minuscole.  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 **✓ SI** utilizzare il sistema Pascal per tutti i membri, tipo e spazio dei nomi nomi pubblici composta da più parole.  
  
 **✓ SI** utilizzare camel per i nomi dei parametri.  
  
 Nella tabella seguente descrive le regole di utilizzo delle maiuscole per diversi tipi di identificatori.  
  
|Identificatore|Maiuscole e minuscole|Esempio|  
|----------------|------------|-------------|  
|Spazio dei nomi|Convenzione Pascal|`namespace System.Security { ... }`|  
|Tipo|Convenzione Pascal|`public class StreamReader { ... }`|  
|Interfaccia|Convenzione Pascal|`public interface IEnumerable { ... }`|  
|Metodo|Convenzione Pascal|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|Proprietà|Convenzione Pascal|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|event|Convenzione Pascal|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|Campo|Convenzione Pascal|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|Valore enum|Convenzione Pascal|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|Parametro|Convenzione camel|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a>Le parole composte con iniziale maiuscole e termini comuni  
 La maggior parte dei termini composti vengono considerati come singole parole per scopi di lettere maiuscole/minuscole.  
  
 **X non** tutte iniziali maiuscole in cosiddette parole composte forma chiusa.  
  
 Queste sono le parole composte scritte come una parola singola, ad esempio endpoint. Allo scopo di linee guida di maiuscole e minuscole, considerare una chiuso parola composta come una singola parola. Utilizzare un dizionario corrente per determinare se una parola composta è scritto in forma chiusa.  
  
|Convenzione Pascal|Convenzione camel|non|  
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
 Linguaggi che è possono eseguire in Common Language Runtime non è richiesta per supportare distinzione maiuscole/minuscole, anche se alcuni. Anche se supporta la lingua, altri linguaggi che potrebbero accedere il framework non. Le API che sono accessibili dall'esterno, pertanto, possono basarsi su case da solo per distinguere tra i due nomi nello stesso contesto.  
  
 **X non** presupporre che tutti i linguaggi di programmazione siano distinzione maiuscole / minuscole. Ma non lo sono. I nomi non possono differire dalle maiuscole o minuscole da solo.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)

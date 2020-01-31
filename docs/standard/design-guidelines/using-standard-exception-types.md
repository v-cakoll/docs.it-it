---
title: Utilizzo di tipi di eccezioni standard
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
ms.openlocfilehash: 3caa94d9a39966614161e4b19201dcf6065776a2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743550"
---
# <a name="using-standard-exception-types"></a>Utilizzo di tipi di eccezioni standard
In questa sezione vengono descritte le eccezioni standard fornite dal Framework e i dettagli relativi all'utilizzo. L'elenco non è esaustivo. Per informazioni sull'utilizzo di altri tipi di eccezioni del Framework, fare riferimento alla documentazione di riferimento .NET Framework.

## <a name="exception-and-systemexception"></a>Eccezione e SystemException
 ❌ non generano <xref:System.Exception?displayProperty=nameWithType> o <xref:System.SystemException?displayProperty=nameWithType>.

 ❌ non intercettare `System.Exception` o `System.SystemException` nel codice del Framework, a meno che non si intenda rigenerare.

 ❌ evitare di rilevare `System.Exception` o `System.SystemException`, eccetto nei gestori di eccezioni di primo livello.

## <a name="applicationexception"></a>ApplicationException
 ❌ non generano o derivano da <xref:System.ApplicationException>.

## <a name="invalidoperationexception"></a>InvalidOperationException
 ✔️ generano una <xref:System.InvalidOperationException> se lo stato dell'oggetto non è appropriato.

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException, ArgumentNullException ed ArgumentOutOfRangeException
 ✔️ generano <xref:System.ArgumentException> o uno dei relativi sottotipi se gli argomenti non validi vengono passati a un membro. Preferisce il tipo di eccezione più derivato, se applicabile.

 ✔️ impostare la proprietà `ParamName` quando si genera una delle sottoclassi di `ArgumentException`.

 Questa proprietà rappresenta il nome del parametro che ha causato la generazione dell'eccezione. Si noti che la proprietà può essere impostata utilizzando uno degli overload del costruttore.

 ✔️ usare `value` per il nome del parametro del valore implicito dei setter della proprietà.

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException, IndexOutOfRangeException e AccessViolationException
 ❌ non consentono alle API pubblicamente richiamabili di generare <xref:System.NullReferenceException>, <xref:System.AccessViolationException>o <xref:System.IndexOutOfRangeException>in modo esplicito o implicito. Queste eccezioni sono riservate e generate dal motore di esecuzione e nella maggior parte dei casi indicano un bug.

 Eseguire il controllo degli argomenti per evitare la generazione di queste eccezioni. La generazione di queste eccezioni espone i dettagli di implementazione del metodo che potrebbero cambiare nel tempo.

## <a name="stackoverflowexception"></a>StackOverflowException
 ❌ non generano <xref:System.StackOverflowException>in modo esplicito. L'eccezione deve essere generata in modo esplicito solo da CLR.

 ❌ non intercettare `StackOverflowException`.

 È quasi impossibile scrivere codice gestito che rimanga coerente in presenza di overflow dello stack arbitrario. Le parti non gestite di CLR rimangono coerenti usando i probe per spostare gli overflow dello stack in posizioni ben definite anziché eseguendo il backup da overflow dello stack arbitrario.

## <a name="outofmemoryexception"></a>OutOfMemoryException
 ❌ non generano <xref:System.OutOfMemoryException>in modo esplicito. Questa eccezione deve essere generata solo dall'infrastruttura CLR.

## <a name="comexception-sehexception-and-executionengineexception"></a>COMException, SEHException e ExecutionEngineException
 ❌ non generano esplicitamente <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>e <xref:System.Runtime.InteropServices.SEHException>. Queste eccezioni devono essere generate solo dall'infrastruttura CLR.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Linee guida di progettazione delle eccezioni](../../../docs/standard/design-guidelines/exceptions.md)

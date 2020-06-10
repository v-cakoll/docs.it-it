---
title: Utilizzo di tipi di eccezioni standard
description: Per informazioni sui tipi di eccezione standard, vedere .NET. Informazioni su SystemException, ApplicationException, ArgumentException, COMException e altro ancora.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
ms.openlocfilehash: f95529eabd87d9ec7c379b9f790e039e1192ac53
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84663057"
---
# <a name="using-standard-exception-types"></a>Utilizzo di tipi di eccezioni standard
In questa sezione vengono descritte le eccezioni standard fornite dal Framework e i dettagli relativi all'utilizzo. L'elenco non è esaustivo. Per informazioni sull'utilizzo di altri tipi di eccezioni del Framework, fare riferimento alla documentazione di riferimento .NET Framework.

## <a name="exception-and-systemexception"></a>Eccezione e SystemException
 ❌NON generare <xref:System.Exception?displayProperty=nameWithType> o <xref:System.SystemException?displayProperty=nameWithType> .

 ❌Non intercettare `System.Exception` o `System.SystemException` nel codice del Framework, a meno che non si intenda rigenerare.

 ❌EVITARE di intercettare `System.Exception` o `System.SystemException` , eccetto nei gestori di eccezioni di primo livello.

## <a name="applicationexception"></a>ApplicationException
 ❌NON generare o derivare da <xref:System.ApplicationException> .

## <a name="invalidoperationexception"></a>InvalidOperationException
 ✔️ genera un'operazione <xref:System.InvalidOperationException> se lo stato dell'oggetto non è appropriato.

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException, ArgumentNullException ed ArgumentOutOfRangeException
 ✔️ Throw <xref:System.ArgumentException> o uno dei relativi sottotipi se gli argomenti non validi vengono passati a un membro. Preferisce il tipo di eccezione più derivato, se applicabile.

 ✔️ impostare la `ParamName` proprietà quando si genera una delle sottoclassi di `ArgumentException` .

 Questa proprietà rappresenta il nome del parametro che ha causato la generazione dell'eccezione. Si noti che la proprietà può essere impostata utilizzando uno degli overload del costruttore.

 ✔️ utilizzare `value` per il nome del parametro del valore implicito dei setter della proprietà.

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException, IndexOutOfRangeException e AccessViolationException
 ❌NON consentire alle API pubblicamente richiamabili di generare in modo esplicito o implicito <xref:System.NullReferenceException> , <xref:System.AccessViolationException> o <xref:System.IndexOutOfRangeException> . Queste eccezioni sono riservate e generate dal motore di esecuzione e nella maggior parte dei casi indicano un bug.

 Eseguire il controllo degli argomenti per evitare la generazione di queste eccezioni. La generazione di queste eccezioni espone i dettagli di implementazione del metodo che potrebbero cambiare nel tempo.

## <a name="stackoverflowexception"></a>StackOverflowException
 ❌NON generare esplicitamente <xref:System.StackOverflowException> . L'eccezione deve essere generata in modo esplicito solo da CLR.

 ❌Non intercettare `StackOverflowException` .

 È quasi impossibile scrivere codice gestito che rimanga coerente in presenza di overflow dello stack arbitrario. Le parti non gestite di CLR rimangono coerenti usando i probe per spostare gli overflow dello stack in posizioni ben definite anziché eseguendo il backup da overflow dello stack arbitrario.

## <a name="outofmemoryexception"></a>OutOfMemoryException
 ❌NON generare esplicitamente <xref:System.OutOfMemoryException> . Questa eccezione deve essere generata solo dall'infrastruttura CLR.

## <a name="comexception-sehexception-and-executionengineexception"></a>COMException, SEHException e ExecutionEngineException
 ❌NON generare in modo esplicito <xref:System.Runtime.InteropServices.COMException> , <xref:System.ExecutionEngineException> e <xref:System.Runtime.InteropServices.SEHException> . Queste eccezioni devono essere generate solo dall'infrastruttura CLR.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](index.md)
- [Linee guida di progettazione delle eccezioni](exceptions.md)

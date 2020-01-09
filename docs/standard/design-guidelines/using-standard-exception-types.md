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
ms.openlocfilehash: 6b202d618d9d2216c8998181303250081de6781c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708984"
---
# <a name="using-standard-exception-types"></a>Utilizzo di tipi di eccezioni standard
In questa sezione vengono descritte le eccezioni standard fornite dal Framework e i dettagli relativi all'utilizzo. L'elenco non è esaustivo. Per informazioni sull'utilizzo di altri tipi di eccezioni del Framework, fare riferimento alla documentazione di riferimento .NET Framework.  
  
## <a name="exception-and-systemexception"></a>Eccezione e SystemException  
 **X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> o <xref:System.SystemException?displayProperty=nameWithType>.  
  
 **X DO NOT** catch `System.Exception` o `System.SystemException` nel codice del framework, a meno che non si intende generare di nuovo.  
  
 **X AVOID** intercettazione `System.Exception` o `System.SystemException`, ad eccezione dei gestori di eccezioni di livello superiore.  
  
## <a name="applicationexception"></a>ApplicationException  
 **X DO NOT** generare o derivare da <xref:System.ApplicationException>.  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **✓ DO** generano un <xref:System.InvalidOperationException> se l'oggetto è in uno stato non appropriato.  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException, ArgumentNullException ed ArgumentOutOfRangeException  
 **✓ DO** throw <xref:System.ArgumentException> o uno dei sottotipi se a un membro vengono passati argomenti non validi. Preferisce il tipo di eccezione più derivato, se applicabile.  
  
 **✓ DO** impostare il `ParamName` proprietà durante la generazione di una delle sottoclassi di `ArgumentException`.  
  
 Questa proprietà rappresenta il nome del parametro che ha causato la generazione dell'eccezione. Si noti che la proprietà può essere impostata utilizzando uno degli overload del costruttore.  
  
 **✓ DO** utilizzare `value` per il nome del parametro del valore implicito dell'impostazione delle proprietà.  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException, IndexOutOfRangeException e AccessViolationException  
 **X DO NOT** consentire pubblicamente disponibile per la chiamata API generare in modo esplicito o implicito <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, o <xref:System.IndexOutOfRangeException>. Queste eccezioni sono riservate e generate dal motore di esecuzione e nella maggior parte dei casi indicano un bug.  
  
 Eseguire il controllo degli argomenti per evitare la generazione di queste eccezioni. La generazione di queste eccezioni espone i dettagli di implementazione del metodo che potrebbero cambiare nel tempo.  
  
## <a name="stackoverflowexception"></a>StackOverflowException  
 **X DO NOT** generare in modo esplicito <xref:System.StackOverflowException>. L'eccezione deve essere generata in modo esplicito solo da CLR.  
  
 **X DO NOT** catch `StackOverflowException`.  
  
 È quasi impossibile scrivere codice gestito che rimanga coerente in presenza di overflow dello stack arbitrario. Le parti non gestite di CLR rimangono coerenti usando i probe per spostare gli overflow dello stack in posizioni ben definite anziché eseguendo il backup da overflow dello stack arbitrario.  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X DO NOT** generare in modo esplicito <xref:System.OutOfMemoryException>. Questa eccezione deve essere generata solo dall'infrastruttura CLR.  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>COMException, SEHException e ExecutionEngineException  
 **X DO NOT** generare in modo esplicito <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, e <xref:System.Runtime.InteropServices.SEHException>. Queste eccezioni devono essere generate solo dall'infrastruttura CLR.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Linee guida di progettazione delle eccezioni](../../../docs/standard/design-guidelines/exceptions.md)

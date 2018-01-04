---
title: Utilizzo di tipi di eccezioni standard
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5098db5131c2e47c0b73efaac51477ef3b107761
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="using-standard-exception-types"></a>Utilizzo di tipi di eccezioni standard
In questa sezione descrive le eccezioni standard fornite dal Framework e i dettagli del loro utilizzo. L'elenco non è completo. Consultare la documentazione di riferimento di .NET Framework per l'utilizzo di altri tipi di eccezione di Framework.  
  
## <a name="exception-and-systemexception"></a>Eccezione e SystemException  
 **X non** generare <xref:System.Exception?displayProperty=nameWithType> o <xref:System.SystemException?displayProperty=nameWithType>.  
  
 **X non** catch `System.Exception` o `System.SystemException` nel codice del framework, a meno che non si intende generare di nuovo.  
  
 **X evitare** intercettazione `System.Exception` o `System.SystemException`, tranne che nei gestori di eccezioni di livello superiore.  
  
## <a name="applicationexception"></a>ApplicationException  
 **X non** generare o derivare da <xref:System.ApplicationException>.  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **✓ SI** generano un <xref:System.InvalidOperationException> se l'oggetto è in uno stato appropriato.  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException, ArgumentNullException e ArgumentOutOfRangeException  
 **✓ SI** generare <xref:System.ArgumentException> o uno dei relativi sottotipi se a un membro vengono passati argomenti non validi. Scegliere il tipo di eccezione più derivato, se applicabile.  
  
 **✓ SI** impostare il `ParamName` proprietà durante la generazione di una delle sottoclassi di `ArgumentException`.  
  
 Questa proprietà rappresenta il nome del parametro che ha causato l'eccezione generata. Si noti che è possibile impostare la proprietà utilizzando uno degli overload del costruttore.  
  
 **✓ SI** utilizzare `value` per il nome del parametro del valore implicito dell'impostazione delle proprietà.  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>AccessViolationException NullReferenceException e IndexOutOfRangeException  
 **X non** consentire ad API pubblicamente richiamabili generare in modo esplicito o implicito <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, o <xref:System.IndexOutOfRangeException>. Queste eccezioni sono riservate e generata dal motore di esecuzione e nella che maggior parte dei casi indica un bug.  
  
 Eseguire un controllo per evitare la generazione di queste eccezioni di argomento. Generazione di queste eccezioni espone i dettagli di implementazione del metodo che può cambiare nel tempo.  
  
## <a name="stackoverflowexception"></a>StackOverflowException  
 **X non** generare in modo esplicito <xref:System.StackOverflowException>. L'eccezione deve essere generata in modo esplicito solo da CLR.  
  
 **X non** catch `StackOverflowException`.  
  
 È quasi impossibile scrivere il codice gestito che rimanga coerenza in presenza di overflow dello stack arbitrario. Le parti di CLR non gestite rimangono coerenti utilizzando probe per spostare l'overflow dello stack a posizioni ben definiti invece il backup di overflow dello stack arbitrario.  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X non** generare in modo esplicito <xref:System.OutOfMemoryException>. Questa eccezione viene generata solo dall'infrastruttura di CLR.  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>ComException e SEHException ExecutionEngineException  
 **X non** generare in modo esplicito <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, e <xref:System.Runtime.InteropServices.SEHException>. Queste eccezioni devono essere generate solo dall'infrastruttura CLR.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Linee guida di progettazione delle eccezioni](../../../docs/standard/design-guidelines/exceptions.md)

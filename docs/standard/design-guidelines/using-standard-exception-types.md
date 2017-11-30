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
ms.openlocfilehash: 91cd9a03ad1acf61681ecfad0edb061802c4362c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="5c923-102">Utilizzo di tipi di eccezioni standard</span><span class="sxs-lookup"><span data-stu-id="5c923-102">Using Standard Exception Types</span></span>
<span data-ttu-id="5c923-103">In questa sezione descrive le eccezioni standard fornite dal Framework e i dettagli del loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="5c923-103">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="5c923-104">L'elenco non è completo.</span><span class="sxs-lookup"><span data-stu-id="5c923-104">The list is by no means exhaustive.</span></span> <span data-ttu-id="5c923-105">Consultare la documentazione di riferimento di .NET Framework per l'utilizzo di altri tipi di eccezione di Framework.</span><span class="sxs-lookup"><span data-stu-id="5c923-105">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>  
  
## <a name="exception-and-systemexception"></a><span data-ttu-id="5c923-106">Eccezione e SystemException</span><span class="sxs-lookup"><span data-stu-id="5c923-106">Exception and SystemException</span></span>  
 <span data-ttu-id="5c923-107">**X non** generare <xref:System.Exception?displayProperty=nameWithType> o <xref:System.SystemException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c923-107">**X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="5c923-108">**X non** catch `System.Exception` o `System.SystemException` nel codice del framework, a meno che non si intende generare di nuovo.</span><span class="sxs-lookup"><span data-stu-id="5c923-108">**X DO NOT** catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>  
  
 <span data-ttu-id="5c923-109">**X evitare** intercettazione `System.Exception` o `System.SystemException`, tranne che nei gestori di eccezioni di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="5c923-109">**X AVOID** catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>  
  
## <a name="applicationexception"></a><span data-ttu-id="5c923-110">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="5c923-110">ApplicationException</span></span>  
 <span data-ttu-id="5c923-111">**X non** generare o derivare da <xref:System.ApplicationException>.</span><span class="sxs-lookup"><span data-stu-id="5c923-111">**X DO NOT** throw or derive from <xref:System.ApplicationException>.</span></span>  
  
## <a name="invalidoperationexception"></a><span data-ttu-id="5c923-112">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="5c923-112">InvalidOperationException</span></span>  
 <span data-ttu-id="5c923-113">**✓ SI** generano un <xref:System.InvalidOperationException> se l'oggetto è in uno stato appropriato.</span><span class="sxs-lookup"><span data-stu-id="5c923-113">**✓ DO** throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="5c923-114">ArgumentException, ArgumentNullException e ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="5c923-114">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>  
 <span data-ttu-id="5c923-115">**✓ SI** generare <xref:System.ArgumentException> o uno dei relativi sottotipi se a un membro vengono passati argomenti non validi.</span><span class="sxs-lookup"><span data-stu-id="5c923-115">**✓ DO** throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="5c923-116">Scegliere il tipo di eccezione più derivato, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="5c923-116">Prefer the most derived exception type, if applicable.</span></span>  
  
 <span data-ttu-id="5c923-117">**✓ SI** impostare il `ParamName` proprietà durante la generazione di una delle sottoclassi di `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="5c923-117">**✓ DO** set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>  
  
 <span data-ttu-id="5c923-118">Questa proprietà rappresenta il nome del parametro che ha causato l'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="5c923-118">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="5c923-119">Si noti che è possibile impostare la proprietà utilizzando uno degli overload del costruttore.</span><span class="sxs-lookup"><span data-stu-id="5c923-119">Note that the property can be set using one of the constructor overloads.</span></span>  
  
 <span data-ttu-id="5c923-120">**✓ SI** utilizzare `value` per il nome del parametro del valore implicito dell'impostazione delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="5c923-120">**✓ DO** use `value` for the name of the implicit value parameter of property setters.</span></span>  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="5c923-121">AccessViolationException NullReferenceException e IndexOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="5c923-121">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>  
 <span data-ttu-id="5c923-122">**X non** consentire ad API pubblicamente richiamabili generare in modo esplicito o implicito <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, o <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="5c923-122">**X DO NOT** allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="5c923-123">Queste eccezioni sono riservate e generata dal motore di esecuzione e nella che maggior parte dei casi indica un bug.</span><span class="sxs-lookup"><span data-stu-id="5c923-123">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>  
  
 <span data-ttu-id="5c923-124">Eseguire un controllo per evitare la generazione di queste eccezioni di argomento.</span><span class="sxs-lookup"><span data-stu-id="5c923-124">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="5c923-125">Generazione di queste eccezioni espone i dettagli di implementazione del metodo che può cambiare nel tempo.</span><span class="sxs-lookup"><span data-stu-id="5c923-125">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>  
  
## <a name="stackoverflowexception"></a><span data-ttu-id="5c923-126">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="5c923-126">StackOverflowException</span></span>  
 <span data-ttu-id="5c923-127">**X non** generare in modo esplicito <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="5c923-127">**X DO NOT** explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="5c923-128">L'eccezione deve essere generata in modo esplicito solo da CLR.</span><span class="sxs-lookup"><span data-stu-id="5c923-128">The exception should be explicitly thrown only by the CLR.</span></span>  
  
 <span data-ttu-id="5c923-129">**X non** catch `StackOverflowException`.</span><span class="sxs-lookup"><span data-stu-id="5c923-129">**X DO NOT** catch `StackOverflowException`.</span></span>  
  
 <span data-ttu-id="5c923-130">È quasi impossibile scrivere il codice gestito che rimanga coerenza in presenza di overflow dello stack arbitrario.</span><span class="sxs-lookup"><span data-stu-id="5c923-130">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="5c923-131">Le parti di CLR non gestite rimangono coerenti utilizzando probe per spostare l'overflow dello stack a posizioni ben definiti invece il backup di overflow dello stack arbitrario.</span><span class="sxs-lookup"><span data-stu-id="5c923-131">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>  
  
## <a name="outofmemoryexception"></a><span data-ttu-id="5c923-132">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="5c923-132">OutOfMemoryException</span></span>  
 <span data-ttu-id="5c923-133">**X non** generare in modo esplicito <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="5c923-133">**X DO NOT** explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="5c923-134">Questa eccezione viene generata solo dall'infrastruttura di CLR.</span><span class="sxs-lookup"><span data-stu-id="5c923-134">This exception is to be thrown only by the CLR infrastructure.</span></span>  
  
## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="5c923-135">ComException e SEHException ExecutionEngineException</span><span class="sxs-lookup"><span data-stu-id="5c923-135">ComException, SEHException, and ExecutionEngineException</span></span>  
 <span data-ttu-id="5c923-136">**X non** generare in modo esplicito <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, e <xref:System.Runtime.InteropServices.SEHException>.</span><span class="sxs-lookup"><span data-stu-id="5c923-136">**X DO NOT** explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="5c923-137">Queste eccezioni devono essere generate solo dall'infrastruttura CLR.</span><span class="sxs-lookup"><span data-stu-id="5c923-137">These exceptions are to be thrown only by the CLR infrastructure.</span></span>  
  
 <span data-ttu-id="5c923-138">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="5c923-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5c923-139">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="5c923-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c923-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c923-140">See Also</span></span>  
 [<span data-ttu-id="5c923-141">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="5c923-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="5c923-142">Linee guida di progettazione per le eccezioni</span><span class="sxs-lookup"><span data-stu-id="5c923-142">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)

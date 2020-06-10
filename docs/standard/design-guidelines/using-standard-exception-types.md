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
# <a name="using-standard-exception-types"></a><span data-ttu-id="5c47b-104">Utilizzo di tipi di eccezioni standard</span><span class="sxs-lookup"><span data-stu-id="5c47b-104">Using Standard Exception Types</span></span>
<span data-ttu-id="5c47b-105">In questa sezione vengono descritte le eccezioni standard fornite dal Framework e i dettagli relativi all'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="5c47b-105">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="5c47b-106">L'elenco non è esaustivo.</span><span class="sxs-lookup"><span data-stu-id="5c47b-106">The list is by no means exhaustive.</span></span> <span data-ttu-id="5c47b-107">Per informazioni sull'utilizzo di altri tipi di eccezioni del Framework, fare riferimento alla documentazione di riferimento .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5c47b-107">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>

## <a name="exception-and-systemexception"></a><span data-ttu-id="5c47b-108">Eccezione e SystemException</span><span class="sxs-lookup"><span data-stu-id="5c47b-108">Exception and SystemException</span></span>
 <span data-ttu-id="5c47b-109">❌NON generare <xref:System.Exception?displayProperty=nameWithType> o <xref:System.SystemException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="5c47b-109">❌ DO NOT throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="5c47b-110">❌Non intercettare `System.Exception` o `System.SystemException` nel codice del Framework, a meno che non si intenda rigenerare.</span><span class="sxs-lookup"><span data-stu-id="5c47b-110">❌ DO NOT catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>

 <span data-ttu-id="5c47b-111">❌EVITARE di intercettare `System.Exception` o `System.SystemException` , eccetto nei gestori di eccezioni di primo livello.</span><span class="sxs-lookup"><span data-stu-id="5c47b-111">❌ AVOID catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>

## <a name="applicationexception"></a><span data-ttu-id="5c47b-112">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="5c47b-112">ApplicationException</span></span>
 <span data-ttu-id="5c47b-113">❌NON generare o derivare da <xref:System.ApplicationException> .</span><span class="sxs-lookup"><span data-stu-id="5c47b-113">❌ DO NOT throw or derive from <xref:System.ApplicationException>.</span></span>

## <a name="invalidoperationexception"></a><span data-ttu-id="5c47b-114">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="5c47b-114">InvalidOperationException</span></span>
 <span data-ttu-id="5c47b-115">✔️ genera un'operazione <xref:System.InvalidOperationException> se lo stato dell'oggetto non è appropriato.</span><span class="sxs-lookup"><span data-stu-id="5c47b-115">✔️ DO throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="5c47b-116">ArgumentException, ArgumentNullException ed ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="5c47b-116">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>
 <span data-ttu-id="5c47b-117">✔️ Throw <xref:System.ArgumentException> o uno dei relativi sottotipi se gli argomenti non validi vengono passati a un membro.</span><span class="sxs-lookup"><span data-stu-id="5c47b-117">✔️ DO throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="5c47b-118">Preferisce il tipo di eccezione più derivato, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="5c47b-118">Prefer the most derived exception type, if applicable.</span></span>

 <span data-ttu-id="5c47b-119">✔️ impostare la `ParamName` proprietà quando si genera una delle sottoclassi di `ArgumentException` .</span><span class="sxs-lookup"><span data-stu-id="5c47b-119">✔️ DO set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>

 <span data-ttu-id="5c47b-120">Questa proprietà rappresenta il nome del parametro che ha causato la generazione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5c47b-120">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="5c47b-121">Si noti che la proprietà può essere impostata utilizzando uno degli overload del costruttore.</span><span class="sxs-lookup"><span data-stu-id="5c47b-121">Note that the property can be set using one of the constructor overloads.</span></span>

 <span data-ttu-id="5c47b-122">✔️ utilizzare `value` per il nome del parametro del valore implicito dei setter della proprietà.</span><span class="sxs-lookup"><span data-stu-id="5c47b-122">✔️ DO use `value` for the name of the implicit value parameter of property setters.</span></span>

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="5c47b-123">NullReferenceException, IndexOutOfRangeException e AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="5c47b-123">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>
 <span data-ttu-id="5c47b-124">❌NON consentire alle API pubblicamente richiamabili di generare in modo esplicito o implicito <xref:System.NullReferenceException> , <xref:System.AccessViolationException> o <xref:System.IndexOutOfRangeException> .</span><span class="sxs-lookup"><span data-stu-id="5c47b-124">❌ DO NOT allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="5c47b-125">Queste eccezioni sono riservate e generate dal motore di esecuzione e nella maggior parte dei casi indicano un bug.</span><span class="sxs-lookup"><span data-stu-id="5c47b-125">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>

 <span data-ttu-id="5c47b-126">Eseguire il controllo degli argomenti per evitare la generazione di queste eccezioni.</span><span class="sxs-lookup"><span data-stu-id="5c47b-126">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="5c47b-127">La generazione di queste eccezioni espone i dettagli di implementazione del metodo che potrebbero cambiare nel tempo.</span><span class="sxs-lookup"><span data-stu-id="5c47b-127">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>

## <a name="stackoverflowexception"></a><span data-ttu-id="5c47b-128">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="5c47b-128">StackOverflowException</span></span>
 <span data-ttu-id="5c47b-129">❌NON generare esplicitamente <xref:System.StackOverflowException> .</span><span class="sxs-lookup"><span data-stu-id="5c47b-129">❌ DO NOT explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="5c47b-130">L'eccezione deve essere generata in modo esplicito solo da CLR.</span><span class="sxs-lookup"><span data-stu-id="5c47b-130">The exception should be explicitly thrown only by the CLR.</span></span>

 <span data-ttu-id="5c47b-131">❌Non intercettare `StackOverflowException` .</span><span class="sxs-lookup"><span data-stu-id="5c47b-131">❌ DO NOT catch `StackOverflowException`.</span></span>

 <span data-ttu-id="5c47b-132">È quasi impossibile scrivere codice gestito che rimanga coerente in presenza di overflow dello stack arbitrario.</span><span class="sxs-lookup"><span data-stu-id="5c47b-132">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="5c47b-133">Le parti non gestite di CLR rimangono coerenti usando i probe per spostare gli overflow dello stack in posizioni ben definite anziché eseguendo il backup da overflow dello stack arbitrario.</span><span class="sxs-lookup"><span data-stu-id="5c47b-133">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>

## <a name="outofmemoryexception"></a><span data-ttu-id="5c47b-134">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="5c47b-134">OutOfMemoryException</span></span>
 <span data-ttu-id="5c47b-135">❌NON generare esplicitamente <xref:System.OutOfMemoryException> .</span><span class="sxs-lookup"><span data-stu-id="5c47b-135">❌ DO NOT explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="5c47b-136">Questa eccezione deve essere generata solo dall'infrastruttura CLR.</span><span class="sxs-lookup"><span data-stu-id="5c47b-136">This exception is to be thrown only by the CLR infrastructure.</span></span>

## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="5c47b-137">COMException, SEHException e ExecutionEngineException</span><span class="sxs-lookup"><span data-stu-id="5c47b-137">ComException, SEHException, and ExecutionEngineException</span></span>
 <span data-ttu-id="5c47b-138">❌NON generare in modo esplicito <xref:System.Runtime.InteropServices.COMException> , <xref:System.ExecutionEngineException> e <xref:System.Runtime.InteropServices.SEHException> .</span><span class="sxs-lookup"><span data-stu-id="5c47b-138">❌ DO NOT explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="5c47b-139">Queste eccezioni devono essere generate solo dall'infrastruttura CLR.</span><span class="sxs-lookup"><span data-stu-id="5c47b-139">These exceptions are to be thrown only by the CLR infrastructure.</span></span>

 <span data-ttu-id="5c47b-140">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="5c47b-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="5c47b-141">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="5c47b-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="5c47b-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c47b-142">See also</span></span>

- [<span data-ttu-id="5c47b-143">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="5c47b-143">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="5c47b-144">Linee guida di progettazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="5c47b-144">Design Guidelines for Exceptions</span></span>](exceptions.md)

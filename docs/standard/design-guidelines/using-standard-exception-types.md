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
ms.openlocfilehash: b8e05f22a66fabeab28cc83a074471df29aae218
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291357"
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="57ce8-102">Utilizzo di tipi di eccezioni standard</span><span class="sxs-lookup"><span data-stu-id="57ce8-102">Using Standard Exception Types</span></span>
<span data-ttu-id="57ce8-103">In questa sezione vengono descritte le eccezioni standard fornite dal Framework e i dettagli relativi all'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="57ce8-103">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="57ce8-104">L'elenco non è esaustivo.</span><span class="sxs-lookup"><span data-stu-id="57ce8-104">The list is by no means exhaustive.</span></span> <span data-ttu-id="57ce8-105">Per informazioni sull'utilizzo di altri tipi di eccezioni del Framework, fare riferimento alla documentazione di riferimento .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57ce8-105">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>

## <a name="exception-and-systemexception"></a><span data-ttu-id="57ce8-106">Eccezione e SystemException</span><span class="sxs-lookup"><span data-stu-id="57ce8-106">Exception and SystemException</span></span>
 <span data-ttu-id="57ce8-107">❌NON generare <xref:System.Exception?displayProperty=nameWithType> o <xref:System.SystemException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="57ce8-107">❌ DO NOT throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="57ce8-108">❌Non intercettare `System.Exception` o `System.SystemException` nel codice del Framework, a meno che non si intenda rigenerare.</span><span class="sxs-lookup"><span data-stu-id="57ce8-108">❌ DO NOT catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>

 <span data-ttu-id="57ce8-109">❌EVITARE di intercettare `System.Exception` o `System.SystemException` , eccetto nei gestori di eccezioni di primo livello.</span><span class="sxs-lookup"><span data-stu-id="57ce8-109">❌ AVOID catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>

## <a name="applicationexception"></a><span data-ttu-id="57ce8-110">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="57ce8-110">ApplicationException</span></span>
 <span data-ttu-id="57ce8-111">❌NON generare o derivare da <xref:System.ApplicationException> .</span><span class="sxs-lookup"><span data-stu-id="57ce8-111">❌ DO NOT throw or derive from <xref:System.ApplicationException>.</span></span>

## <a name="invalidoperationexception"></a><span data-ttu-id="57ce8-112">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="57ce8-112">InvalidOperationException</span></span>
 <span data-ttu-id="57ce8-113">✔️ genera un'operazione <xref:System.InvalidOperationException> se lo stato dell'oggetto non è appropriato.</span><span class="sxs-lookup"><span data-stu-id="57ce8-113">✔️ DO throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="57ce8-114">ArgumentException, ArgumentNullException ed ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="57ce8-114">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>
 <span data-ttu-id="57ce8-115">✔️ Throw <xref:System.ArgumentException> o uno dei relativi sottotipi se gli argomenti non validi vengono passati a un membro.</span><span class="sxs-lookup"><span data-stu-id="57ce8-115">✔️ DO throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="57ce8-116">Preferisce il tipo di eccezione più derivato, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="57ce8-116">Prefer the most derived exception type, if applicable.</span></span>

 <span data-ttu-id="57ce8-117">✔️ impostare la `ParamName` proprietà quando si genera una delle sottoclassi di `ArgumentException` .</span><span class="sxs-lookup"><span data-stu-id="57ce8-117">✔️ DO set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>

 <span data-ttu-id="57ce8-118">Questa proprietà rappresenta il nome del parametro che ha causato la generazione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="57ce8-118">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="57ce8-119">Si noti che la proprietà può essere impostata utilizzando uno degli overload del costruttore.</span><span class="sxs-lookup"><span data-stu-id="57ce8-119">Note that the property can be set using one of the constructor overloads.</span></span>

 <span data-ttu-id="57ce8-120">✔️ utilizzare `value` per il nome del parametro del valore implicito dei setter della proprietà.</span><span class="sxs-lookup"><span data-stu-id="57ce8-120">✔️ DO use `value` for the name of the implicit value parameter of property setters.</span></span>

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="57ce8-121">NullReferenceException, IndexOutOfRangeException e AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="57ce8-121">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>
 <span data-ttu-id="57ce8-122">❌NON consentire alle API pubblicamente richiamabili di generare in modo esplicito o implicito <xref:System.NullReferenceException> , <xref:System.AccessViolationException> o <xref:System.IndexOutOfRangeException> .</span><span class="sxs-lookup"><span data-stu-id="57ce8-122">❌ DO NOT allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="57ce8-123">Queste eccezioni sono riservate e generate dal motore di esecuzione e nella maggior parte dei casi indicano un bug.</span><span class="sxs-lookup"><span data-stu-id="57ce8-123">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>

 <span data-ttu-id="57ce8-124">Eseguire il controllo degli argomenti per evitare la generazione di queste eccezioni.</span><span class="sxs-lookup"><span data-stu-id="57ce8-124">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="57ce8-125">La generazione di queste eccezioni espone i dettagli di implementazione del metodo che potrebbero cambiare nel tempo.</span><span class="sxs-lookup"><span data-stu-id="57ce8-125">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>

## <a name="stackoverflowexception"></a><span data-ttu-id="57ce8-126">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="57ce8-126">StackOverflowException</span></span>
 <span data-ttu-id="57ce8-127">❌NON generare esplicitamente <xref:System.StackOverflowException> .</span><span class="sxs-lookup"><span data-stu-id="57ce8-127">❌ DO NOT explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="57ce8-128">L'eccezione deve essere generata in modo esplicito solo da CLR.</span><span class="sxs-lookup"><span data-stu-id="57ce8-128">The exception should be explicitly thrown only by the CLR.</span></span>

 <span data-ttu-id="57ce8-129">❌Non intercettare `StackOverflowException` .</span><span class="sxs-lookup"><span data-stu-id="57ce8-129">❌ DO NOT catch `StackOverflowException`.</span></span>

 <span data-ttu-id="57ce8-130">È quasi impossibile scrivere codice gestito che rimanga coerente in presenza di overflow dello stack arbitrario.</span><span class="sxs-lookup"><span data-stu-id="57ce8-130">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="57ce8-131">Le parti non gestite di CLR rimangono coerenti usando i probe per spostare gli overflow dello stack in posizioni ben definite anziché eseguendo il backup da overflow dello stack arbitrario.</span><span class="sxs-lookup"><span data-stu-id="57ce8-131">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>

## <a name="outofmemoryexception"></a><span data-ttu-id="57ce8-132">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="57ce8-132">OutOfMemoryException</span></span>
 <span data-ttu-id="57ce8-133">❌NON generare esplicitamente <xref:System.OutOfMemoryException> .</span><span class="sxs-lookup"><span data-stu-id="57ce8-133">❌ DO NOT explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="57ce8-134">Questa eccezione deve essere generata solo dall'infrastruttura CLR.</span><span class="sxs-lookup"><span data-stu-id="57ce8-134">This exception is to be thrown only by the CLR infrastructure.</span></span>

## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="57ce8-135">COMException, SEHException e ExecutionEngineException</span><span class="sxs-lookup"><span data-stu-id="57ce8-135">ComException, SEHException, and ExecutionEngineException</span></span>
 <span data-ttu-id="57ce8-136">❌NON generare in modo esplicito <xref:System.Runtime.InteropServices.COMException> , <xref:System.ExecutionEngineException> e <xref:System.Runtime.InteropServices.SEHException> .</span><span class="sxs-lookup"><span data-stu-id="57ce8-136">❌ DO NOT explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="57ce8-137">Queste eccezioni devono essere generate solo dall'infrastruttura CLR.</span><span class="sxs-lookup"><span data-stu-id="57ce8-137">These exceptions are to be thrown only by the CLR infrastructure.</span></span>

 <span data-ttu-id="57ce8-138">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="57ce8-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="57ce8-139">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="57ce8-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="57ce8-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57ce8-140">See also</span></span>

- [<span data-ttu-id="57ce8-141">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="57ce8-141">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="57ce8-142">Linee guida di progettazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="57ce8-142">Design Guidelines for Exceptions</span></span>](exceptions.md)

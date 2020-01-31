---
title: Eccezioni e prestazioni
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: afa4e748599781a5979823320d8913ff5357d415
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741649"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="b9c36-102">Eccezioni e prestazioni</span><span class="sxs-lookup"><span data-stu-id="b9c36-102">Exceptions and Performance</span></span>
<span data-ttu-id="b9c36-103">Un problema comune correlato alle eccezioni è che se vengono utilizzate eccezioni per il codice che si interrompe normalmente, le prestazioni dell'implementazione non saranno accettabili.</span><span class="sxs-lookup"><span data-stu-id="b9c36-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="b9c36-104">Si tratta di un problema valido.</span><span class="sxs-lookup"><span data-stu-id="b9c36-104">This is a valid concern.</span></span> <span data-ttu-id="b9c36-105">Quando un membro genera un'eccezione, le prestazioni possono essere di dimensioni inferiori.</span><span class="sxs-lookup"><span data-stu-id="b9c36-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="b9c36-106">Tuttavia, è possibile ottenere prestazioni soddisfacenti rispettando rigorosamente le linee guida sulle eccezioni che non consentono l'utilizzo di codici di errore.</span><span class="sxs-lookup"><span data-stu-id="b9c36-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="b9c36-107">Due modelli descritti in questa sezione suggeriscono i modi per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="b9c36-107">Two patterns described in this section suggest ways to do this.</span></span>

 <span data-ttu-id="b9c36-108">❌ non utilizzano codici di errore a causa di problemi che le eccezioni possono influire negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b9c36-108">❌ DO NOT use error codes because of concerns that exceptions might affect performance negatively.</span></span>

 <span data-ttu-id="b9c36-109">Per migliorare le prestazioni, è possibile usare il modello del tester-agente di test o il modello try-Parse, descritto nelle due sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="b9c36-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>

## <a name="tester-doer-pattern"></a><span data-ttu-id="b9c36-110">Modello del tester-agente</span><span class="sxs-lookup"><span data-stu-id="b9c36-110">Tester-Doer Pattern</span></span>
 <span data-ttu-id="b9c36-111">A volte le prestazioni di un membro che genera eccezioni possono essere migliorate suddividendo il membro in due.</span><span class="sxs-lookup"><span data-stu-id="b9c36-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="b9c36-112">Esaminiamo il metodo <xref:System.Collections.Generic.ICollection%601.Add%2A> dell'interfaccia <xref:System.Collections.Generic.ICollection%601>.</span><span class="sxs-lookup"><span data-stu-id="b9c36-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 <span data-ttu-id="b9c36-113">Il metodo `Add` genera un'eccezione se la raccolta è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="b9c36-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="b9c36-114">Questo può essere un problema di prestazioni negli scenari in cui si prevede che la chiamata al metodo abbia spesso esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b9c36-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="b9c36-115">Uno dei modi per attenuare il problema consiste nel verificare se la raccolta è scrivibile prima di tentare di aggiungere un valore.</span><span class="sxs-lookup"><span data-stu-id="b9c36-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 <span data-ttu-id="b9c36-116">Il membro usato per testare una condizione, che in questo esempio è la proprietà `IsReadOnly`, viene definito tester.</span><span class="sxs-lookup"><span data-stu-id="b9c36-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="b9c36-117">Il membro usato per eseguire un'operazione potenzialmente generata, il metodo `Add` nell'esempio, viene definito agente.</span><span class="sxs-lookup"><span data-stu-id="b9c36-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>

 <span data-ttu-id="b9c36-118">✔️ prendere in considerazione il modello del tester per i membri che potrebbero generare eccezioni in scenari comuni per evitare problemi di prestazioni correlati alle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="b9c36-118">✔️ CONSIDER the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

## <a name="try-parse-pattern"></a><span data-ttu-id="b9c36-119">Modello try-parse</span><span class="sxs-lookup"><span data-stu-id="b9c36-119">Try-Parse Pattern</span></span>
 <span data-ttu-id="b9c36-120">Per le API estremamente sensibili alle prestazioni, è consigliabile usare un modello ancora più veloce rispetto a quello descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="b9c36-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="b9c36-121">Il pattern chiama per modificare il nome del membro per creare una test case ben definita parte della semantica dei membri.</span><span class="sxs-lookup"><span data-stu-id="b9c36-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="b9c36-122">Ad esempio, <xref:System.DateTime> definisce un metodo <xref:System.DateTime.Parse%2A> che genera un'eccezione se l'analisi di una stringa ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b9c36-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="b9c36-123">Definisce inoltre un metodo di <xref:System.DateTime.TryParse%2A> corrispondente che tenta di analizzare, ma restituisce false se l'analisi ha esito negativo e restituisce il risultato di un'analisi corretta utilizzando un parametro di `out`.</span><span class="sxs-lookup"><span data-stu-id="b9c36-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>

```csharp
public struct DateTime
{
    public static DateTime Parse(string dateTime)
    {
        ...
    }
    public static bool TryParse(string dateTime, out DateTime result)
    {
        ...
    }
}
```

 <span data-ttu-id="b9c36-124">Quando si usa questo modello, è importante definire la funzionalità try in termini rigorosi.</span><span class="sxs-lookup"><span data-stu-id="b9c36-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="b9c36-125">Se il membro ha esito negativo per un motivo diverso da quello definito correttamente, il membro deve comunque generare un'eccezione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b9c36-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>

 <span data-ttu-id="b9c36-126">✔️ CONSIDERARE il modello try-Parse per i membri che potrebbero generare eccezioni in scenari comuni per evitare problemi di prestazioni correlati alle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="b9c36-126">✔️ CONSIDER the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

 <span data-ttu-id="b9c36-127">✔️ usano il prefisso "Try" e il tipo restituito booleano per i metodi che implementano questo modello.</span><span class="sxs-lookup"><span data-stu-id="b9c36-127">✔️ DO use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>

 <span data-ttu-id="b9c36-128">✔️ forniscono un membro di generazione delle eccezioni per ogni membro usando il modello try-Parse.</span><span class="sxs-lookup"><span data-stu-id="b9c36-128">✔️ DO provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>

 <span data-ttu-id="b9c36-129">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="b9c36-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="b9c36-130">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="b9c36-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="b9c36-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9c36-131">See also</span></span>

- [<span data-ttu-id="b9c36-132">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="b9c36-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="b9c36-133">Linee guida di progettazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="b9c36-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)

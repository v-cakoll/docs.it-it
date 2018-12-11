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
author: KrzysztofCwalina
ms.openlocfilehash: ab125117836545b9a2436347375ed0e08c591c7b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153748"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="c905c-102">Eccezioni e prestazioni</span><span class="sxs-lookup"><span data-stu-id="c905c-102">Exceptions and Performance</span></span>
<span data-ttu-id="c905c-103">Un problema comune correlato alle eccezioni è che se le eccezioni vengono usate per il codice che normalmente ha esito negativo, le prestazioni dell'implementazione saranno inaccettabili.</span><span class="sxs-lookup"><span data-stu-id="c905c-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="c905c-104">Si tratta di un problema valido.</span><span class="sxs-lookup"><span data-stu-id="c905c-104">This is a valid concern.</span></span> <span data-ttu-id="c905c-105">Quando un membro genera un'eccezione, le prestazioni possono essere notevolmente più lenti.</span><span class="sxs-lookup"><span data-stu-id="c905c-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="c905c-106">Tuttavia, è possibile ottenere buone prestazioni rimanendo rigorosamente le linee guida di eccezione che impedisce l'utilizzo di codici di errore.</span><span class="sxs-lookup"><span data-stu-id="c905c-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="c905c-107">Due modelli descritti in questa sezione suggeriscono metodi per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="c905c-107">Two patterns described in this section suggest ways to do this.</span></span>  
  
 <span data-ttu-id="c905c-108">**X DO NOT** utilizzare i codici di errore a causa di problemi che le eccezioni potrebbero influire negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c905c-108">**X DO NOT** use error codes because of concerns that exceptions might affect performance negatively.</span></span>  
  
 <span data-ttu-id="c905c-109">Per migliorare le prestazioni, è possibile usare il Tester-Doer (modello) o il modello di tentare l'analisi, descritte nelle due sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="c905c-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>  
  
## <a name="tester-doer-pattern"></a><span data-ttu-id="c905c-110">Tester-Doer (modello)</span><span class="sxs-lookup"><span data-stu-id="c905c-110">Tester-Doer Pattern</span></span>  
 <span data-ttu-id="c905c-111">A volte le prestazioni di un membro che generano eccezioni possono essere migliorate tramite la suddivisione del membro in due.</span><span class="sxs-lookup"><span data-stu-id="c905c-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="c905c-112">Verrà ora esaminato il <xref:System.Collections.Generic.ICollection%601.Add%2A> metodo del <xref:System.Collections.Generic.ICollection%601> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c905c-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 <span data-ttu-id="c905c-113">Il metodo `Add` genera un'eccezione se la raccolta è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="c905c-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="c905c-114">Può trattarsi di un problema di prestazioni negli scenari in cui è prevista la chiamata al metodo spesso esito negativo.</span><span class="sxs-lookup"><span data-stu-id="c905c-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="c905c-115">Uno dei modi per attenuare il problema consiste nel testare se la raccolta è accessibile in scrittura prima di tentare di aggiungere un valore.</span><span class="sxs-lookup"><span data-stu-id="c905c-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 <span data-ttu-id="c905c-116">Il membro usato per testare una condizione, che in questo esempio è la proprietà `IsReadOnly`, viene definito il tester.</span><span class="sxs-lookup"><span data-stu-id="c905c-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="c905c-117">Il membro usato per eseguire un'operazione potenzialmente generando un'eccezione, il `Add` metodo nel nostro esempio, è noto come dell'agente.</span><span class="sxs-lookup"><span data-stu-id="c905c-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>  
  
 <span data-ttu-id="c905c-118">**✓ CONSIDER** modello Tester-Agente per i membri che potrebbero generare eccezioni in comune scenari per evitare problemi di prestazioni relativi alle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="c905c-118">**✓ CONSIDER** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
## <a name="try-parse-pattern"></a><span data-ttu-id="c905c-119">Modello di tentare l'analisi</span><span class="sxs-lookup"><span data-stu-id="c905c-119">Try-Parse Pattern</span></span>  
 <span data-ttu-id="c905c-120">Per le API molto sensibili alle prestazioni, usare un modello ancora più veloce rispetto al Tester-Doer (modello) descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="c905c-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="c905c-121">Il modello viene chiamato per modificare il nome del membro in modo che un test ben definito caso una parte della semantica di membro.</span><span class="sxs-lookup"><span data-stu-id="c905c-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="c905c-122">Ad esempio, <xref:System.DateTime> definisce un <xref:System.DateTime.Parse%2A> metodo che genera un'eccezione se l'analisi della stringa ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="c905c-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="c905c-123">Definisce inoltre un corrispondente <xref:System.DateTime.TryParse%2A> metodo che tenta di analizzare, ma restituisce false se l'analisi ha esito negativo e restituisce il risultato di una corretta analisi usando un `out` parametro.</span><span class="sxs-lookup"><span data-stu-id="c905c-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>  
  
```  
public struct DateTime {  
    public static DateTime Parse(string dateTime){   
        ...   
    }  
    public static bool TryParse(string dateTime, out DateTime result){  
        ...  
    }  
}  
```  
  
 <span data-ttu-id="c905c-124">Quando si usa questo modello, è importante definire la funzionalità try in termini di tipo strict.</span><span class="sxs-lookup"><span data-stu-id="c905c-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="c905c-125">Se il membro non riesce per qualsiasi motivo diverso da try ben definiti, il membro deve ancora generare un'eccezione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c905c-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>  
  
 <span data-ttu-id="c905c-126">**✓ CONSIDER** il modello di analisi Try per i membri che potrebbero generare eccezioni in comune scenari per evitare problemi di prestazioni relativi alle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="c905c-126">**✓ CONSIDER** the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
 <span data-ttu-id="c905c-127">**✓ DO** utilizzare il prefisso "Try" e un valore booleano tipo restituito per i metodi di implementazione di questo modello.</span><span class="sxs-lookup"><span data-stu-id="c905c-127">**✓ DO** use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>  
  
 <span data-ttu-id="c905c-128">**✓ DO** forniscono un membro che generano eccezioni per ogni membro utilizzando il modello di analisi di riprovare.</span><span class="sxs-lookup"><span data-stu-id="c905c-128">**✓ DO** provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>  
  
 <span data-ttu-id="c905c-129">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="c905c-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c905c-130">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="c905c-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c905c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c905c-131">See also</span></span>

- [<span data-ttu-id="c905c-132">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="c905c-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="c905c-133">Linee guida di progettazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="c905c-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)

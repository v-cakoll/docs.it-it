---
title: Eccezioni e prestazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9a876a818086e0d54251f53a1e8f83cc74a574ae
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="6a72e-102">Eccezioni e prestazioni</span><span class="sxs-lookup"><span data-stu-id="6a72e-102">Exceptions and Performance</span></span>
<span data-ttu-id="6a72e-103">Un problema comune relative alle eccezioni è che se le eccezioni vengono utilizzate per il codice che normalmente non riesce, le prestazioni dell'implementazione saranno inaccettabili.</span><span class="sxs-lookup"><span data-stu-id="6a72e-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="6a72e-104">Si tratta di un problema valido.</span><span class="sxs-lookup"><span data-stu-id="6a72e-104">This is a valid concern.</span></span> <span data-ttu-id="6a72e-105">Quando un membro genera un'eccezione, le prestazioni possono essere notevolmente più lenti.</span><span class="sxs-lookup"><span data-stu-id="6a72e-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="6a72e-106">Tuttavia, è possibile ottenere buone prestazioni rimanendo rigorosamente le linee guida di eccezione che non consentire l'utilizzo di codici di errore.</span><span class="sxs-lookup"><span data-stu-id="6a72e-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="6a72e-107">Due modelli descritti in questa sezione vengono forniti suggerimenti per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="6a72e-107">Two patterns described in this section suggest ways to do this.</span></span>  
  
 <span data-ttu-id="6a72e-108">**X non** utilizzare i codici di errore a causa di problemi che le eccezioni potrebbero influire negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6a72e-108">**X DO NOT** use error codes because of concerns that exceptions might affect performance negatively.</span></span>  
  
 <span data-ttu-id="6a72e-109">Per migliorare le prestazioni, è possibile utilizzare il modello Tester-agente o il modello di analisi di provare, descritti nelle due sezioni.</span><span class="sxs-lookup"><span data-stu-id="6a72e-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>  
  
## <a name="tester-doer-pattern"></a><span data-ttu-id="6a72e-110">Modello Tester-Agente</span><span class="sxs-lookup"><span data-stu-id="6a72e-110">Tester-Doer Pattern</span></span>  
 <span data-ttu-id="6a72e-111">In alcuni casi possono migliorare le prestazioni di un membro che generano eccezioni suddividendo il membro in due.</span><span class="sxs-lookup"><span data-stu-id="6a72e-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="6a72e-112">Esaminiamo il <xref:System.Collections.Generic.ICollection%601.Add%2A> metodo il <xref:System.Collections.Generic.ICollection%601> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6a72e-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 <span data-ttu-id="6a72e-113">Il metodo `Add` genera un'eccezione se la raccolta è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="6a72e-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="6a72e-114">Può trattarsi di un problema di prestazioni in scenari in cui la chiamata al metodo deve avere esito negativo spesso.</span><span class="sxs-lookup"><span data-stu-id="6a72e-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="6a72e-115">Uno dei modi per risolvere il problema è per verificare se la raccolta è accessibile in scrittura prima di tentare di aggiungere un valore.</span><span class="sxs-lookup"><span data-stu-id="6a72e-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 <span data-ttu-id="6a72e-116">Il membro utilizzato per testare una condizione, che nel nostro esempio è la proprietà `IsReadOnly`, viene definito il tester.</span><span class="sxs-lookup"><span data-stu-id="6a72e-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="6a72e-117">Il membro usato per eseguire un'operazione potenzialmente generando un'eccezione, il `Add` metodo in questo esempio, è detto dell'agente.</span><span class="sxs-lookup"><span data-stu-id="6a72e-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>  
  
 <span data-ttu-id="6a72e-118">**Provare a ✓** modello Tester-Agente per i membri che potrebbero generare eccezioni in comune scenari per evitare problemi di prestazioni relativi alle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="6a72e-118">**✓ CONSIDER** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
## <a name="try-parse-pattern"></a><span data-ttu-id="6a72e-119">Try-analisi modello</span><span class="sxs-lookup"><span data-stu-id="6a72e-119">Try-Parse Pattern</span></span>  
 <span data-ttu-id="6a72e-120">Per le API molto sensibili alle prestazioni, deve essere utilizzato un modello ancora più rapido del modello Tester-Agente descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="6a72e-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="6a72e-121">Il modello necessario modificare il nome del membro per eseguire un test ben definito di caso di una parte della semantica di membro.</span><span class="sxs-lookup"><span data-stu-id="6a72e-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="6a72e-122">Ad esempio, <xref:System.DateTime> definisce un <xref:System.DateTime.Parse%2A> metodo che genera un'eccezione se l'analisi di una stringa non riesce.</span><span class="sxs-lookup"><span data-stu-id="6a72e-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="6a72e-123">Definisce inoltre un corrispondente <xref:System.DateTime.TryParse%2A> metodo che tenta di analizzare, ma restituisce false se l'analisi ha esito negativo e restituisce il risultato di una corretta analisi utilizzando un `out` parametro.</span><span class="sxs-lookup"><span data-stu-id="6a72e-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>  
  
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
  
 <span data-ttu-id="6a72e-124">Quando si utilizza questo modello, è importante definire la funzionalità try in termini di tipo strict.</span><span class="sxs-lookup"><span data-stu-id="6a72e-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="6a72e-125">Se il membro non riesce per qualsiasi ragione diversa dalla try ben definito, il membro deve ancora generare un'eccezione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6a72e-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>  
  
 <span data-ttu-id="6a72e-126">**Provare a ✓** il modello di analisi di provare per i membri che potrebbero generare eccezioni in comune scenari per evitare problemi di prestazioni relativi alle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="6a72e-126">**✓ CONSIDER** the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
 <span data-ttu-id="6a72e-127">**✓ SI** utilizzare il prefisso "Try" e un valore booleano tipo restituito per i metodi di implementazione di questo modello.</span><span class="sxs-lookup"><span data-stu-id="6a72e-127">**✓ DO** use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>  
  
 <span data-ttu-id="6a72e-128">**✓ SI** forniscono un membro che generano eccezioni per ogni membro utilizzando il modello di analisi di riprovare.</span><span class="sxs-lookup"><span data-stu-id="6a72e-128">**✓ DO** provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>  
  
 <span data-ttu-id="6a72e-129">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="6a72e-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6a72e-130">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6a72e-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a72e-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a72e-131">See Also</span></span>  
 [<span data-ttu-id="6a72e-132">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="6a72e-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="6a72e-133">Linee guida di progettazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="6a72e-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)

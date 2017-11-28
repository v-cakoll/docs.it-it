---
title: Specificare dinamicamente i filtri dei predicati in fase di esecuzione
description: 'Procedura: specificare dinamicamente i filtri dei predicati in fase di esecuzione.'
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: 06bc594ac1357e7dca6c182fa28310559a79875c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="60950-104">Specificare dinamicamente i filtri dei predicati in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="60950-104">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="60950-105">In alcuni casi, fino alla fase di esecuzione non si sa quanti predicati è necessario applicare agli elementi di origine nella clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="60950-105">In some cases you do not know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="60950-106">Un modo per specificare dinamicamente più filtri di predicato consiste nell'usare il metodo <xref:System.Linq.Enumerable.Contains%2A>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="60950-106">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="60950-107">L'esempio si costruisce in due modi.</span><span class="sxs-lookup"><span data-stu-id="60950-107">The example is constructed in two ways.</span></span> <span data-ttu-id="60950-108">Innanzitutto viene eseguito il progetto applicando filtri basati sui valori forniti nel programma.</span><span class="sxs-lookup"><span data-stu-id="60950-108">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="60950-109">Il progetto viene quindi eseguito di nuovo usando l'input fornito in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="60950-109">Then the project is run again by using input provided at run time.</span></span>  
  
## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="60950-110">Per applicare un filtro usando il metodo Contains</span><span class="sxs-lookup"><span data-stu-id="60950-110">To filter by using the Contains method</span></span>  
  
1.  <span data-ttu-id="60950-111">Aprire una nuova applicazione console e denominarla `PredicateFilters`.</span><span class="sxs-lookup"><span data-stu-id="60950-111">Open a new console application and name it `PredicateFilters`.</span></span>  
  
2.  <span data-ttu-id="60950-112">Copiare la classe `StudentClass` da [Eseguire query in una raccolta di oggetti](query-a-collection-of-objects.md) e incollarla nello spazio dei nomi `PredicateFilters` sotto la classe `Program`.</span><span class="sxs-lookup"><span data-stu-id="60950-112">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="60950-113">`StudentClass` fornisce un elenco di oggetti `Student`.</span><span class="sxs-lookup"><span data-stu-id="60950-113">`StudentClass` provides a list of `Student` objects.</span></span>  
  
3.  <span data-ttu-id="60950-114">Impostare il metodo `Main` come commento in `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="60950-114">Comment out the `Main` method in `StudentClass`.</span></span>  
  
4.  <span data-ttu-id="60950-115">Sostituire la classe `Program` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="60950-115">Replace class `Program` with the following code.</span></span>  
  
     [!code-csharp[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]  
  
5.  <span data-ttu-id="60950-116">Aggiungere la riga seguente al metodo `Main` nella classe `DynamicPredicates`, sotto la dichiarazione di `ids`.</span><span class="sxs-lookup"><span data-stu-id="60950-116">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>  
  
     ```csharp
     QueryById(ids);
     ```

6.  <span data-ttu-id="60950-117">Eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="60950-117">Run the project.</span></span>  
  
7.  <span data-ttu-id="60950-118">Nella finestra della console verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="60950-118">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="60950-119">Garcia: 114</span><span class="sxs-lookup"><span data-stu-id="60950-119">Garcia: 114</span></span>  
  
     <span data-ttu-id="60950-120">O'Donnell: 112</span><span class="sxs-lookup"><span data-stu-id="60950-120">O'Donnell: 112</span></span>  
  
     <span data-ttu-id="60950-121">Omelchenko: 111</span><span class="sxs-lookup"><span data-stu-id="60950-121">Omelchenko: 111</span></span>  
  
8.  <span data-ttu-id="60950-122">Il passaggio successivo consiste nell'eseguire nuovamente il progetto, questa volta usando l'input immesso in fase di esecuzione anziché la matrice `ids`.</span><span class="sxs-lookup"><span data-stu-id="60950-122">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="60950-123">Cambiare `QueryByID(ids)` in `QueryByID(args)` nel metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="60950-123">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>  
  
9. <span data-ttu-id="60950-124">Eseguire il progetto con gli argomenti della riga di comando `122 117 120 115`.</span><span class="sxs-lookup"><span data-stu-id="60950-124">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="60950-125">Quando il progetto viene eseguito, questi valori diventano elementi di `args`, il parametro del metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="60950-125">When the project is run, those values become elements of `args`, the parameter of the `Main` method..</span></span>  
  
10. <span data-ttu-id="60950-126">Nella finestra della console verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="60950-126">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="60950-127">Adams: 120</span><span class="sxs-lookup"><span data-stu-id="60950-127">Adams: 120</span></span>  
  
     <span data-ttu-id="60950-128">Feng: 117</span><span class="sxs-lookup"><span data-stu-id="60950-128">Feng: 117</span></span>  
  
     <span data-ttu-id="60950-129">Garcia: 115</span><span class="sxs-lookup"><span data-stu-id="60950-129">Garcia: 115</span></span>  
  
     <span data-ttu-id="60950-130">Tucker: 122</span><span class="sxs-lookup"><span data-stu-id="60950-130">Tucker: 122</span></span>  
  
## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="60950-131">Per filtrare tramite un'istruzione switch</span><span class="sxs-lookup"><span data-stu-id="60950-131">To filter by using a switch statement</span></span>  
  
1.  <span data-ttu-id="60950-132">È possibile usare un'istruzione `switch` per scegliere tra query alternative predefinite.</span><span class="sxs-lookup"><span data-stu-id="60950-132">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="60950-133">Nell'esempio seguente `studentQuery` usa una clausola `where` diversa a seconda di quale livello o anno viene specificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="60950-133">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>  
  
2.  <span data-ttu-id="60950-134">Copiare il metodo seguente e incollarlo nella classe `DynamicPredicates`.</span><span class="sxs-lookup"><span data-stu-id="60950-134">Copy the following method and paste it into class `DynamicPredicates`.</span></span>  
  
     [!code-csharp[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]  
  
3.  <span data-ttu-id="60950-135">Nel metodo `Main` sostituire la chiamata di `QueryByID` con la chiamata seguente che invia il primo elemento dalla matrice `args` come suo argomento: `QueryByYear(args[0])`.</span><span class="sxs-lookup"><span data-stu-id="60950-135">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>  
  
4.  <span data-ttu-id="60950-136">Eseguire il progetto usando come argomento della riga di comando un valore intero compreso tra 1 e 4.</span><span class="sxs-lookup"><span data-stu-id="60950-136">Run the project with a command line argument of an integer value between 1 and 4.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="60950-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60950-137">See Also</span></span>  
 [<span data-ttu-id="60950-138">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="60950-138">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="60950-139">Clausola where</span><span class="sxs-lookup"><span data-stu-id="60950-139">where clause</span></span>](../language-reference/keywords/where-clause.md)

---
title: Specificare dinamicamente i filtri dei predicati in fase di esecuzione (LINQ in C#)
description: Informazioni su come specificare dinamicamente i filtri dei predicati in fase di esecuzione usando LINQ in C#.
ms.date: 12/1/2016
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: ece5940edd615f30acab06a429de300e27811a66
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2018
ms.locfileid: "52296074"
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="4cf66-103">Specificare dinamicamente i filtri dei predicati in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="4cf66-103">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="4cf66-104">In alcuni casi, fino alla fase di esecuzione non si sa quanti predicati è necessario applicare agli elementi di origine nella clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="4cf66-104">In some cases, you don't know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="4cf66-105">Un modo per specificare dinamicamente più filtri di predicato consiste nell'usare il metodo <xref:System.Linq.Enumerable.Contains%2A>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4cf66-105">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="4cf66-106">L'esempio si costruisce in due modi.</span><span class="sxs-lookup"><span data-stu-id="4cf66-106">The example is constructed in two ways.</span></span> <span data-ttu-id="4cf66-107">Innanzitutto viene eseguito il progetto applicando filtri basati sui valori forniti nel programma.</span><span class="sxs-lookup"><span data-stu-id="4cf66-107">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="4cf66-108">Il progetto viene quindi eseguito di nuovo usando l'input fornito in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4cf66-108">Then the project is run again by using input provided at run time.</span></span>

## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="4cf66-109">Per applicare un filtro usando il metodo Contains</span><span class="sxs-lookup"><span data-stu-id="4cf66-109">To filter by using the Contains method</span></span>

1. <span data-ttu-id="4cf66-110">Aprire una nuova applicazione console e denominarla `PredicateFilters`.</span><span class="sxs-lookup"><span data-stu-id="4cf66-110">Open a new console application and name it `PredicateFilters`.</span></span>

2. <span data-ttu-id="4cf66-111">Copiare la classe `StudentClass` da [Eseguire query in una raccolta di oggetti](query-a-collection-of-objects.md) e incollarla nello spazio dei nomi `PredicateFilters` sotto la classe `Program`.</span><span class="sxs-lookup"><span data-stu-id="4cf66-111">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="4cf66-112">`StudentClass` fornisce un elenco di oggetti `Student`.</span><span class="sxs-lookup"><span data-stu-id="4cf66-112">`StudentClass` provides a list of `Student` objects.</span></span>

3. <span data-ttu-id="4cf66-113">Impostare il metodo `Main` come commento in `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="4cf66-113">Comment out the `Main` method in `StudentClass`.</span></span>

4. <span data-ttu-id="4cf66-114">Sostituire la classe `Program` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4cf66-114">Replace class `Program` with the following code:</span></span>

     [!code-csharp[csProgGuideLINQ#26](~/samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]

5. <span data-ttu-id="4cf66-115">Aggiungere la riga seguente al metodo `Main` nella classe `DynamicPredicates`, sotto la dichiarazione di `ids`.</span><span class="sxs-lookup"><span data-stu-id="4cf66-115">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>

     ```csharp
     QueryById(ids);
     ```

6. <span data-ttu-id="4cf66-116">Eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="4cf66-116">Run the project.</span></span>

7. <span data-ttu-id="4cf66-117">Nella finestra della console verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="4cf66-117">The following output is displayed in a console window:</span></span>

     <span data-ttu-id="4cf66-118">Garcia: 114</span><span class="sxs-lookup"><span data-stu-id="4cf66-118">Garcia: 114</span></span>

     <span data-ttu-id="4cf66-119">O'Donnell: 112</span><span class="sxs-lookup"><span data-stu-id="4cf66-119">O'Donnell: 112</span></span>

     <span data-ttu-id="4cf66-120">Omelchenko: 111</span><span class="sxs-lookup"><span data-stu-id="4cf66-120">Omelchenko: 111</span></span>

8. <span data-ttu-id="4cf66-121">Il passaggio successivo consiste nell'eseguire nuovamente il progetto, questa volta usando l'input immesso in fase di esecuzione anziché la matrice `ids`.</span><span class="sxs-lookup"><span data-stu-id="4cf66-121">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="4cf66-122">Cambiare `QueryByID(ids)` in `QueryByID(args)` nel metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="4cf66-122">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>

9. <span data-ttu-id="4cf66-123">Eseguire il progetto con gli argomenti della riga di comando `122 117 120 115`.</span><span class="sxs-lookup"><span data-stu-id="4cf66-123">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="4cf66-124">Quando il progetto viene eseguito, questi valori diventano elementi di `args`, il parametro del metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="4cf66-124">When the project is run, those values become elements of `args`, the parameter of the `Main` method.</span></span>

10. <span data-ttu-id="4cf66-125">Nella finestra della console verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="4cf66-125">The following output is displayed in a console window:</span></span>

     <span data-ttu-id="4cf66-126">Adams: 120</span><span class="sxs-lookup"><span data-stu-id="4cf66-126">Adams: 120</span></span>

     <span data-ttu-id="4cf66-127">Feng: 117</span><span class="sxs-lookup"><span data-stu-id="4cf66-127">Feng: 117</span></span>

     <span data-ttu-id="4cf66-128">Garcia: 115</span><span class="sxs-lookup"><span data-stu-id="4cf66-128">Garcia: 115</span></span>

     <span data-ttu-id="4cf66-129">Tucker: 122</span><span class="sxs-lookup"><span data-stu-id="4cf66-129">Tucker: 122</span></span>

## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="4cf66-130">Per filtrare tramite un'istruzione switch</span><span class="sxs-lookup"><span data-stu-id="4cf66-130">To filter by using a switch statement</span></span>

1. <span data-ttu-id="4cf66-131">È possibile usare un'istruzione `switch` per scegliere tra query alternative predefinite.</span><span class="sxs-lookup"><span data-stu-id="4cf66-131">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="4cf66-132">Nell'esempio seguente `studentQuery` usa una clausola `where` diversa a seconda di quale livello o anno viene specificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4cf66-132">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>

2. <span data-ttu-id="4cf66-133">Copiare il metodo seguente e incollarlo nella classe `DynamicPredicates`.</span><span class="sxs-lookup"><span data-stu-id="4cf66-133">Copy the following method and paste it into class `DynamicPredicates`.</span></span>

     [!code-csharp[csProgGuideLINQ#27](~/samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]

3. <span data-ttu-id="4cf66-134">Nel metodo `Main` sostituire la chiamata di `QueryByID` con la chiamata seguente che invia il primo elemento dalla matrice `args` come suo argomento: `QueryByYear(args[0])`.</span><span class="sxs-lookup"><span data-stu-id="4cf66-134">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>

4. <span data-ttu-id="4cf66-135">Eseguire il progetto usando come argomento della riga di comando un valore intero compreso tra 1 e 4.</span><span class="sxs-lookup"><span data-stu-id="4cf66-135">Run the project with a command line argument of an integer value between 1 and 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="4cf66-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cf66-136">See also</span></span>

- [<span data-ttu-id="4cf66-137">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="4cf66-137">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="4cf66-138">Clausola where</span><span class="sxs-lookup"><span data-stu-id="4cf66-138">where clause</span></span>](../language-reference/keywords/where-clause.md)

---
title: Dimensioni di matrice in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: 0b4e7c9e253f94e1e28700c8669d28799ab69d91
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836935"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="c241a-102">Dimensioni di matrice in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c241a-102">Array Dimensions in Visual Basic</span></span>
<span data-ttu-id="c241a-103">Oggetto *dimensione* è una direzione in cui è possibile modificare la specifica di elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="c241a-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="c241a-104">Matrice contenente le vendite totali per ogni giorno del mese ha una dimensione (il giorno del mese).</span><span class="sxs-lookup"><span data-stu-id="c241a-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="c241a-105">Matrice contenente le vendite totali per reparto per ciascun giorno del mese ha due dimensioni (il numero di reparto e il giorno del mese).</span><span class="sxs-lookup"><span data-stu-id="c241a-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="c241a-106">Il numero di dimensioni è una matrice viene chiamato relativa *rank*.</span><span class="sxs-lookup"><span data-stu-id="c241a-106">The number of dimensions an array has is called its *rank*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c241a-107">È possibile usare il <xref:System.Array.Rank%2A> proprietà per determinare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="c241a-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>  
  
## <a name="working-with-dimensions"></a><span data-ttu-id="c241a-108">Utilizzo delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="c241a-108">Working with Dimensions</span></span>  
 <span data-ttu-id="c241a-109">È possibile specificare un elemento della matrice fornendo un' *indice* oppure *pedice* per ognuna delle relative dimensioni.</span><span class="sxs-lookup"><span data-stu-id="c241a-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="c241a-110">Gli elementi sono contigui in ogni dimensione dall'indice 0 dell'indice più alto per tale dimensione.</span><span class="sxs-lookup"><span data-stu-id="c241a-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>  
  
 <span data-ttu-id="c241a-111">Le illustrazioni seguenti mostrano la struttura concettuale di matrici con intervalli diversi.</span><span class="sxs-lookup"><span data-stu-id="c241a-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="c241a-112">Ogni elemento nelle figure Mostra i valori di indice che vi accedono.</span><span class="sxs-lookup"><span data-stu-id="c241a-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="c241a-113">Ad esempio, è possibile accedere il primo elemento della seconda riga della matrice bidimensionale specificando gli indici `(1, 0)`.</span><span class="sxs-lookup"><span data-stu-id="c241a-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>  
  
 ![Diagramma che mostra una matrice unidimensionale.](./media/array-dimensions/one-dimensional-array.gif)  
  
 ![Diagramma che mostra una matrice bidimensionale.](./media/array-dimensions/two-dimensional-array.gif)  
  
 ![Diagramma che mostra una matrice tridimensionale.](./media/array-dimensions/three-dimensional-array.gif)  
  
### <a name="one-dimension"></a><span data-ttu-id="c241a-117">Una dimensione</span><span class="sxs-lookup"><span data-stu-id="c241a-117">One Dimension</span></span>  
 <span data-ttu-id="c241a-118">Le matrici molti hanno solo una dimensione, ad esempio il numero di persone di ogni età.</span><span class="sxs-lookup"><span data-stu-id="c241a-118">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="c241a-119">L'unico requisito per specificare un elemento è il periodo di validità per il quale questo elemento contiene il conteggio.</span><span class="sxs-lookup"><span data-stu-id="c241a-119">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="c241a-120">Pertanto, ad esempio una matrice Usa un solo indice.</span><span class="sxs-lookup"><span data-stu-id="c241a-120">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="c241a-121">L'esempio seguente dichiara una variabile per contenere una *matrice unidimensionale* di età conta rivolto a 0 e 120.</span><span class="sxs-lookup"><span data-stu-id="c241a-121">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a><span data-ttu-id="c241a-122">Due dimensioni</span><span class="sxs-lookup"><span data-stu-id="c241a-122">Two Dimensions</span></span>  
 <span data-ttu-id="c241a-123">Alcuni array di avere due dimensioni, ad esempio il numero di uffici in ogni parte intera di ogni compilazione in un campus.</span><span class="sxs-lookup"><span data-stu-id="c241a-123">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="c241a-124">La specifica di un elemento richiede che il numero di compilazione e la parte intera e ogni elemento contiene il conteggio per la combinazione di edificio e piano.</span><span class="sxs-lookup"><span data-stu-id="c241a-124">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="c241a-125">Pertanto, ad esempio una matrice usa due indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="c241a-125">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="c241a-126">L'esempio seguente dichiara una variabile per contenere una *matrice bidimensionale* dei conteggi di office, per gli edifici 0 e 40 e piani compresi tra 0 a 5.</span><span class="sxs-lookup"><span data-stu-id="c241a-126">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 <span data-ttu-id="c241a-127">Una matrice bidimensionale viene anche chiamata un' *matrice rettangolare*.</span><span class="sxs-lookup"><span data-stu-id="c241a-127">A two-dimensional array is also called a *rectangular array*.</span></span>  
  
### <a name="three-dimensions"></a><span data-ttu-id="c241a-128">Tre dimensioni</span><span class="sxs-lookup"><span data-stu-id="c241a-128">Three Dimensions</span></span>  
 <span data-ttu-id="c241a-129">Le matrici alcuni hanno tre dimensioni, ad esempio i valori nello spazio tridimensionale.</span><span class="sxs-lookup"><span data-stu-id="c241a-129">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="c241a-130">Ad esempio una matrice Usa tre indici, che in questo caso rappresentano x, y e le coordinate z spazio fisico.</span><span class="sxs-lookup"><span data-stu-id="c241a-130">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="c241a-131">L'esempio seguente dichiara una variabile per contenere una *matrice tridimensionale* della temperatura dell'aria in momenti diversi in un volume tridimensionale.</span><span class="sxs-lookup"><span data-stu-id="c241a-131">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a><span data-ttu-id="c241a-132">Più di tre dimensioni</span><span class="sxs-lookup"><span data-stu-id="c241a-132">More than Three Dimensions</span></span>  
 <span data-ttu-id="c241a-133">Anche se una matrice può avere un massimo di 32 dimensioni, è raro che ne abbia più di tre.</span><span class="sxs-lookup"><span data-stu-id="c241a-133">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c241a-134">Quando si aggiungono le dimensioni a una matrice, l'archiviazione totale necessario per la matrice aumenta notevolmente, pertanto si consiglia di utilizzare le matrici multidimensionali con cautela.</span><span class="sxs-lookup"><span data-stu-id="c241a-134">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>  
  
## <a name="using-different-dimensions"></a><span data-ttu-id="c241a-135">Utilizzo di dimensioni diverse</span><span class="sxs-lookup"><span data-stu-id="c241a-135">Using Different Dimensions</span></span>  
 <span data-ttu-id="c241a-136">Si supponga che si desidera rilevare gli importi delle vendite per ogni giorno del mese attuale.</span><span class="sxs-lookup"><span data-stu-id="c241a-136">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="c241a-137">È possibile dichiarare una matrice unidimensionale con gli 31 elementi, uno per ogni giorno del mese, come illustrato nell'esempio seguente viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="c241a-137">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 <span data-ttu-id="c241a-138">Ora si supponga che si desidera rilevare le stesse informazioni non solo per tutti i giorni del mese, ma anche per ogni mese dell'anno.</span><span class="sxs-lookup"><span data-stu-id="c241a-138">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="c241a-139">È possibile dichiarare una matrice bidimensionale di 12 righe (per i mesi) e 31 colonne (per i giorni), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c241a-139">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 <span data-ttu-id="c241a-140">Ora si supponga che si decide di avere la matrice contengono informazioni per più di un anno.</span><span class="sxs-lookup"><span data-stu-id="c241a-140">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="c241a-141">Se si vuole tenere traccia di importi delle vendite per 5 anni, è possibile dichiarare una matrice tridimensionale con livelli di 5, 12 righe e 31 colonne, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c241a-141">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 <span data-ttu-id="c241a-142">Si noti che, poiché ogni indice varia da 0 al valore massimo, ciascuna dimensione del `salesAmounts` viene dichiarata come uno in meno rispetto alla lunghezza desiderata per la dimensione.</span><span class="sxs-lookup"><span data-stu-id="c241a-142">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="c241a-143">Si noti inoltre che le dimensioni della matrice aumentano con ogni nuova dimensione.</span><span class="sxs-lookup"><span data-stu-id="c241a-143">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="c241a-144">Le tre dimensioni negli esempi precedenti sono 1860 elementi, 372 e 31.</span><span class="sxs-lookup"><span data-stu-id="c241a-144">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c241a-145">È possibile creare una matrice senza utilizzare il `Dim` istruzione o il `New` clausola.</span><span class="sxs-lookup"><span data-stu-id="c241a-145">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="c241a-146">Ad esempio, è possibile chiamare il <xref:System.Array.CreateInstance%2A> metodo o un altro componente può passare al codice una matrice creata in questo modo.</span><span class="sxs-lookup"><span data-stu-id="c241a-146">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="c241a-147">Ad esempio una matrice può avere un limite inferiore diverso da 0.</span><span class="sxs-lookup"><span data-stu-id="c241a-147">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="c241a-148">È sempre possibile verificare il limite inferiore di una dimensione utilizzando la <xref:System.Array.GetLowerBound%2A> metodo o il `LBound` (funzione).</span><span class="sxs-lookup"><span data-stu-id="c241a-148">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c241a-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c241a-149">See also</span></span>

- [<span data-ttu-id="c241a-150">Matrici</span><span class="sxs-lookup"><span data-stu-id="c241a-150">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="c241a-151">Risoluzione dei problemi relativi alle matrici</span><span class="sxs-lookup"><span data-stu-id="c241a-151">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)

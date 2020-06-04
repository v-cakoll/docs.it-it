---
title: Dimensioni di matrice
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: f971f0c3693177adbcb8869d487e3ad41d49ddc2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413104"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="efbb1-102">Dimensioni di matrice in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="efbb1-102">Array Dimensions in Visual Basic</span></span>

<span data-ttu-id="efbb1-103">Una *dimensione* rappresenta una direzione in cui è possibile variare la specifica degli elementi di una matrice.</span><span class="sxs-lookup"><span data-stu-id="efbb1-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="efbb1-104">Una matrice che contiene il totale delle vendite per ogni giorno del mese ha una dimensione (il giorno del mese).</span><span class="sxs-lookup"><span data-stu-id="efbb1-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="efbb1-105">Una matrice che contiene il totale delle vendite per reparto per ogni giorno del mese ha due dimensioni, ovvero il numero del reparto e il giorno del mese.</span><span class="sxs-lookup"><span data-stu-id="efbb1-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="efbb1-106">Il numero di dimensioni di una matrice è denominato *rango*.</span><span class="sxs-lookup"><span data-stu-id="efbb1-106">The number of dimensions an array has is called its *rank*.</span></span>

> [!NOTE]
> <span data-ttu-id="efbb1-107">È possibile usare la <xref:System.Array.Rank%2A> proprietà per determinare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="efbb1-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>

## <a name="working-with-dimensions"></a><span data-ttu-id="efbb1-108">Utilizzo delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="efbb1-108">Working with Dimensions</span></span>

<span data-ttu-id="efbb1-109">Per specificare un elemento di una matrice, è necessario specificare un indice *o un* *Indice* per ogni dimensione.</span><span class="sxs-lookup"><span data-stu-id="efbb1-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="efbb1-110">Gli elementi sono contigui lungo ogni dimensione dall'indice 0 all'indice più alto per tale dimensione.</span><span class="sxs-lookup"><span data-stu-id="efbb1-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>

<span data-ttu-id="efbb1-111">Nelle illustrazioni seguenti viene illustrata la struttura concettuale di matrici con diverse classificazioni.</span><span class="sxs-lookup"><span data-stu-id="efbb1-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="efbb1-112">Ogni elemento nelle illustrazioni mostra i valori di indice che vi accedono.</span><span class="sxs-lookup"><span data-stu-id="efbb1-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="efbb1-113">Ad esempio, è possibile accedere al primo elemento della seconda riga della matrice bidimensionale specificando gli indici `(1, 0)` .</span><span class="sxs-lookup"><span data-stu-id="efbb1-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>

![Diagramma che mostra una matrice unidimensionale.](./media/array-dimensions/one-dimensional-array.gif)

![Diagramma che mostra una matrice bidimensionale.](./media/array-dimensions/two-dimensional-array.gif)

![Diagramma che mostra una matrice tridimensionale.](./media/array-dimensions/three-dimensional-array.gif)

### <a name="one-dimension"></a><span data-ttu-id="efbb1-117">Una dimensione</span><span class="sxs-lookup"><span data-stu-id="efbb1-117">One Dimension</span></span>

<span data-ttu-id="efbb1-118">Molte matrici hanno solo una dimensione, ad esempio il numero di persone di ogni età.</span><span class="sxs-lookup"><span data-stu-id="efbb1-118">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="efbb1-119">L'unico requisito per specificare un elemento è l'età per cui l'elemento include il conteggio.</span><span class="sxs-lookup"><span data-stu-id="efbb1-119">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="efbb1-120">Pertanto, una matrice di questo tipo utilizza un solo indice.</span><span class="sxs-lookup"><span data-stu-id="efbb1-120">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="efbb1-121">Nell'esempio seguente viene dichiarata una variabile per includere una *matrice unidimensionale* di età compresa tra 0 e 120.</span><span class="sxs-lookup"><span data-stu-id="efbb1-121">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>

```vb
Dim ageCounts(120) As UInteger
```

### <a name="two-dimensions"></a><span data-ttu-id="efbb1-122">Due dimensioni</span><span class="sxs-lookup"><span data-stu-id="efbb1-122">Two Dimensions</span></span>

<span data-ttu-id="efbb1-123">Alcune matrici hanno due dimensioni, ad esempio il numero di uffici in ogni piano di ogni edificio in un campus.</span><span class="sxs-lookup"><span data-stu-id="efbb1-123">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="efbb1-124">La specifica di un elemento richiede il numero di edificio e il piano e ogni elemento include il conteggio per la combinazione di compilazione e piano.</span><span class="sxs-lookup"><span data-stu-id="efbb1-124">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="efbb1-125">Pertanto, una matrice di questo tipo utilizza due indici.</span><span class="sxs-lookup"><span data-stu-id="efbb1-125">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="efbb1-126">Nell'esempio seguente viene dichiarata una variabile in cui è contenuta una *matrice bidimensionale* di conteggi di Office, per edifici da 0 a 40 e da piani 0 a 5.</span><span class="sxs-lookup"><span data-stu-id="efbb1-126">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>

```vb
Dim officeCounts(40, 5) As Byte
```

<span data-ttu-id="efbb1-127">Una matrice bidimensionale viene definita anche *matrice rettangolare*.</span><span class="sxs-lookup"><span data-stu-id="efbb1-127">A two-dimensional array is also called a *rectangular array*.</span></span>

### <a name="three-dimensions"></a><span data-ttu-id="efbb1-128">Tre dimensioni</span><span class="sxs-lookup"><span data-stu-id="efbb1-128">Three Dimensions</span></span>

<span data-ttu-id="efbb1-129">Alcune matrici hanno tre dimensioni, ad esempio valori nello spazio tridimensionale.</span><span class="sxs-lookup"><span data-stu-id="efbb1-129">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="efbb1-130">Tale matrice utilizza tre indici, che in questo caso rappresentano le coordinate x, y e z dello spazio fisico.</span><span class="sxs-lookup"><span data-stu-id="efbb1-130">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="efbb1-131">Nell'esempio seguente viene dichiarata una variabile in cui è contenuta una *matrice tridimensionale* di temperature aeree in vari punti in un volume tridimensionale.</span><span class="sxs-lookup"><span data-stu-id="efbb1-131">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>

```vb
Dim airTemperatures(99, 99, 24) As Single
```

### <a name="more-than-three-dimensions"></a><span data-ttu-id="efbb1-132">Più di tre dimensioni</span><span class="sxs-lookup"><span data-stu-id="efbb1-132">More than Three Dimensions</span></span>

<span data-ttu-id="efbb1-133">Sebbene una matrice possa avere un numero di dimensioni pari a 32, è raro avere più di tre dimensioni.</span><span class="sxs-lookup"><span data-stu-id="efbb1-133">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>

> [!NOTE]
> <span data-ttu-id="efbb1-134">Quando si aggiungono dimensioni a una matrice, lo spazio di archiviazione totale necessario per l'array aumenta considerevolmente, pertanto è opportuno utilizzare matrici multidimensionali con cautela.</span><span class="sxs-lookup"><span data-stu-id="efbb1-134">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>

## <a name="using-different-dimensions"></a><span data-ttu-id="efbb1-135">Utilizzo di dimensioni diverse</span><span class="sxs-lookup"><span data-stu-id="efbb1-135">Using Different Dimensions</span></span>

<span data-ttu-id="efbb1-136">Si supponga di voler tenere traccia degli importi delle vendite per ogni giorno del mese corrente.</span><span class="sxs-lookup"><span data-stu-id="efbb1-136">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="efbb1-137">È possibile dichiarare una matrice unidimensionale con 31 elementi, uno per ogni giorno del mese, come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="efbb1-137">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>

```vb
Dim salesAmounts(30) As Double
```

<span data-ttu-id="efbb1-138">Si supponga ora di voler tenere traccia delle stesse informazioni non solo per ogni giorno del mese, ma anche per ogni mese dell'anno.</span><span class="sxs-lookup"><span data-stu-id="efbb1-138">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="efbb1-139">È possibile dichiarare una matrice bidimensionale con 12 righe (per i mesi) e 31 colonne (per i giorni), come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="efbb1-139">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>

```vb
Dim salesAmounts(11, 30) As Double
```

<span data-ttu-id="efbb1-140">Si supponga ora di decidere se la matrice contiene informazioni per più di un anno.</span><span class="sxs-lookup"><span data-stu-id="efbb1-140">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="efbb1-141">Se si desidera tenere traccia degli importi delle vendite per 5 anni, è possibile dichiarare una matrice tridimensionale con 5 livelli, 12 righe e 31 colonne, come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="efbb1-141">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>

```vb
Dim salesAmounts(4, 11, 30) As Double
```

<span data-ttu-id="efbb1-142">Si noti che, poiché ogni indice varia da 0 al massimo, ogni dimensione di `salesAmounts` viene dichiarata come una minore della lunghezza richiesta per tale dimensione.</span><span class="sxs-lookup"><span data-stu-id="efbb1-142">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="efbb1-143">Si noti inoltre che le dimensioni della matrice aumentano con ogni nuova dimensione.</span><span class="sxs-lookup"><span data-stu-id="efbb1-143">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="efbb1-144">Le tre dimensioni degli esempi precedenti sono rispettivamente 31, 372 e 1.860.</span><span class="sxs-lookup"><span data-stu-id="efbb1-144">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="efbb1-145">È possibile creare una matrice senza utilizzare l' `Dim` istruzione o la `New` clausola.</span><span class="sxs-lookup"><span data-stu-id="efbb1-145">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="efbb1-146">Ad esempio, è possibile chiamare il <xref:System.Array.CreateInstance%2A> metodo oppure un altro componente può passare il codice a una matrice creata in questo modo.</span><span class="sxs-lookup"><span data-stu-id="efbb1-146">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="efbb1-147">Una matrice di questo tipo può avere un limite inferiore diverso da 0.</span><span class="sxs-lookup"><span data-stu-id="efbb1-147">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="efbb1-148">È sempre possibile verificare il limite inferiore di una dimensione tramite il <xref:System.Array.GetLowerBound%2A> metodo o la `LBound` funzione.</span><span class="sxs-lookup"><span data-stu-id="efbb1-148">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="efbb1-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efbb1-149">See also</span></span>

- [<span data-ttu-id="efbb1-150">Matrici</span><span class="sxs-lookup"><span data-stu-id="efbb1-150">Arrays</span></span>](index.md)
- [<span data-ttu-id="efbb1-151">Risoluzione dei problemi relativi alle matrici</span><span class="sxs-lookup"><span data-stu-id="efbb1-151">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)

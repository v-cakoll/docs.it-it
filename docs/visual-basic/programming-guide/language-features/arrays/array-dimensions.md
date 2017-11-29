---
title: Dimensioni di matrice in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21e170ca5942862a26e05428fffaea7d1e875e19
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="f7362-102">Dimensioni di matrice in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7362-102">Array Dimensions in Visual Basic</span></span>
<span data-ttu-id="f7362-103">Oggetto *dimensione* indica una direzione in cui è possibile variare la specifica di elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f7362-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="f7362-104">Matrice contenente le vendite totali per ogni giorno del mese ha una dimensione (giorno del mese).</span><span class="sxs-lookup"><span data-stu-id="f7362-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="f7362-105">Matrice contenente le vendite totali per reparto per ogni giorno del mese ha due dimensioni (il numero di reparto e il giorno del mese).</span><span class="sxs-lookup"><span data-stu-id="f7362-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="f7362-106">Il numero di dimensioni è una matrice viene chiamato il relativo *rank*.</span><span class="sxs-lookup"><span data-stu-id="f7362-106">The number of dimensions an array has is called its *rank*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7362-107">È possibile utilizzare il <xref:System.Array.Rank%2A> proprietà per determinare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="f7362-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>  
  
## <a name="working-with-dimensions"></a><span data-ttu-id="f7362-108">Utilizzo delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="f7362-108">Working with Dimensions</span></span>  
 <span data-ttu-id="f7362-109">È possibile specificare un elemento di una matrice fornendo un *indice* o *pedice* per ciascuna delle relative dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f7362-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="f7362-110">Gli elementi sono contigui lungo ciascuna dimensione dall'indice 0 dell'indice più alto per tale dimensione.</span><span class="sxs-lookup"><span data-stu-id="f7362-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>  
  
 <span data-ttu-id="f7362-111">Le illustrazioni seguenti mostrano la struttura concettuale di matrici con intervalli diversi.</span><span class="sxs-lookup"><span data-stu-id="f7362-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="f7362-112">Ogni elemento illustrato nelle figure vengono illustrati i valori di indice di diritti di accesso.</span><span class="sxs-lookup"><span data-stu-id="f7362-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="f7362-113">Ad esempio, si può accedere al primo elemento della seconda riga della matrice bidimensionale specificando gli indici `(1, 0)`.</span><span class="sxs-lookup"><span data-stu-id="f7362-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>  
  
 <span data-ttu-id="f7362-114">![Diagramma grafico di una finestra di &#45; matrice dimensionale](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span><span class="sxs-lookup"><span data-stu-id="f7362-114">![Graphic diagram of one&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span></span>  
<span data-ttu-id="f7362-115">Matrice unidimensionale</span><span class="sxs-lookup"><span data-stu-id="f7362-115">One-dimensional array</span></span>  
  
 <span data-ttu-id="f7362-116">![Diagramma grafico di due &#45; matrice dimensionale](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span><span class="sxs-lookup"><span data-stu-id="f7362-116">![Graphic diagram of two&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span></span>  
<span data-ttu-id="f7362-117">matrice bidimensionale</span><span class="sxs-lookup"><span data-stu-id="f7362-117">Two-dimensional array</span></span>  
  
 <span data-ttu-id="f7362-118">![Diagramma grafico di tre &#45; matrice dimensionale](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span><span class="sxs-lookup"><span data-stu-id="f7362-118">![Graphic diagram of three&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span></span>  
<span data-ttu-id="f7362-119">Matrice tridimensionale</span><span class="sxs-lookup"><span data-stu-id="f7362-119">Three-dimensional array</span></span>  
  
### <a name="one-dimension"></a><span data-ttu-id="f7362-120">Una dimensione</span><span class="sxs-lookup"><span data-stu-id="f7362-120">One Dimension</span></span>  
 <span data-ttu-id="f7362-121">Molte matrici hanno una sola dimensione, ad esempio il numero di persone di ciascuna età.</span><span class="sxs-lookup"><span data-stu-id="f7362-121">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="f7362-122">L'unico requisito per specificare un elemento è la durata per cui tale elemento contiene il conteggio.</span><span class="sxs-lookup"><span data-stu-id="f7362-122">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="f7362-123">Tale matrice utilizza pertanto un solo indice.</span><span class="sxs-lookup"><span data-stu-id="f7362-123">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="f7362-124">Nell'esempio seguente viene dichiarata una variabile per contenere un *unidimensionale* di età i conteggi per età compresi tra 0 e 120.</span><span class="sxs-lookup"><span data-stu-id="f7362-124">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a><span data-ttu-id="f7362-125">Due dimensioni</span><span class="sxs-lookup"><span data-stu-id="f7362-125">Two Dimensions</span></span>  
 <span data-ttu-id="f7362-126">Alcune matrici hanno due dimensioni, ad esempio il numero di uffici in ogni piano di ogni compilazione in una struttura.</span><span class="sxs-lookup"><span data-stu-id="f7362-126">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="f7362-127">La specifica di un elemento richiede che il numero di compilazione e la base e ogni elemento contiene il numero per la combinazione di edificio e piano.</span><span class="sxs-lookup"><span data-stu-id="f7362-127">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="f7362-128">Di conseguenza, tale matrice usa due indici.</span><span class="sxs-lookup"><span data-stu-id="f7362-128">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="f7362-129">Nell'esempio seguente viene dichiarata una variabile per contenere un *matrice bidimensionale* dei conteggi di office, per edifici 0 e 40 e piani compresi tra 0 e 5.</span><span class="sxs-lookup"><span data-stu-id="f7362-129">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 <span data-ttu-id="f7362-130">Una matrice bidimensionale viene inoltre chiamata un *matrice rettangolare*.</span><span class="sxs-lookup"><span data-stu-id="f7362-130">A two-dimensional array is also called a *rectangular array*.</span></span>  
  
### <a name="three-dimensions"></a><span data-ttu-id="f7362-131">Tre dimensioni</span><span class="sxs-lookup"><span data-stu-id="f7362-131">Three Dimensions</span></span>  
 <span data-ttu-id="f7362-132">Alcune matrici hanno tre dimensioni, ad esempio i valori in uno spazio tridimensionale.</span><span class="sxs-lookup"><span data-stu-id="f7362-132">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="f7362-133">Tale matrice utilizza tre indici, che in questo caso rappresentano le coordinate z di spazio fisico, x e y.</span><span class="sxs-lookup"><span data-stu-id="f7362-133">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="f7362-134">Nell'esempio seguente viene dichiarata una variabile per contenere un *matrice tridimensionale* delle temperature aria in vari punti in un volume tridimensionale.</span><span class="sxs-lookup"><span data-stu-id="f7362-134">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a><span data-ttu-id="f7362-135">Più di tre dimensioni</span><span class="sxs-lookup"><span data-stu-id="f7362-135">More than Three Dimensions</span></span>  
 <span data-ttu-id="f7362-136">Anche se una matrice può avere un massimo di 32 dimensioni, è raro che ne abbia più di tre.</span><span class="sxs-lookup"><span data-stu-id="f7362-136">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7362-137">Quando si aggiungono dimensioni a una matrice, l'archiviazione totale necessaria per la matrice aumenta notevolmente, pertanto si consiglia di utilizzare le matrici multidimensionali con cautela.</span><span class="sxs-lookup"><span data-stu-id="f7362-137">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>  
  
## <a name="using-different-dimensions"></a><span data-ttu-id="f7362-138">Utilizzo di dimensioni diverse</span><span class="sxs-lookup"><span data-stu-id="f7362-138">Using Different Dimensions</span></span>  
 <span data-ttu-id="f7362-139">Si supponga che si desidera rilevare gli importi delle vendite per ogni giorno del mese corrente.</span><span class="sxs-lookup"><span data-stu-id="f7362-139">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="f7362-140">È possibile dichiarare una matrice unidimensionale con 31 elementi, uno per ogni giorno del mese, come nell'esempio seguente viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="f7362-140">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 <span data-ttu-id="f7362-141">Ora si supponga che si desidera rilevare le stesse informazioni non solo per ogni giorno del mese, ma anche per ogni mese dell'anno.</span><span class="sxs-lookup"><span data-stu-id="f7362-141">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="f7362-142">È possibile dichiarare una matrice bidimensionale con 12 righe (per i mesi) e 31 colonne (per i giorni), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f7362-142">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 <span data-ttu-id="f7362-143">Ora si supponga che si sceglie la matrice contengono informazioni per più di un anno.</span><span class="sxs-lookup"><span data-stu-id="f7362-143">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="f7362-144">Se si desidera rilevare gli importi delle vendite per 5 anni, è possibile dichiarare una matrice tridimensionale con 5 livelli, 12 righe e 31 colonne, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f7362-144">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 <span data-ttu-id="f7362-145">Si noti che, poiché ogni indice varia da 0 al valore massimo, ogni dimensione di `salesAmounts` è dichiarato come una minore della lunghezza necessari per la dimensione.</span><span class="sxs-lookup"><span data-stu-id="f7362-145">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="f7362-146">Si noti inoltre che le dimensioni della matrice aumentano con ogni nuova dimensione.</span><span class="sxs-lookup"><span data-stu-id="f7362-146">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="f7362-147">Le tre dimensioni negli esempi precedenti sono 31, 372 e 1860 elementi.</span><span class="sxs-lookup"><span data-stu-id="f7362-147">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7362-148">È possibile creare una matrice senza utilizzare il `Dim` istruzione o `New` clausola.</span><span class="sxs-lookup"><span data-stu-id="f7362-148">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="f7362-149">Ad esempio, è possibile chiamare il <xref:System.Array.CreateInstance%2A> metodo o un altro componente può passare al codice una matrice creata in questo modo.</span><span class="sxs-lookup"><span data-stu-id="f7362-149">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="f7362-150">Tale matrice può avere un limite inferiore diverso da 0.</span><span class="sxs-lookup"><span data-stu-id="f7362-150">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="f7362-151">È sempre possibile verificare il limite inferiore di una dimensione utilizzando il <xref:System.Array.GetLowerBound%2A> metodo o `LBound` (funzione).</span><span class="sxs-lookup"><span data-stu-id="f7362-151">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7362-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7362-152">See Also</span></span>  
 [<span data-ttu-id="f7362-153">Array</span><span class="sxs-lookup"><span data-stu-id="f7362-153">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="f7362-154">Risoluzione dei problemi relativi alle matrici</span><span class="sxs-lookup"><span data-stu-id="f7362-154">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)

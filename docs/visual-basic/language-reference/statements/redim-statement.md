---
title: Istruzione ReDim
ms.date: 07/20/2015
f1_keywords:
- vb.ReDim
- vb.Preserve
helpviewer_keywords:
- fixed-length strings [Visual Basic], declaring
- ReDim statement [Visual Basic], syntax
- dynamic arrays [Visual Basic], ReDim statement
- arrays [Visual Basic], reallocating
- arrays [Visual Basic], reinitializing
- arrays [Visual Basic], dimensions
- scalars, and arrays
- scalars
- declarations [Visual Basic], dynamic arrays
- variables [Visual Basic], scalar
- ReDim statement [Visual Basic]
- data types [Visual Basic], assigning
- As keyword [Visual Basic], in ReDim statement
- To keyword [Visual Basic], ReDim statement
- arrays [Visual Basic], declaring
- Preserve keyword [Visual Basic], ReDim statement
- storage [Visual Basic], allocating
- arrays [Visual Basic], and scalars
- declaration statements [Visual Basic]
- scalar variables [Visual Basic]
ms.assetid: ad1c5e07-dcd7-4ae1-a79e-ad3f2dcc2083
ms.openlocfilehash: 82f19762865fdf3c3f32a0349e21e3b97bebd567
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404278"
---
# <a name="redim-statement-visual-basic"></a><span data-ttu-id="30c81-102">Istruzione ReDim (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30c81-102">ReDim Statement (Visual Basic)</span></span>
<span data-ttu-id="30c81-103">Rialloca lo spazio di archiviazione per una variabile di matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-103">Reallocates storage space for an array variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30c81-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30c81-104">Syntax</span></span>  
  
```vb  
ReDim [ Preserve ] name(boundlist) [ ,  name(boundlist) [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="30c81-105">Parti</span><span class="sxs-lookup"><span data-stu-id="30c81-105">Parts</span></span>  
  
|<span data-ttu-id="30c81-106">Termine</span><span class="sxs-lookup"><span data-stu-id="30c81-106">Term</span></span>|<span data-ttu-id="30c81-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="30c81-107">Definition</span></span>|  
|----------|----------------|  
|`Preserve`|<span data-ttu-id="30c81-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="30c81-108">Optional.</span></span> <span data-ttu-id="30c81-109">Modificatore utilizzato per conservare i dati nella matrice esistente quando si modifica soltanto la grandezza dell'ultima dimensione.</span><span class="sxs-lookup"><span data-stu-id="30c81-109">Modifier used to preserve the data in the existing array when you change the size of only the last dimension.</span></span>|  
|`name`|<span data-ttu-id="30c81-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="30c81-110">Required.</span></span> <span data-ttu-id="30c81-111">Nome della variabile di matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-111">Name of the array variable.</span></span> <span data-ttu-id="30c81-112">Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="30c81-112">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`boundlist`|<span data-ttu-id="30c81-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="30c81-113">Required.</span></span> <span data-ttu-id="30c81-114">Elenco di limiti relativi a ogni dimensione della matrice ridefinita.</span><span class="sxs-lookup"><span data-stu-id="30c81-114">List of bounds of each dimension of the redefined array.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30c81-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="30c81-115">Remarks</span></span>  
 <span data-ttu-id="30c81-116">È possibile utilizzare l'istruzione `ReDim` per modificare una o più dimensioni di una matrice che è stata già dichiarata.</span><span class="sxs-lookup"><span data-stu-id="30c81-116">You can use the `ReDim` statement to change the size of one or more dimensions of an array that has already been declared.</span></span> <span data-ttu-id="30c81-117">Se si dispone di una matrice di grandi dimensioni e alcuni degli elementi di questa non sono più necessari, `ReDim` consente di liberare memoria riducendo le dimensioni della matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-117">If you have a large array and you no longer need some of its elements, `ReDim` can free up memory by reducing the array size.</span></span> <span data-ttu-id="30c81-118">D’altra parte, se la matrice necessita di più elementi, `ReDim` è in grado di aggiungerli.</span><span class="sxs-lookup"><span data-stu-id="30c81-118">On the other hand, if your array needs more elements, `ReDim` can add them.</span></span>  
  
 <span data-ttu-id="30c81-119">L'istruzione `ReDim` è destinata solo alle matrici.</span><span class="sxs-lookup"><span data-stu-id="30c81-119">The `ReDim` statement is intended only for arrays.</span></span> <span data-ttu-id="30c81-120">Non è valida per valori scalari (variabili che contengono un unico valore), raccolte o strutture.</span><span class="sxs-lookup"><span data-stu-id="30c81-120">It's not valid on scalars (variables that contain only a single value), collections, or structures.</span></span> <span data-ttu-id="30c81-121">Tenere presente che se l'utente dichiara che una variabile è di tipo `Array`, l'istruzione `ReDim` non dispone di sufficienti informazioni sulla tipologia e non può creare la nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-121">Note that if you declare a variable to be of type `Array`, the `ReDim` statement doesn't have sufficient type information to create the new array.</span></span>  
  
 <span data-ttu-id="30c81-122">Si può usare `ReDim` solo a livello di routine.</span><span class="sxs-lookup"><span data-stu-id="30c81-122">You can use `ReDim` only at procedure level.</span></span> <span data-ttu-id="30c81-123">Pertanto, il contesto della dichiarazione relativo alla variabile deve essere una routine. Di conseguenza, non può essere un file di origine, uno spazio dei nomi, un'interfaccia, una classe, una struttura, un modulo o un blocco.</span><span class="sxs-lookup"><span data-stu-id="30c81-123">Therefore, the declaration context for the variable must be a procedure; it can't be a source file, a namespace, an interface, a class, a structure, a module, or a block.</span></span> <span data-ttu-id="30c81-124">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="30c81-124">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="30c81-125">Regole</span><span class="sxs-lookup"><span data-stu-id="30c81-125">Rules</span></span>  
  
- <span data-ttu-id="30c81-126">**Variabili multiple.**</span><span class="sxs-lookup"><span data-stu-id="30c81-126">**Multiple Variables.**</span></span> <span data-ttu-id="30c81-127">È possibile ridimensionare diverse variabili di matrice nella stessa istruzione di dichiarazione e specificare le `name` `boundlist` parti e per ogni variabile.</span><span class="sxs-lookup"><span data-stu-id="30c81-127">You can resize several array variables in the same declaration statement and specify the `name` and `boundlist` parts for each variable.</span></span> <span data-ttu-id="30c81-128">Nel caso di più variabili, è possibile separarle mediante virgole.</span><span class="sxs-lookup"><span data-stu-id="30c81-128">Multiple variables are separated by commas.</span></span>  
  
- <span data-ttu-id="30c81-129">**Limiti della matrice.**</span><span class="sxs-lookup"><span data-stu-id="30c81-129">**Array Bounds.**</span></span> <span data-ttu-id="30c81-130">Ogni voce in `boundlist` può specificare i limiti inferiore e superiore della dimensione.</span><span class="sxs-lookup"><span data-stu-id="30c81-130">Each entry in `boundlist` can specify the lower and upper bounds of that dimension.</span></span> <span data-ttu-id="30c81-131">Il limite inferiore è sempre pari a 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="30c81-131">The lower bound is always 0 (zero).</span></span> <span data-ttu-id="30c81-132">Il limite superiore rappresenta il valore di indice più alto possibile per la dimensione, non la lunghezza della dimensione (vale a dire, il limite superiore più uno).</span><span class="sxs-lookup"><span data-stu-id="30c81-132">The upper bound is the highest possible index value for that dimension, not the length of the dimension (which is the upper bound plus one).</span></span> <span data-ttu-id="30c81-133">L'indice di ogni dimensione può variare tra 0 e il relativo valore di limite superiore.</span><span class="sxs-lookup"><span data-stu-id="30c81-133">The index for each dimension can vary from 0 through its upper bound value.</span></span>  
  
     <span data-ttu-id="30c81-134">Il numero di dimensioni in `boundlist` deve corrispondere al numero originale di dimensioni (livello) della matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-134">The number of dimensions in `boundlist` must match the original number of dimensions (rank) of the array.</span></span>  
  
- <span data-ttu-id="30c81-135">**Tipi di dati.**</span><span class="sxs-lookup"><span data-stu-id="30c81-135">**Data Types.**</span></span> <span data-ttu-id="30c81-136">L' `ReDim` istruzione non può modificare il tipo di dati di una variabile di matrice o dei relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="30c81-136">The `ReDim` statement cannot change the data type of an array variable or its elements.</span></span>  
  
- <span data-ttu-id="30c81-137">**Inizializzazione.**</span><span class="sxs-lookup"><span data-stu-id="30c81-137">**Initialization.**</span></span> <span data-ttu-id="30c81-138">L' `ReDim` istruzione non può fornire nuovi valori di inizializzazione per gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-138">The `ReDim` statement cannot provide new initialization values for the array elements.</span></span>  
  
- <span data-ttu-id="30c81-139">**Rank.**</span><span class="sxs-lookup"><span data-stu-id="30c81-139">**Rank.**</span></span> <span data-ttu-id="30c81-140">L' `ReDim` istruzione non può modificare il rango (numero di dimensioni) della matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-140">The `ReDim` statement cannot change the rank (the number of dimensions) of the array.</span></span>  
  
- <span data-ttu-id="30c81-141">**Ridimensionamento con Preserve.**</span><span class="sxs-lookup"><span data-stu-id="30c81-141">**Resizing with Preserve.**</span></span> <span data-ttu-id="30c81-142">Se si utilizza `Preserve` , è possibile ridimensionare solo l'ultima dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-142">If you use `Preserve`, you can resize only the last dimension of the array.</span></span> <span data-ttu-id="30c81-143">Per ogni dimensione, è necessario specificare il limite della matrice esistente.</span><span class="sxs-lookup"><span data-stu-id="30c81-143">For every other dimension, you must specify the bound of the existing array.</span></span>  
  
     <span data-ttu-id="30c81-144">Ad esempio, se la matrice contiene solo una dimensione, è possibile ridimensionarla e mantenere tutto il contenuto della matrice, poiché si sta modificando l'ultima e unica dimensione.</span><span class="sxs-lookup"><span data-stu-id="30c81-144">For example, if your array has only one dimension, you can resize that dimension and still preserve all the contents of the array, because you are changing the last and only dimension.</span></span> <span data-ttu-id="30c81-145">Tuttavia, se la matrice dispone di due o più dimensioni e si utilizza `Preserve`, è possibile modificare i valori soltanto per l'ultima dimensione.</span><span class="sxs-lookup"><span data-stu-id="30c81-145">However, if your array has two or more dimensions, you can change the size of only the last dimension if you use `Preserve`.</span></span>  
  
- <span data-ttu-id="30c81-146">**Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="30c81-146">**Properties.**</span></span> <span data-ttu-id="30c81-147">È possibile utilizzare `ReDim` su una proprietà che include una matrice di valori.</span><span class="sxs-lookup"><span data-stu-id="30c81-147">You can use `ReDim` on a property that holds an array of values.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="30c81-148">Comportamento</span><span class="sxs-lookup"><span data-stu-id="30c81-148">Behavior</span></span>  
  
- <span data-ttu-id="30c81-149">**Sostituzione di matrici.**</span><span class="sxs-lookup"><span data-stu-id="30c81-149">**Array Replacement.**</span></span> <span data-ttu-id="30c81-150">`ReDim`rilascia la matrice esistente e crea una nuova matrice con lo stesso rango.</span><span class="sxs-lookup"><span data-stu-id="30c81-150">`ReDim` releases the existing array and creates a new array with the same rank.</span></span> <span data-ttu-id="30c81-151">La nuova matrice sostituisce quella rilasciata nella variabile di matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-151">The new array replaces the released array in the array variable.</span></span>  
  
- <span data-ttu-id="30c81-152">**Inizializzazione senza Preserve.**</span><span class="sxs-lookup"><span data-stu-id="30c81-152">**Initialization without Preserve.**</span></span> <span data-ttu-id="30c81-153">Se non si specifica `Preserve` , `ReDim` Inizializza gli elementi della nuova matrice usando il valore predefinito per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="30c81-153">If you do not specify `Preserve`, `ReDim` initializes the elements of the new array by using the default value for their data type.</span></span>  
  
- <span data-ttu-id="30c81-154">**Inizializzazione con Preserve.**</span><span class="sxs-lookup"><span data-stu-id="30c81-154">**Initialization with Preserve.**</span></span> <span data-ttu-id="30c81-155">Se si specifica `Preserve` , Visual Basic copia gli elementi dalla matrice esistente alla nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-155">If you specify `Preserve`, Visual Basic copies the elements from the existing array to the new array.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30c81-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="30c81-156">Example</span></span>  
 <span data-ttu-id="30c81-157">Nell'esempio seguente viene aumentata la grandezza dell'ultima dimensione di una matrice dinamica senza perdere i dati presenti nella matrice; in seguito, viene ridotta la dimensione con perdita di dati parziali.</span><span class="sxs-lookup"><span data-stu-id="30c81-157">The following example increases the size of the last dimension of a dynamic array without losing any existing data in the array, and then decreases the size with partial data loss.</span></span> <span data-ttu-id="30c81-158">Infine, viene ridotta la dimensione del relativo valore originale e vengono inizializzati di nuovo tutti gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-158">Finally, it decreases the size back to its original value and reinitializes all the array elements.</span></span>  
  
 [!code-vb[VbVbalrStatements#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#52)]  
  
 <span data-ttu-id="30c81-159">L'istruzione `Dim` crea una nuova matrice con tre dimensioni.</span><span class="sxs-lookup"><span data-stu-id="30c81-159">The `Dim` statement creates a new array with three dimensions.</span></span> <span data-ttu-id="30c81-160">Ogni dimensione viene dichiarata con un limite pari a 10. In questo modo l'indice della matrice per ogni dimensione può essere compreso tra 0 e 10.</span><span class="sxs-lookup"><span data-stu-id="30c81-160">Each dimension is declared with a bound of 10, so the array index for each dimension can range from 0 through 10.</span></span> <span data-ttu-id="30c81-161">Nella seguente discussione, si fa riferimento alle tre dimensioni come livello, riga e colonna.</span><span class="sxs-lookup"><span data-stu-id="30c81-161">In the following discussion, the three dimensions are referred to as layer, row, and column.</span></span>  
  
 <span data-ttu-id="30c81-162">La prima `ReDim` crea una nuova matrice che sostituisce quella esistente nella `intArray` di variabile.</span><span class="sxs-lookup"><span data-stu-id="30c81-162">The first `ReDim` creates a new array which replaces the existing array in variable `intArray`.</span></span> <span data-ttu-id="30c81-163">`ReDim` copia tutti gli elementi dalla matrice esistente in quella nuova.</span><span class="sxs-lookup"><span data-stu-id="30c81-163">`ReDim` copies all the elements from the existing array into the new array.</span></span> <span data-ttu-id="30c81-164">Inoltre, consente di aggiungere altre 10 colonne alla fine di ogni riga di tutti i livelli e consente di inizializzare gli elementi in queste nuove colonne su 0 (valore predefinito) di `Integer`, ovvero il tipo di elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-164">It also adds 10 more columns to the end of every row in every layer and initializes the elements in these new columns to 0 (the default value of `Integer`, which is the element type of the array).</span></span>  
  
 <span data-ttu-id="30c81-165">La seconda `ReDim` crea una nuova matrice e copia tutti gli elementi adeguati.</span><span class="sxs-lookup"><span data-stu-id="30c81-165">The second `ReDim` creates another new array and copies all the elements that fit.</span></span> <span data-ttu-id="30c81-166">Tuttavia, cinque colonne vengono perse alla fine di ogni riga relativa a ogni livello.</span><span class="sxs-lookup"><span data-stu-id="30c81-166">However, five columns are lost from the end of every row in every layer.</span></span> <span data-ttu-id="30c81-167">Ciò non rappresenta un problema se l'utente non ha più la necessità di utilizzare tali colonne.</span><span class="sxs-lookup"><span data-stu-id="30c81-167">This is not a problem if you have finished using these columns.</span></span> <span data-ttu-id="30c81-168">La riduzione delle dimensioni di una grande matrice può liberare memoria che non è più necessaria.</span><span class="sxs-lookup"><span data-stu-id="30c81-168">Reducing the size of a large array can free up memory that you no longer need.</span></span>  
  
 <span data-ttu-id="30c81-169">La terza `ReDim` crea una nuova matrice e rimuove altre cinque colonne dalla fine di ogni riga relativa a ogni livello.</span><span class="sxs-lookup"><span data-stu-id="30c81-169">The third `ReDim` creates another new array and removes another five columns from the end of every row in every layer.</span></span> <span data-ttu-id="30c81-170">Questa volta non copia gli elementi esistenti.</span><span class="sxs-lookup"><span data-stu-id="30c81-170">This time it does not copy any existing elements.</span></span> <span data-ttu-id="30c81-171">Questa istruzione consente di ripristinare le dimensioni originali della matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-171">This statement reverts the array to its original size.</span></span> <span data-ttu-id="30c81-172">Dal momento che l'istruzione non include il modificatore `Preserve`, imposta i valori predefiniti originali di tutti gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="30c81-172">Because the statement doesn't include the `Preserve` modifier, it sets all array elements to their original default values.</span></span>  
  
 <span data-ttu-id="30c81-173">Per altri esempi, vedere [matrici](../../programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="30c81-173">For additional examples, see [Arrays](../../programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c81-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30c81-174">See also</span></span>

- <xref:System.IndexOutOfRangeException>
- [<span data-ttu-id="30c81-175">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="30c81-175">Const Statement</span></span>](const-statement.md)
- [<span data-ttu-id="30c81-176">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="30c81-176">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="30c81-177">Istruzione Erase</span><span class="sxs-lookup"><span data-stu-id="30c81-177">Erase Statement</span></span>](erase-statement.md)
- [<span data-ttu-id="30c81-178">Nothing</span><span class="sxs-lookup"><span data-stu-id="30c81-178">Nothing</span></span>](../nothing.md)
- [<span data-ttu-id="30c81-179">Matrici</span><span class="sxs-lookup"><span data-stu-id="30c81-179">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)

---
title: "Procedura: assegnare una matrice a un'altra matrice"
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: c38def1ba9f3720bc760d6f6e4264510c884c930
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413079"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="05b0a-102">Procedura: assegnare una matrice a un'altra matrice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05b0a-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>

<span data-ttu-id="05b0a-103">Poiché le matrici sono oggetti, è possibile usarle nelle istruzioni di assegnazione come altri tipi di oggetto.</span><span class="sxs-lookup"><span data-stu-id="05b0a-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="05b0a-104">Una variabile di matrice include un puntatore ai dati che costituiscono gli elementi della matrice e le informazioni di rango e lunghezza e un'assegnazione copia solo questo puntatore.</span><span class="sxs-lookup"><span data-stu-id="05b0a-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>

### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="05b0a-105">Per assegnare una matrice a un'altra matrice</span><span class="sxs-lookup"><span data-stu-id="05b0a-105">To assign one array to another array</span></span>

1. <span data-ttu-id="05b0a-106">Verificare che le due matrici abbiano lo stesso rango (numero di dimensioni) e tipi di dati degli elementi compatibili.</span><span class="sxs-lookup"><span data-stu-id="05b0a-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>

2. <span data-ttu-id="05b0a-107">Utilizzare un'istruzione di assegnazione standard per assegnare la matrice di origine alla matrice di destinazione.</span><span class="sxs-lookup"><span data-stu-id="05b0a-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="05b0a-108">Non seguire neanche il nome della matrice con le parentesi.</span><span class="sxs-lookup"><span data-stu-id="05b0a-108">Do not follow either array name with parentheses.</span></span>

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

<span data-ttu-id="05b0a-109">Quando si assegna una matrice a un'altra, si applicano le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="05b0a-109">When you assign one array to another, the following rules apply:</span></span>

- <span data-ttu-id="05b0a-110">**Corrispondenze di rango.**</span><span class="sxs-lookup"><span data-stu-id="05b0a-110">**Equal Ranks.**</span></span> <span data-ttu-id="05b0a-111">Il rango (numero di dimensioni) della matrice di destinazione deve essere uguale a quello della matrice di origine.</span><span class="sxs-lookup"><span data-stu-id="05b0a-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>

  <span data-ttu-id="05b0a-112">Se le classificazioni delle due matrici sono uguali, le dimensioni non devono essere uguali.</span><span class="sxs-lookup"><span data-stu-id="05b0a-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="05b0a-113">Il numero di elementi in una determinata dimensione può essere modificato durante l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="05b0a-113">The number of elements in a given dimension can change during assignment.</span></span>

- <span data-ttu-id="05b0a-114">**Tipi di elemento.**</span><span class="sxs-lookup"><span data-stu-id="05b0a-114">**Element Types.**</span></span> <span data-ttu-id="05b0a-115">Entrambe le matrici devono avere elementi di *tipo riferimento* o entrambe le matrici devono avere elementi di *tipo valore* .</span><span class="sxs-lookup"><span data-stu-id="05b0a-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="05b0a-116">Per altre informazioni, vedere [Value Types and Reference Types](../data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="05b0a-116">For more information, see [Value Types and Reference Types](../data-types/value-types-and-reference-types.md).</span></span>

  - <span data-ttu-id="05b0a-117">Se entrambe le matrici hanno elementi di tipo valore, i tipi di dati degli elementi devono essere esattamente gli stessi.</span><span class="sxs-lookup"><span data-stu-id="05b0a-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="05b0a-118">L'unica eccezione è che è possibile assegnare una matrice di `Enum` elementi a una matrice del tipo di base `Enum` .</span><span class="sxs-lookup"><span data-stu-id="05b0a-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>

  - <span data-ttu-id="05b0a-119">Se entrambe le matrici hanno elementi di tipo riferimento, il tipo di elemento di origine deve derivare dal tipo di elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="05b0a-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="05b0a-120">In tal caso, le due matrici hanno la stessa relazione di ereditarietà dei relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="05b0a-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="05b0a-121">Questa operazione è denominata *covarianza di matrici*.</span><span class="sxs-lookup"><span data-stu-id="05b0a-121">This is called *array covariance*.</span></span>

<span data-ttu-id="05b0a-122">Il compilatore segnala un errore se le regole precedenti vengono violate, ad esempio se i tipi di dati non sono compatibili o se le classificazioni sono diverse.</span><span class="sxs-lookup"><span data-stu-id="05b0a-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="05b0a-123">È possibile aggiungere la gestione degli errori al codice per assicurarsi che le matrici siano compatibili prima di tentare un'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="05b0a-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="05b0a-124">È anche possibile usare la parola chiave dell' [operatore TryCast](../../../language-reference/operators/trycast-operator.md) se si vuole evitare la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="05b0a-124">You can also use the [TryCast Operator](../../../language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="05b0a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05b0a-125">See also</span></span>

- [<span data-ttu-id="05b0a-126">Matrici</span><span class="sxs-lookup"><span data-stu-id="05b0a-126">Arrays</span></span>](index.md)
- [<span data-ttu-id="05b0a-127">Risoluzione dei problemi relativi alle matrici</span><span class="sxs-lookup"><span data-stu-id="05b0a-127">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="05b0a-128">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="05b0a-128">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
- [<span data-ttu-id="05b0a-129">Conversioni di matrice</span><span class="sxs-lookup"><span data-stu-id="05b0a-129">Array Conversions</span></span>](../data-types/array-conversions.md)

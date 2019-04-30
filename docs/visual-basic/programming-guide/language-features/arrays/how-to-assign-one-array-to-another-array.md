---
title: "Procedura: Assegnare una matrice a un'altra matrice (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: 78497de3a9aea55320639c55a151a1260a960159
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053678"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="9df41-102">Procedura: Assegnare una matrice a un'altra matrice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9df41-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>

<span data-ttu-id="9df41-103">Poiché le matrici sono gli oggetti, è possibile usarli nelle istruzioni di assegnazione, come altri tipi di oggetto.</span><span class="sxs-lookup"><span data-stu-id="9df41-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="9df41-104">Una variabile di matrice contiene un puntatore ai dati che costituiscono gli elementi della matrice e le informazioni di classificazione e la lunghezza e un'assegnazione di copia solo questo puntatore.</span><span class="sxs-lookup"><span data-stu-id="9df41-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>

### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="9df41-105">Per assegnare una matrice a un'altra matrice</span><span class="sxs-lookup"><span data-stu-id="9df41-105">To assign one array to another array</span></span>

1. <span data-ttu-id="9df41-106">Assicurarsi che le due matrici hanno la stessa classificazione (numero di dimensioni) e tipi di dati compatibile.</span><span class="sxs-lookup"><span data-stu-id="9df41-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>

2. <span data-ttu-id="9df41-107">Utilizzare un'istruzione di assegnazione standard per assegnare l'array di origine nella matrice di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9df41-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="9df41-108">Non seguire i nomi delle matrici tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="9df41-108">Do not follow either array name with parentheses.</span></span>

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

<span data-ttu-id="9df41-109">Quando si assegna una matrice a un altro, si applicano le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="9df41-109">When you assign one array to another, the following rules apply:</span></span>

- <span data-ttu-id="9df41-110">**Numeri di dimensioni uguali.**</span><span class="sxs-lookup"><span data-stu-id="9df41-110">**Equal Ranks.**</span></span> <span data-ttu-id="9df41-111">La classificazione (numero di dimensioni) della matrice di destinazione deve essere uguale a quello della matrice di origine.</span><span class="sxs-lookup"><span data-stu-id="9df41-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>

  <span data-ttu-id="9df41-112">Le classificazioni delle due matrici sono uguali, le dimensioni non sono necessario essere uguali.</span><span class="sxs-lookup"><span data-stu-id="9df41-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="9df41-113">Il numero di elementi in una determinata dimensione può cambiare durante l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="9df41-113">The number of elements in a given dimension can change during assignment.</span></span>

- <span data-ttu-id="9df41-114">**Tipi di elemento.**</span><span class="sxs-lookup"><span data-stu-id="9df41-114">**Element Types.**</span></span> <span data-ttu-id="9df41-115">Devono disporre di entrambe le matrici *tipo di riferimento* devono avere entrambe le matrici o gli elementi *tipo di valore* elementi.</span><span class="sxs-lookup"><span data-stu-id="9df41-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="9df41-116">Per altre informazioni, vedere [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="9df41-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>

  - <span data-ttu-id="9df41-117">Se entrambe le matrici sono elementi di tipo valore, i tipi di dati elemento devono essere esattamente lo stesso.</span><span class="sxs-lookup"><span data-stu-id="9df41-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="9df41-118">L'unica eccezione è che è possibile assegnare una matrice di `Enum` elementi in una matrice del tipo di base di tale `Enum`.</span><span class="sxs-lookup"><span data-stu-id="9df41-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>

  - <span data-ttu-id="9df41-119">Se entrambe le matrici hanno riferimenti a elementi di tipo, il tipo di elemento di origine deve derivare dal tipo di elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9df41-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="9df41-120">In questo caso, le due matrici hanno la stessa relazione di ereditarietà dei rispettivi elementi.</span><span class="sxs-lookup"><span data-stu-id="9df41-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="9df41-121">Questa operazione viene definita *covarianza di matrici*.</span><span class="sxs-lookup"><span data-stu-id="9df41-121">This is called *array covariance*.</span></span>

<span data-ttu-id="9df41-122">Il compilatore segnala un errore se le regole precedenti vengono violate, ad esempio se i tipi di dati non sono compatibili o le classificazioni non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="9df41-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="9df41-123">È possibile aggiungere al codice per assicurarsi che le matrici sono compatibili prima di tentare un'assegnazione di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="9df41-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="9df41-124">È anche possibile usare la [operatore TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md) parola chiave se si desidera evitare di generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9df41-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="9df41-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9df41-125">See also</span></span>

- [<span data-ttu-id="9df41-126">Matrici</span><span class="sxs-lookup"><span data-stu-id="9df41-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="9df41-127">Risoluzione dei problemi relativi alle matrici</span><span class="sxs-lookup"><span data-stu-id="9df41-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="9df41-128">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="9df41-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="9df41-129">Conversioni di matrice</span><span class="sxs-lookup"><span data-stu-id="9df41-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)

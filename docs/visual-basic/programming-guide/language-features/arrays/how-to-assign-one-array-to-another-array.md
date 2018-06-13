---
title: "Procedura: assegnare una matrice a un'altra matrice (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: 63c7d187152fcb5ea84378c677aa687f334f63de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647930"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="a3da4-102">Procedura: assegnare una matrice a un'altra matrice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3da4-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>
<span data-ttu-id="a3da4-103">Poiché le matrici sono oggetti, è possibile utilizzare le istruzioni di assegnazione, come altri tipi di oggetto.</span><span class="sxs-lookup"><span data-stu-id="a3da4-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="a3da4-104">Una variabile di matrice contiene un puntatore ai dati che costituiscono gli elementi della matrice e le informazioni di classificazione e la lunghezza e un'assegnazione di copia solo l'indicatore di misura.</span><span class="sxs-lookup"><span data-stu-id="a3da4-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>  
  
### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="a3da4-105">Per assegnare una matrice a un'altra matrice</span><span class="sxs-lookup"><span data-stu-id="a3da4-105">To assign one array to another array</span></span>  
  
1.  <span data-ttu-id="a3da4-106">Verificare che le due matrici abbiano la stessa classificazione (numero di dimensioni) e i tipi di dati compatibile.</span><span class="sxs-lookup"><span data-stu-id="a3da4-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>  
  
2.  <span data-ttu-id="a3da4-107">Utilizzare un'istruzione di assegnazione standard per assegnare l'array di origine alla matrice di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a3da4-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="a3da4-108">Non seguono il nome di una matrice con parentesi.</span><span class="sxs-lookup"><span data-stu-id="a3da4-108">Do not follow either array name with parentheses.</span></span>  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 <span data-ttu-id="a3da4-109">Quando si assegna una matrice a un altro, si applicano le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3da4-109">When you assign one array to another, the following rules apply:</span></span>  
  
-   <span data-ttu-id="a3da4-110">**Numeri di dimensioni uguali.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-110">**Equal Ranks.**</span></span> <span data-ttu-id="a3da4-111">La classificazione (numero di dimensioni) della matrice di destinazione deve essere uguale a quello della matrice di origine.</span><span class="sxs-lookup"><span data-stu-id="a3da4-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>  
  
     <span data-ttu-id="a3da4-112">Purché le classificazioni di due matrici sono uguali, le dimensioni non è necessario essere uguale.</span><span class="sxs-lookup"><span data-stu-id="a3da4-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="a3da4-113">Il numero di elementi in una determinata dimensione può cambiare durante l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="a3da4-113">The number of elements in a given dimension can change during assignment.</span></span>  
  
-   <span data-ttu-id="a3da4-114">**Tipi di elemento.**</span><span class="sxs-lookup"><span data-stu-id="a3da4-114">**Element Types.**</span></span> <span data-ttu-id="a3da4-115">Devono disporre di entrambe le matrici *tipo di riferimento* elementi o entrambe le matrici devono disporre *tipo di valore* elementi.</span><span class="sxs-lookup"><span data-stu-id="a3da4-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="a3da4-116">Per ulteriori informazioni, vedere [tipi di valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="a3da4-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
    -   <span data-ttu-id="a3da4-117">Se entrambe le matrici sono elementi del tipo di valore, i tipi di elemento di dati devono essere esattamente lo stesso.</span><span class="sxs-lookup"><span data-stu-id="a3da4-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="a3da4-118">L'unica eccezione è che è possibile assegnare una matrice di `Enum` elementi in una matrice del tipo di base di tale `Enum`.</span><span class="sxs-lookup"><span data-stu-id="a3da4-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>  
  
    -   <span data-ttu-id="a3da4-119">Se entrambe le matrici hanno riferimento a elementi di tipo, il tipo di elemento di origine deve derivare dal tipo di elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a3da4-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="a3da4-120">In questo caso, le due matrici hanno la stessa relazione di ereditarietà dei rispettivi elementi.</span><span class="sxs-lookup"><span data-stu-id="a3da4-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="a3da4-121">Si tratta di *covarianza*.</span><span class="sxs-lookup"><span data-stu-id="a3da4-121">This is called *array covariance*.</span></span>  
  
 <span data-ttu-id="a3da4-122">Il compilatore segnala un errore se le regole precedenti vengono violate, ad esempio se i tipi di dati non sono compatibili o le classificazioni sono uguali.</span><span class="sxs-lookup"><span data-stu-id="a3da4-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="a3da4-123">È possibile aggiungere il codice per assicurarsi che le matrici sono compatibili prima di tentare un'assegnazione di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="a3da4-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="a3da4-124">È inoltre possibile utilizzare il [operatore TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md) (parola chiave), se si desidera evitare di generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a3da4-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3da4-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3da4-125">See Also</span></span>  
 [<span data-ttu-id="a3da4-126">Array</span><span class="sxs-lookup"><span data-stu-id="a3da4-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="a3da4-127">Risoluzione dei problemi relativi alle matrici</span><span class="sxs-lookup"><span data-stu-id="a3da4-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [<span data-ttu-id="a3da4-128">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="a3da4-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="a3da4-129">Conversioni di matrice</span><span class="sxs-lookup"><span data-stu-id="a3da4-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)

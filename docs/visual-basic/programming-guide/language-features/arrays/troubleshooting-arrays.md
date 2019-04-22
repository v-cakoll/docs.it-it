---
title: Risoluzione dei problemi relativi alle matrici (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 2b051d22fe3d331626f2e181c008043e576b7526
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833373"
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="d76f6-102">Risoluzione dei problemi relativi alle matrici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d76f6-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="d76f6-103">Questa pagina elenca alcuni problemi comuni che possono verificarsi quando si lavora con le matrici.</span><span class="sxs-lookup"><span data-stu-id="d76f6-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="d76f6-104">Errori di compilazione, la dichiarazione e inizializzazione di una matrice</span><span class="sxs-lookup"><span data-stu-id="d76f6-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="d76f6-105">Errori di compilazione possono essere generati da malintesi delle regole per la dichiarazione, la creazione e inizializzazione di matrici.</span><span class="sxs-lookup"><span data-stu-id="d76f6-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="d76f6-106">Le cause più comuni degli errori sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d76f6-106">The most common causes of errors are the following:</span></span>  
  
-   <span data-ttu-id="d76f6-107">Fornendo una [operatore New](../../../../visual-basic/language-reference/operators/new-operator.md) clausola dopo aver specificato le lunghezze delle dimensioni nella dichiarazione di variabile di matrice.</span><span class="sxs-lookup"><span data-stu-id="d76f6-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="d76f6-108">Le righe di codice seguente mostrano le dichiarazioni non valide di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="d76f6-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   <span data-ttu-id="d76f6-109">Specifica le lunghezze delle dimensioni per più di una matrice di primo livello di una matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="d76f6-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="d76f6-110">La riga di codice seguente mostra una dichiarazione non valida di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="d76f6-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   <span data-ttu-id="d76f6-111">L'omissione di `New` parola chiave quando si specificano i valori degli elementi.</span><span class="sxs-lookup"><span data-stu-id="d76f6-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="d76f6-112">La riga di codice seguente mostra una dichiarazione non valida di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="d76f6-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   <span data-ttu-id="d76f6-113">Fornendo una `New` clausola senza parentesi graffe (`{}`).</span><span class="sxs-lookup"><span data-stu-id="d76f6-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="d76f6-114">Le righe di codice seguente mostrano le dichiarazioni non valide di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="d76f6-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="d76f6-115">L'accesso a una matrice fuori intervallo</span><span class="sxs-lookup"><span data-stu-id="d76f6-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="d76f6-116">Il processo di inizializzazione matrice assegna un limite superiore e inferiore di ogni dimensione.</span><span class="sxs-lookup"><span data-stu-id="d76f6-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="d76f6-117">Ogni accesso a un elemento della matrice debba specificare un indice valido o indice, per ogni dimensione.</span><span class="sxs-lookup"><span data-stu-id="d76f6-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="d76f6-118">Se il valore dell'indice è di sotto del limite inferiore o di sopra del limite superiore, un <xref:System.IndexOutOfRangeException> dei risultati dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d76f6-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="d76f6-119">Il compilatore non è in grado di rilevare un errore di questo tipo, in modo che si verifica un errore in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d76f6-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="d76f6-120">Determinazione dei limiti</span><span class="sxs-lookup"><span data-stu-id="d76f6-120">Determining Bounds</span></span>  
 <span data-ttu-id="d76f6-121">Se un altro componente passa una matrice al codice, ad esempio come un argomento di routine, non si conosce la dimensione della matrice o le lunghezze delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d76f6-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="d76f6-122">È sempre necessario determinare il limite massimo per ogni dimensione di matrice prima di tentare di accedere a tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="d76f6-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="d76f6-123">Se la matrice è stata creata da alcuni mezzi diversi da Visual Basic `New` clausola, potrebbe essere un valore diverso da 0 al limite inferiore ed è più sicuro determinare anche tale limite inferiore.</span><span class="sxs-lookup"><span data-stu-id="d76f6-123">If the array has been created by some means other than a Visual Basic `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="d76f6-124">Specificare la dimensione di tipo</span><span class="sxs-lookup"><span data-stu-id="d76f6-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="d76f6-125">Quando si determinano i limiti di una matrice multidimensionale, prestare attenzione a come specificare la dimensione.</span><span class="sxs-lookup"><span data-stu-id="d76f6-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="d76f6-126">Il `dimension` parametri del <xref:System.Array.GetLowerBound%2A> e <xref:System.Array.GetUpperBound%2A> metodi sono basati su 0, mentre il `Rank` parametri di Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> e <xref:Microsoft.VisualBasic.Information.UBound%2A> funzioni sono basate su 1.</span><span class="sxs-lookup"><span data-stu-id="d76f6-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d76f6-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d76f6-127">See also</span></span>

- [<span data-ttu-id="d76f6-128">Matrici</span><span class="sxs-lookup"><span data-stu-id="d76f6-128">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="d76f6-129">Procedura: Inizializzare una variabile di matrice in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d76f6-129">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)

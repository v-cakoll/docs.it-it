---
title: Risoluzione dei problemi relativi alle matrici
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: e633c5a00693f188270b1610abaf2decb656b00a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414595"
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="e04b5-102">Risoluzione dei problemi relativi alle matrici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e04b5-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="e04b5-103">In questa pagina vengono elencati alcuni problemi comuni che possono verificarsi quando si utilizzano matrici.</span><span class="sxs-lookup"><span data-stu-id="e04b5-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="e04b5-104">Errori di compilazione che dichiarano e inizializzano una matrice</span><span class="sxs-lookup"><span data-stu-id="e04b5-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="e04b5-105">Gli errori di compilazione possono derivare dalla comprensione delle regole per la dichiarazione, la creazione e l'inizializzazione di matrici.</span><span class="sxs-lookup"><span data-stu-id="e04b5-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="e04b5-106">Di seguito sono riportate le cause più comuni degli errori:</span><span class="sxs-lookup"><span data-stu-id="e04b5-106">The most common causes of errors are the following:</span></span>  
  
- <span data-ttu-id="e04b5-107">Fornire una [nuova clausola operator](../../../language-reference/operators/new-operator.md) dopo aver specificato le lunghezze della dimensione nella dichiarazione della variabile di matrice.</span><span class="sxs-lookup"><span data-stu-id="e04b5-107">Supplying a [New Operator](../../../language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="e04b5-108">Nelle righe di codice seguenti vengono mostrate dichiarazioni non valide di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="e04b5-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- <span data-ttu-id="e04b5-109">Specifica delle lunghezze delle dimensioni per più della matrice di primo livello di una matrice irregolare.</span><span class="sxs-lookup"><span data-stu-id="e04b5-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="e04b5-110">La seguente riga di codice mostra una dichiarazione non valida di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="e04b5-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- <span data-ttu-id="e04b5-111">Omissione della `New` parola chiave quando si specificano i valori dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="e04b5-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="e04b5-112">La seguente riga di codice mostra una dichiarazione non valida di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="e04b5-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- <span data-ttu-id="e04b5-113">Specifica di una `New` clausola senza parentesi graffe ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="e04b5-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="e04b5-114">Nelle righe di codice seguenti vengono mostrate dichiarazioni non valide di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="e04b5-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="e04b5-115">Accesso a una matrice fuori limite</span><span class="sxs-lookup"><span data-stu-id="e04b5-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="e04b5-116">Il processo di inizializzazione di una matrice assegna un limite superiore e un limite inferiore a ogni dimensione.</span><span class="sxs-lookup"><span data-stu-id="e04b5-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="e04b5-117">Tutti gli accessi a un elemento della matrice devono specificare un indice valido, o pedice, per ogni dimensione.</span><span class="sxs-lookup"><span data-stu-id="e04b5-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="e04b5-118">Se un indice è al di sotto del limite inferiore o al di sopra del limite superiore, viene generata un' <xref:System.IndexOutOfRangeException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="e04b5-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="e04b5-119">Il compilatore non è in grado di rilevare tale errore, quindi si verifica un errore in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e04b5-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="e04b5-120">Determinazione dei limiti</span><span class="sxs-lookup"><span data-stu-id="e04b5-120">Determining Bounds</span></span>  
 <span data-ttu-id="e04b5-121">Se un altro componente passa una matrice al codice, ad esempio come argomento di routine, non si conosce la dimensione della matrice o la lunghezza delle relative dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e04b5-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="e04b5-122">Prima di provare ad accedere a qualsiasi elemento, è necessario determinare sempre il limite superiore per ogni dimensione di una matrice.</span><span class="sxs-lookup"><span data-stu-id="e04b5-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="e04b5-123">Se la matrice è stata creata con un mezzo diverso da una `New` clausola Visual Basic, il limite inferiore potrebbe essere diverso da 0 ed è più sicuro determinare anche tale limite inferiore.</span><span class="sxs-lookup"><span data-stu-id="e04b5-123">If the array has been created by some means other than a Visual Basic `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="e04b5-124">Specifica della dimensione</span><span class="sxs-lookup"><span data-stu-id="e04b5-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="e04b5-125">Quando si determinano i limiti di una matrice multidimensionale, prestare attenzione alla modalità di impostazione della dimensione.</span><span class="sxs-lookup"><span data-stu-id="e04b5-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="e04b5-126">I `dimension` parametri dei <xref:System.Array.GetLowerBound%2A> metodi e <xref:System.Array.GetUpperBound%2A> sono basati su 0, mentre i `Rank` parametri del Visual Basic e delle <xref:Microsoft.VisualBasic.Information.LBound%2A> <xref:Microsoft.VisualBasic.Information.UBound%2A> funzioni sono in base 1.</span><span class="sxs-lookup"><span data-stu-id="e04b5-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e04b5-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e04b5-127">See also</span></span>

- [<span data-ttu-id="e04b5-128">Matrici</span><span class="sxs-lookup"><span data-stu-id="e04b5-128">Arrays</span></span>](index.md)
- [<span data-ttu-id="e04b5-129">Procedura: Inizializzare una variabile di matrice in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e04b5-129">How to: Initialize an Array Variable in Visual Basic</span></span>](how-to-initialize-an-array-variable.md)

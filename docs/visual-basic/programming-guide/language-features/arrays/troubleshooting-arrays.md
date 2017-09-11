---
title: Risoluzione dei problemi di matrici (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 571731ae7066ba7ec52d4a2413b4d948f3f35bfe
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="3c2a4-102">Risoluzione dei problemi relativi alle matrici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c2a4-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="3c2a4-103">Questa pagina sono elencati alcuni problemi comuni che possono verificarsi quando si lavora con le matrici.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="3c2a4-104">Errori di compilazione dichiarazione e inizializzazione di una matrice</span><span class="sxs-lookup"><span data-stu-id="3c2a4-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="3c2a4-105">Errori di compilazione possono dipendere da un'incomprensione delle regole per la dichiarazione, la creazione e inizializzazione di matrici.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="3c2a4-106">Le cause più comuni di errori sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c2a4-106">The most common causes of errors are the following:</span></span>  
  
-   <span data-ttu-id="3c2a4-107">Fornendo un [nuovo operatore](../../../../visual-basic/language-reference/operators/new-operator.md) clausola dopo aver specificato le lunghezze delle dimensioni nella dichiarazione di variabile di matrice.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="3c2a4-108">Le righe di codice seguente mostrano le dichiarazioni non valide di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   <span data-ttu-id="3c2a4-109">Specifica le lunghezze delle dimensioni per più di una matrice di livello superiore di una matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="3c2a4-110">L'esempio di codice seguente viene illustrata una dichiarazione di questo tipo non valida.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   <span data-ttu-id="3c2a4-111">L'omissione di `New` parola chiave quando si specificano i valori dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="3c2a4-112">L'esempio di codice seguente viene illustrata una dichiarazione di questo tipo non valida.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   <span data-ttu-id="3c2a4-113">Fornendo un `New` clausola senza parentesi graffe (`{}`).</span><span class="sxs-lookup"><span data-stu-id="3c2a4-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="3c2a4-114">Le righe di codice seguente mostrano le dichiarazioni non valide di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="3c2a4-115">Accesso a una matrice fuori dai limiti</span><span class="sxs-lookup"><span data-stu-id="3c2a4-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="3c2a4-116">Il processo di inizializzazione di una matrice assegna un limite superiore e inferiore di ogni dimensione.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="3c2a4-117">L'accesso a un elemento della matrice debba specificare un indice valido o un indice, per ogni dimensione.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="3c2a4-118">Se il valore dell'indice è di sotto del limite inferiore o di sopra del limite superiore, un <xref:System.IndexOutOfRangeException>risultati dell'eccezione.</xref:System.IndexOutOfRangeException></span><span class="sxs-lookup"><span data-stu-id="3c2a4-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="3c2a4-119">Il compilatore non è in grado di rilevare un errore di questo tipo, si verifica un errore in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="3c2a4-120">Determinazione dei limiti</span><span class="sxs-lookup"><span data-stu-id="3c2a4-120">Determining Bounds</span></span>  
 <span data-ttu-id="3c2a4-121">Se un altro componente passa una matrice al codice, ad esempio come un argomento di routine, non si conosce la dimensione della matrice o le lunghezze delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="3c2a4-122">È sempre necessario determinare il limite superiore per ogni dimensione della matrice prima di tentare di accedere a tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="3c2a4-123">Se la matrice è stata creata in modo diverso da un [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `New` clausola, potrebbe essere il limite inferiore diverso da 0 ed è più sicuro determinare tale limite.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-123">If the array has been created by some means other than a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="3c2a4-124">Specifica la dimensione</span><span class="sxs-lookup"><span data-stu-id="3c2a4-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="3c2a4-125">Durante la determinazione dei limiti di una matrice multidimensionale, prestare attenzione a come specificare la dimensione.</span><span class="sxs-lookup"><span data-stu-id="3c2a4-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="3c2a4-126">Il `dimension` parametri della <xref:System.Array.GetLowerBound%2A>e <xref:System.Array.GetUpperBound%2A>metodi sono basati su 0, mentre il `Rank` parametri di [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A>e <xref:Microsoft.VisualBasic.Information.UBound%2A>funzioni sono basati su 1.</xref:Microsoft.VisualBasic.Information.UBound%2A> </xref:Microsoft.VisualBasic.Information.LBound%2A> </xref:System.Array.GetUpperBound%2A> </xref:System.Array.GetLowerBound%2A></span><span class="sxs-lookup"><span data-stu-id="3c2a4-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c2a4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c2a4-127">See Also</span></span>  
 <span data-ttu-id="3c2a4-128">[Matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="3c2a4-128">[Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md) </span></span>  
<span data-ttu-id="3c2a4-129"> [Procedura: inizializzare una variabile di matrice in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span><span class="sxs-lookup"><span data-stu-id="3c2a4-129"> [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span></span>

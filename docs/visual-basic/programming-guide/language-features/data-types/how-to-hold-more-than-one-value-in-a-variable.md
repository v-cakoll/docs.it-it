---
title: 'Procedura: Inserire più valori in una variabile (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: e2e1648ea508ecdd744adb8d2a4f7fdbc1e586c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906490"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="6c559-102">Procedura: Inserire più valori in una variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c559-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>
<span data-ttu-id="6c559-103">Una variabile contiene più di un valore se si dichiara che questo sia di un *tipo di dati composito*.</span><span class="sxs-lookup"><span data-stu-id="6c559-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>  
  
 <span data-ttu-id="6c559-104">[Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) includono matrici, strutture e classi.</span><span class="sxs-lookup"><span data-stu-id="6c559-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="6c559-105">Una variabile di un tipo di dati composito può contenere una combinazione di tipi di dati elementari e altri tipi composti.</span><span class="sxs-lookup"><span data-stu-id="6c559-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="6c559-106">Classi e strutture possono contenere codice, nonché i dati.</span><span class="sxs-lookup"><span data-stu-id="6c559-106">Structures and classes can hold code as well as data.</span></span>  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="6c559-107">Per inserire più valori in una variabile</span><span class="sxs-lookup"><span data-stu-id="6c559-107">To hold more than one value in a variable</span></span>  
  
1. <span data-ttu-id="6c559-108">Determinare a quale tipo di dati composito da usare per la variabile.</span><span class="sxs-lookup"><span data-stu-id="6c559-108">Determine what composite data type you want to use for your variable.</span></span>  
  
2. <span data-ttu-id="6c559-109">Se non è già stato definito il tipo di dati compositi, definirlo in modo che la variabile può usarlo.</span><span class="sxs-lookup"><span data-stu-id="6c559-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>  
  
    - <span data-ttu-id="6c559-110">Definire una struttura con un [istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6c559-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
    - <span data-ttu-id="6c559-111">Definire una matrice con un [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6c559-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
    - <span data-ttu-id="6c559-112">Definire una classe con un [istruzione Class](../../../../visual-basic/language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6c559-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
3. <span data-ttu-id="6c559-113">Dichiarare la variabile con un `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="6c559-113">Declare your variable with a `Dim` statement.</span></span>  
  
4. <span data-ttu-id="6c559-114">Seguire il nome della variabile con un `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="6c559-114">Follow the variable name with an `As` clause.</span></span>  
  
5. <span data-ttu-id="6c559-115">Seguire il `As` parola chiave con il nome del tipo di dati compositi appropriato.</span><span class="sxs-lookup"><span data-stu-id="6c559-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c559-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c559-116">See also</span></span>

- [<span data-ttu-id="6c559-117">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="6c559-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="6c559-118">Caratteri tipo</span><span class="sxs-lookup"><span data-stu-id="6c559-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="6c559-119">Tipi di dati compositi</span><span class="sxs-lookup"><span data-stu-id="6c559-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="6c559-120">Strutture</span><span class="sxs-lookup"><span data-stu-id="6c559-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="6c559-121">Matrici</span><span class="sxs-lookup"><span data-stu-id="6c559-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="6c559-122">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="6c559-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="6c559-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="6c559-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)

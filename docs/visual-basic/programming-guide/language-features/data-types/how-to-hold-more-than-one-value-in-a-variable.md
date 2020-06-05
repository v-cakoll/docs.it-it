---
title: 'Procedura: Inserire più valori in una variabile'
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
ms.openlocfilehash: 399c5909ee6988f96bcc85260b0401f3bd18a0f2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393896"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="3f72f-102">Procedura: inserire più valori in una variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f72f-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>

<span data-ttu-id="3f72f-103">Una variabile include più di un valore se lo si dichiara come *tipo di dati composito*.</span><span class="sxs-lookup"><span data-stu-id="3f72f-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>

<span data-ttu-id="3f72f-104">[I tipi di dati compositi](composite-data-types.md) includono strutture, matrici e classi.</span><span class="sxs-lookup"><span data-stu-id="3f72f-104">[Composite Data Types](composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="3f72f-105">Una variabile di un tipo di dati composito può avere una combinazione di tipi di dati elementari e altri tipi compositi.</span><span class="sxs-lookup"><span data-stu-id="3f72f-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="3f72f-106">Le strutture e le classi possono conservare il codice e i dati.</span><span class="sxs-lookup"><span data-stu-id="3f72f-106">Structures and classes can hold code as well as data.</span></span>

## <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="3f72f-107">Per conservare più di un valore in una variabile</span><span class="sxs-lookup"><span data-stu-id="3f72f-107">To hold more than one value in a variable</span></span>

1. <span data-ttu-id="3f72f-108">Determinare il tipo di dati composito che si desidera utilizzare per la variabile.</span><span class="sxs-lookup"><span data-stu-id="3f72f-108">Determine what composite data type you want to use for your variable.</span></span>

2. <span data-ttu-id="3f72f-109">Se il tipo di dati composito non è già definito, definirlo in modo che possa essere utilizzato dalla variabile.</span><span class="sxs-lookup"><span data-stu-id="3f72f-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>

    - <span data-ttu-id="3f72f-110">Definire una struttura con un' [istruzione Structure](../../../language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3f72f-110">Define a structure with a [Structure Statement](../../../language-reference/statements/structure-statement.md).</span></span>

    - <span data-ttu-id="3f72f-111">Definire una matrice con un' [istruzione Dim](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3f72f-111">Define an array with a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span>

    - <span data-ttu-id="3f72f-112">Definire una classe con un' [istruzione di classe](../../../language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3f72f-112">Define a class with a [Class Statement](../../../language-reference/statements/class-statement.md).</span></span>

3. <span data-ttu-id="3f72f-113">Dichiarare la variabile con un' `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="3f72f-113">Declare your variable with a `Dim` statement.</span></span>

4. <span data-ttu-id="3f72f-114">Seguire il nome della variabile con una `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="3f72f-114">Follow the variable name with an `As` clause.</span></span>

5. <span data-ttu-id="3f72f-115">Seguire la `As` parola chiave con il nome del tipo di dati composito appropriato.</span><span class="sxs-lookup"><span data-stu-id="3f72f-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f72f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f72f-116">See also</span></span>

- [<span data-ttu-id="3f72f-117">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="3f72f-117">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="3f72f-118">Caratteri tipo</span><span class="sxs-lookup"><span data-stu-id="3f72f-118">Type Characters</span></span>](type-characters.md)
- [<span data-ttu-id="3f72f-119">Tipi di dati compositi</span><span class="sxs-lookup"><span data-stu-id="3f72f-119">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="3f72f-120">Strutture</span><span class="sxs-lookup"><span data-stu-id="3f72f-120">Structures</span></span>](structures.md)
- [<span data-ttu-id="3f72f-121">Matrici</span><span class="sxs-lookup"><span data-stu-id="3f72f-121">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="3f72f-122">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="3f72f-122">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="3f72f-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="3f72f-123">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)

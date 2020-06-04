---
title: Tipi di dati carattere
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 33dd4c62776ae8c5ec0ce0a6d0858a7ed0d047fb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401992"
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="c7fe6-102">Dati di tipo carattere (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7fe6-102">Character Data Types (Visual Basic)</span></span>
<span data-ttu-id="c7fe6-103">Visual Basic fornisce *tipi di dati di tipo carattere* per gestire i caratteri stampabili e visualizzabili.</span><span class="sxs-lookup"><span data-stu-id="c7fe6-103">Visual Basic provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="c7fe6-104">Mentre entrambi gestiscono i caratteri Unicode, contiene `Char` un singolo carattere mentre `String` contiene un numero di caratteri indefinito.</span><span class="sxs-lookup"><span data-stu-id="c7fe6-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="c7fe6-105">Per una tabella in cui viene visualizzato un confronto affiancato dei tipi di dati Visual Basic, vedere [tipi di dati](../../../language-reference/data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="c7fe6-105">For a table that displays a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../language-reference/data-types/index.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="c7fe6-106">Tipo char</span><span class="sxs-lookup"><span data-stu-id="c7fe6-106">Char Type</span></span>  
 <span data-ttu-id="c7fe6-107">Il `Char` tipo di dati è un singolo carattere Unicode a due byte (a 16 bit).</span><span class="sxs-lookup"><span data-stu-id="c7fe6-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="c7fe6-108">Se una variabile archivia sempre esattamente un carattere, dichiararlo come `Char` .</span><span class="sxs-lookup"><span data-stu-id="c7fe6-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="c7fe6-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c7fe6-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 <span data-ttu-id="c7fe6-110">Ogni valore possibile in una `Char` `String` variabile o è un *punto di codice*, o codice carattere, nel set di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="c7fe6-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="c7fe6-111">I caratteri Unicode includono il set di caratteri ASCII di base, diverse altre lettere di alfabeto, accenti, simboli di valuta, frazioni, segni diacritici e simboli matematici e tecnici.</span><span class="sxs-lookup"><span data-stu-id="c7fe6-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7fe6-112">Il set di caratteri Unicode riserva i punti di codice da D800 a DFFF (da 55296 a 55551 Decimal) per le *coppie di surrogati*, che richiedono valori 2 16 bit per rappresentare un singolo punto di codice.</span><span class="sxs-lookup"><span data-stu-id="c7fe6-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="c7fe6-113">Una `Char` variabile non può avere una coppia di surrogati e un oggetto `String` Usa due posizioni per mantenere tale coppia.</span><span class="sxs-lookup"><span data-stu-id="c7fe6-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="c7fe6-114">Per altre informazioni, vedere [tipo di dati char](../../../language-reference/data-types/char-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="c7fe6-114">For more information, see [Char Data Type](../../../language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="c7fe6-115">Tipo di stringa</span><span class="sxs-lookup"><span data-stu-id="c7fe6-115">String Type</span></span>  
 <span data-ttu-id="c7fe6-116">Il `String` tipo di dati è una sequenza di zero o più caratteri Unicode a 2 byte (a 16 bit).</span><span class="sxs-lookup"><span data-stu-id="c7fe6-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="c7fe6-117">Se una variabile può contenere un numero indefinito di caratteri, dichiararla come `String` .</span><span class="sxs-lookup"><span data-stu-id="c7fe6-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="c7fe6-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c7fe6-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 <span data-ttu-id="c7fe6-119">Per ulteriori informazioni, vedere [tipo di dati String](../../../language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="c7fe6-119">For more information, see [String Data Type](../../../language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7fe6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7fe6-120">See also</span></span>

- [<span data-ttu-id="c7fe6-121">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="c7fe6-121">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="c7fe6-122">Tipi di dati compositi</span><span class="sxs-lookup"><span data-stu-id="c7fe6-122">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="c7fe6-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7fe6-123">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="c7fe6-124">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="c7fe6-124">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="c7fe6-125">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7fe6-125">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="c7fe6-126">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="c7fe6-126">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="c7fe6-127">Caratteri tipo</span><span class="sxs-lookup"><span data-stu-id="c7fe6-127">Type Characters</span></span>](type-characters.md)

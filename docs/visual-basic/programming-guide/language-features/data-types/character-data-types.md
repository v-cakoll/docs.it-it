---
title: Dati di tipo carattere (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: afd368c00444f136c6d69b02a733c82f0c8eafe0
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="7bcc5-102">Dati di tipo carattere (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7bcc5-102">Character Data Types (Visual Basic)</span></span>
<span data-ttu-id="7bcc5-103">Visual Basic fornisce *tipi di dati character* per la gestione dei caratteri stampabili e visualizzabili.</span><span class="sxs-lookup"><span data-stu-id="7bcc5-103">Visual Basic provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="7bcc5-104">Sebbene entrambi gestiscano i caratteri Unicode, `Char` contiene un singolo carattere mentre `String` contiene un numero indefinito di caratteri.</span><span class="sxs-lookup"><span data-stu-id="7bcc5-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="7bcc5-105">Per una tabella che visualizza un confronto side-by-side dei tipi di dati Visual Basic, vedere [tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="7bcc5-105">For a table that displays a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="7bcc5-106">Char (tipo)</span><span class="sxs-lookup"><span data-stu-id="7bcc5-106">Char Type</span></span>  
 <span data-ttu-id="7bcc5-107">Il `Char` tipo di dati è un singolo carattere Unicode di due byte (16 bit).</span><span class="sxs-lookup"><span data-stu-id="7bcc5-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="7bcc5-108">Se una variabile memorizza sempre esattamente un carattere, dichiararla come `Char`.</span><span class="sxs-lookup"><span data-stu-id="7bcc5-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="7bcc5-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bcc5-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 <span data-ttu-id="7bcc5-110">Ogni valore possibile in un `Char` o `String` variabile è un *punto di codice*, o codice di carattere, nel set di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="7bcc5-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="7bcc5-111">I caratteri Unicode includono set di caratteri ASCII di base, diverse altre lettere dell'alfabeto, accenti, simboli di valuta, frazioni, segni diacritici e i simboli matematici e tecnici.</span><span class="sxs-lookup"><span data-stu-id="7bcc5-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bcc5-112">I punti di codice D800 a DFFF (da 55296 55551 decimale) per le riserve di set di caratteri Unicode *coppie di surrogati*, che sono richiesti due valori a 16 bit per rappresentare un singolo punto di codice.</span><span class="sxs-lookup"><span data-stu-id="7bcc5-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="7bcc5-113">Oggetto `Char` variabile non può contenere una coppia di surrogati e un `String` utilizza due posizioni per mantenere tale coppia.</span><span class="sxs-lookup"><span data-stu-id="7bcc5-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="7bcc5-114">Per ulteriori informazioni, vedere [tipo di dati Char](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="7bcc5-114">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="7bcc5-115">Tipo di stringa</span><span class="sxs-lookup"><span data-stu-id="7bcc5-115">String Type</span></span>  
 <span data-ttu-id="7bcc5-116">Il `String` tipo di dati è una sequenza di zero o più caratteri Unicode a due byte (16 bit).</span><span class="sxs-lookup"><span data-stu-id="7bcc5-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="7bcc5-117">Se una variabile può contenere un numero indefinito di caratteri, dichiararla come `String`.</span><span class="sxs-lookup"><span data-stu-id="7bcc5-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="7bcc5-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bcc5-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 <span data-ttu-id="7bcc5-119">Per ulteriori informazioni, vedere [tipo di dati stringa](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="7bcc5-119">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bcc5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bcc5-120">See Also</span></span>  
 [<span data-ttu-id="7bcc5-121">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="7bcc5-121">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="7bcc5-122">Tipi di dati compositi</span><span class="sxs-lookup"><span data-stu-id="7bcc5-122">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="7bcc5-123">Tipi generici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7bcc5-123">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="7bcc5-124">Tipi valore e tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="7bcc5-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="7bcc5-125">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7bcc5-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="7bcc5-126">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="7bcc5-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="7bcc5-127">Caratteri tipo</span><span class="sxs-lookup"><span data-stu-id="7bcc5-127">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)

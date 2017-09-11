---
title: Tipi di dati (Visual Basic) carattere | Documenti di Microsoft
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
- data types [Visual Basic], character
- String data type, character data types
- character data types [Visual Basic]
- Char data type, character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: 23
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
ms.openlocfilehash: 3407f614d5898f4fccf04e0363ec31669661b60a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="f99d8-102">Dati di tipo carattere (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99d8-102">Character Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="f99d8-103">fornisce *tipi di dati carattere* per la gestione dei caratteri stampabili e visualizzabili.</span><span class="sxs-lookup"><span data-stu-id="f99d8-103"> provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="f99d8-104">Sebbene entrambi gestiscano i caratteri Unicode, `Char` contiene un singolo carattere mentre `String` contiene un numero indefinito di caratteri.</span><span class="sxs-lookup"><span data-stu-id="f99d8-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="f99d8-105">Per una tabella che visualizza un confronto side-by-side di [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tipi di dati, vedere [tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="f99d8-105">For a table that displays a side-by-side comparison of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="f99d8-106">Char (tipo)</span><span class="sxs-lookup"><span data-stu-id="f99d8-106">Char Type</span></span>  
 <span data-ttu-id="f99d8-107">Il `Char` tipo di dati è un singolo carattere di Unicode a due byte (16 bit).</span><span class="sxs-lookup"><span data-stu-id="f99d8-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="f99d8-108">Se una variabile memorizza sempre esattamente un carattere, dichiararla come `Char`.</span><span class="sxs-lookup"><span data-stu-id="f99d8-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="f99d8-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f99d8-109">For example:</span></span>  
  
 <span data-ttu-id="f99d8-110">[!code-vb[VbVbalrCharTypes n.&1;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f99d8-110">[!code-vb[VbVbalrCharTypes#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]</span></span>  
  
 <span data-ttu-id="f99d8-111">Ogni valore possibile in un `Char` o `String` variabile è un *punto di codice*, o codice di carattere, nel set di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="f99d8-111">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="f99d8-112">I caratteri Unicode includono set di caratteri ASCII di base diverse altre lettere dell'alfabeto, accenti, simboli di valuta, le frazioni di secondo, i segni diacritici e simboli matematici e tecnici.</span><span class="sxs-lookup"><span data-stu-id="f99d8-112">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f99d8-113">Set di caratteri Unicode riserva i punti di codice D800 a DFFF (da 55296 a 55551 in formato decimale) per *coppie di surrogati*, che richiedono due valori a 16 bit per rappresentare un singolo punto di codice.</span><span class="sxs-lookup"><span data-stu-id="f99d8-113">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="f99d8-114">Oggetto `Char` variabile non può contenere una coppia di surrogati e un `String` utilizza due posizioni per mantenere tale coppia.</span><span class="sxs-lookup"><span data-stu-id="f99d8-114">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="f99d8-115">Per ulteriori informazioni, vedere [tipo di dati Char](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="f99d8-115">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="f99d8-116">Tipo di stringa</span><span class="sxs-lookup"><span data-stu-id="f99d8-116">String Type</span></span>  
 <span data-ttu-id="f99d8-117">Il `String` tipo di dati è una sequenza di zero o più caratteri Unicode a due byte (16 bit).</span><span class="sxs-lookup"><span data-stu-id="f99d8-117">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="f99d8-118">Se una variabile può contenere un numero indefinito di caratteri, dichiararla come `String`.</span><span class="sxs-lookup"><span data-stu-id="f99d8-118">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="f99d8-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f99d8-119">For example:</span></span>  
  
 <span data-ttu-id="f99d8-120">[!code-vb[VbVbalrCharTypes n.&2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f99d8-120">[!code-vb[VbVbalrCharTypes#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]</span></span>  
  
 <span data-ttu-id="f99d8-121">Per ulteriori informazioni, vedere [tipo di dati stringa](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="f99d8-121">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f99d8-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f99d8-122">See Also</span></span>  
 <span data-ttu-id="f99d8-123">[Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="f99d8-123">[Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="f99d8-124"> [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="f99d8-124"> [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
<span data-ttu-id="f99d8-125"> [Tipi generici in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="f99d8-125"> [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="f99d8-126"> [Tipi di valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="f99d8-126"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="f99d8-127"> [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="f99d8-127"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="f99d8-128"> [Risoluzione dei tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="f99d8-128"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="f99d8-129"> [Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="f99d8-129"> [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span>

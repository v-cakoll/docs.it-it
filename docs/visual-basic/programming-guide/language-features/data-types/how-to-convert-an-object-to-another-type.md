---
title: 'Procedura: Convertire un oggetto in un altro tipo in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: d80dc542f71aaf3eec6891006d77c5d39c985abf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64600998"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="8bb70-102">Procedura: Convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8bb70-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="8bb70-103">Si converte un `Object` variabile in un altro tipo di dati con una parola chiave di conversione, ad esempio [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span><span class="sxs-lookup"><span data-stu-id="8bb70-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bb70-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8bb70-104">Example</span></span>  
 <span data-ttu-id="8bb70-105">L'esempio seguente converte un' `Object` variabile in un `Integer` e un `String`.</span><span class="sxs-lookup"><span data-stu-id="8bb70-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="8bb70-106">Se si è certi che il contenuto di un `Object` sono variabile di un particolare tipo di dati, è preferibile convertire la variabile di quel tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="8bb70-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="8bb70-107">Se si continua a usare il `Object` variabile, verrà eseguita una *boxing* e *unboxing* (per un tipo di valore) o *associazione tardiva* (per un tipo riferimento).</span><span class="sxs-lookup"><span data-stu-id="8bb70-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="8bb70-108">Queste operazioni tutti richiedere più tempo di esecuzione e riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8bb70-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8bb70-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8bb70-109">Compiling the Code</span></span>  
 <span data-ttu-id="8bb70-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8bb70-110">This example requires:</span></span>  
  
- <span data-ttu-id="8bb70-111">Un riferimento allo spazio dei nomi <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8bb70-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bb70-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bb70-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="8bb70-113">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8bb70-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="8bb70-114">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="8bb70-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="8bb70-115">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="8bb70-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="8bb70-116">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="8bb70-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="8bb70-117">Conversioni di matrice</span><span class="sxs-lookup"><span data-stu-id="8bb70-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="8bb70-118">Strutture</span><span class="sxs-lookup"><span data-stu-id="8bb70-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="8bb70-119">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="8bb70-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8bb70-120">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="8bb70-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)

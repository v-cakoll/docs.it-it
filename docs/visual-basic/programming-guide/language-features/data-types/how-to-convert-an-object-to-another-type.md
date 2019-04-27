---
title: 'Procedura: Convertire un oggetto in un altro tipo in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 1e515c0f4ce8e787754c61a9b53d247fa93c49f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906529"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="14421-102">Procedura: Convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14421-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="14421-103">Si converte un `Object` variabile in un altro tipo di dati con una parola chiave di conversione, ad esempio [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span><span class="sxs-lookup"><span data-stu-id="14421-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="14421-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="14421-104">Example</span></span>  
 <span data-ttu-id="14421-105">L'esempio seguente converte un' `Object` variabile in un `Integer` e un `String`.</span><span class="sxs-lookup"><span data-stu-id="14421-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="14421-106">Se si è certi che il contenuto di un `Object` sono variabile di un particolare tipo di dati, è preferibile convertire la variabile di quel tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="14421-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="14421-107">Se si continua a usare il `Object` variabile, verrà eseguita una *boxing* e *unboxing* (per un tipo di valore) o *associazione tardiva* (per un tipo riferimento).</span><span class="sxs-lookup"><span data-stu-id="14421-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="14421-108">Queste operazioni tutti richiedere più tempo di esecuzione e riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="14421-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="14421-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="14421-109">Compiling the Code</span></span>  
 <span data-ttu-id="14421-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="14421-110">This example requires:</span></span>  
  
-   <span data-ttu-id="14421-111">Un riferimento allo spazio dei nomi <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="14421-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14421-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14421-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="14421-113">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14421-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="14421-114">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="14421-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="14421-115">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="14421-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="14421-116">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="14421-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="14421-117">Conversioni di matrice</span><span class="sxs-lookup"><span data-stu-id="14421-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="14421-118">Strutture</span><span class="sxs-lookup"><span data-stu-id="14421-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="14421-119">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="14421-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="14421-120">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="14421-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)

---
title: 'Procedura: convertire un oggetto in un altro tipo in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 367991e4bbca710df54edf73179f855ff79bb56e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647618"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="5b7b8-102">Procedura: convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5b7b8-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="5b7b8-103">Convertire un `Object` variabile a un altro tipo di dati tramite una parola chiave di conversione, ad esempio [CType (funzione)](../../../../visual-basic/language-reference/functions/ctype-function.md).</span><span class="sxs-lookup"><span data-stu-id="5b7b8-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b7b8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5b7b8-104">Example</span></span>  
 <span data-ttu-id="5b7b8-105">L'esempio seguente converte un `Object` variabile a un `Integer` e `String`.</span><span class="sxs-lookup"><span data-stu-id="5b7b8-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="5b7b8-106">Se si è certi che il contenuto di un `Object` sono variabile di un particolare tipo di dati, si consiglia di convertire la variabile di quel tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="5b7b8-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="5b7b8-107">Se si continua a utilizzare il `Object` variabile, verrà eseguita una *boxing* e *unboxing* (per un tipo di valore) o *ad associazione tardiva* (per un tipo di riferimento).</span><span class="sxs-lookup"><span data-stu-id="5b7b8-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="5b7b8-108">Queste operazioni tutti richiedere più tempo di esecuzione e riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="5b7b8-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5b7b8-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5b7b8-109">Compiling the Code</span></span>  
 <span data-ttu-id="5b7b8-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b7b8-110">This example requires:</span></span>  
  
-   <span data-ttu-id="5b7b8-111">Un riferimento allo spazio dei nomi <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5b7b8-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b7b8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b7b8-112">See Also</span></span>  
 <xref:System.Object>  
 [<span data-ttu-id="5b7b8-113">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5b7b8-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="5b7b8-114">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="5b7b8-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="5b7b8-115">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="5b7b8-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="5b7b8-116">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="5b7b8-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="5b7b8-117">Conversioni di matrice</span><span class="sxs-lookup"><span data-stu-id="5b7b8-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [<span data-ttu-id="5b7b8-118">Strutture</span><span class="sxs-lookup"><span data-stu-id="5b7b8-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="5b7b8-119">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="5b7b8-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="5b7b8-120">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="5b7b8-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)

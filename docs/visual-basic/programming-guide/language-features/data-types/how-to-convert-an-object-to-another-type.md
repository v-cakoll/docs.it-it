---
title: 'Procedura: convertire un oggetto in un altro tipo'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 19708d03b0514f4572c2baa53e05781e5949766b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350065"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="4de0a-102">Procedura: convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4de0a-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="4de0a-103">Per convertire una variabile di `Object` in un altro tipo di dati, è possibile usare una parola chiave di conversione come la [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md).</span><span class="sxs-lookup"><span data-stu-id="4de0a-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4de0a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4de0a-104">Example</span></span>  
 <span data-ttu-id="4de0a-105">Nell'esempio seguente viene convertita una variabile `Object` in un `Integer` e in un `String`.</span><span class="sxs-lookup"><span data-stu-id="4de0a-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="4de0a-106">Se si è certi che il contenuto di una variabile `Object` è di un determinato tipo di dati, è preferibile convertire la variabile in quel tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="4de0a-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="4de0a-107">Se si continua a usare la variabile di `Object`, è necessario eseguire la *conversione boxing* e unboxing (per un tipo di valore) o l' *associazione tardiva* *(per* un tipo di riferimento).</span><span class="sxs-lookup"><span data-stu-id="4de0a-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="4de0a-108">Queste operazioni consentono di ottenere tempo di esecuzione aggiuntivo e rallentare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="4de0a-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4de0a-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4de0a-109">Compiling the Code</span></span>  
 <span data-ttu-id="4de0a-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4de0a-110">This example requires:</span></span>  
  
- <span data-ttu-id="4de0a-111">Un riferimento allo spazio dei nomi <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4de0a-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de0a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4de0a-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="4de0a-113">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4de0a-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="4de0a-114">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="4de0a-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="4de0a-115">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="4de0a-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="4de0a-116">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="4de0a-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="4de0a-117">Conversioni di matrice</span><span class="sxs-lookup"><span data-stu-id="4de0a-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="4de0a-118">Strutture</span><span class="sxs-lookup"><span data-stu-id="4de0a-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="4de0a-119">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="4de0a-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="4de0a-120">CString</span><span class="sxs-lookup"><span data-stu-id="4de0a-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)

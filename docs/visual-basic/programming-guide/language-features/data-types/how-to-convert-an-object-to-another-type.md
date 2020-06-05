---
title: 'Procedura: Convertire un oggetto in un altro tipo'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: cdb78bc66867ce27076d7b7e42de6a2880cb3a8c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393961"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="16ad3-102">Procedura: convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16ad3-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="16ad3-103">Per convertire una `Object` variabile in un altro tipo di dati, è possibile utilizzare una parola chiave di conversione come la [funzione CType](../../../language-reference/functions/ctype-function.md).</span><span class="sxs-lookup"><span data-stu-id="16ad3-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16ad3-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="16ad3-104">Example</span></span>  
 <span data-ttu-id="16ad3-105">Nell'esempio seguente viene convertita una `Object` variabile in un oggetto `Integer` e un oggetto `String` .</span><span class="sxs-lookup"><span data-stu-id="16ad3-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="16ad3-106">Se si sa che il contenuto di una `Object` variabile è di un determinato tipo di dati, è preferibile convertire la variabile in quel tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="16ad3-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="16ad3-107">Se si continua a usare la `Object` variabile, è necessario eseguire la *conversione boxing* e *unboxing* (per un tipo di valore) o l' *associazione tardiva* (per un tipo di riferimento).</span><span class="sxs-lookup"><span data-stu-id="16ad3-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="16ad3-108">Queste operazioni consentono di ottenere tempo di esecuzione aggiuntivo e rallentare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="16ad3-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="16ad3-109">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="16ad3-109">Compile the code</span></span>  
 <span data-ttu-id="16ad3-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="16ad3-110">This example requires:</span></span>  
  
- <span data-ttu-id="16ad3-111">Un riferimento allo spazio dei nomi <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="16ad3-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16ad3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16ad3-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="16ad3-113">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16ad3-113">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="16ad3-114">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="16ad3-114">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)
- [<span data-ttu-id="16ad3-115">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="16ad3-115">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="16ad3-116">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="16ad3-116">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="16ad3-117">Conversioni di matrice</span><span class="sxs-lookup"><span data-stu-id="16ad3-117">Array Conversions</span></span>](array-conversions.md)
- [<span data-ttu-id="16ad3-118">Strutture</span><span class="sxs-lookup"><span data-stu-id="16ad3-118">Structures</span></span>](structures.md)
- [<span data-ttu-id="16ad3-119">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="16ad3-119">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="16ad3-120">CString</span><span class="sxs-lookup"><span data-stu-id="16ad3-120">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)

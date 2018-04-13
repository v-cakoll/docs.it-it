---
title: 'Procedura: convertire un oggetto in un altro tipo in Visual Basic'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 053c93e7cf842138f5b9299cd2fcfa56342dd40b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="3c947-102">Procedura: convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c947-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="3c947-103">Convertire un `Object` variabile a un altro tipo di dati tramite una parola chiave di conversione, ad esempio [CType (funzione)](../../../../visual-basic/language-reference/functions/ctype-function.md).</span><span class="sxs-lookup"><span data-stu-id="3c947-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c947-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c947-104">Example</span></span>  
 <span data-ttu-id="3c947-105">L'esempio seguente converte un `Object` variabile a un `Integer` e `String`.</span><span class="sxs-lookup"><span data-stu-id="3c947-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="3c947-106">Se si è certi che il contenuto di un `Object` sono variabile di un particolare tipo di dati, si consiglia di convertire la variabile di quel tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="3c947-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="3c947-107">Se si continua a utilizzare il `Object` variabile, verrà eseguita una *boxing* e *unboxing* (per un tipo di valore) o *ad associazione tardiva* (per un tipo di riferimento).</span><span class="sxs-lookup"><span data-stu-id="3c947-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="3c947-108">Queste operazioni tutti richiedere più tempo di esecuzione e riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3c947-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3c947-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3c947-109">Compiling the Code</span></span>  
 <span data-ttu-id="3c947-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c947-110">This example requires:</span></span>  
  
-   <span data-ttu-id="3c947-111">Un riferimento allo spazio dei nomi <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3c947-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c947-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c947-112">See Also</span></span>  
 <xref:System.Object>  
 [<span data-ttu-id="3c947-113">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c947-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="3c947-114">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="3c947-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="3c947-115">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="3c947-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="3c947-116">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="3c947-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="3c947-117">Conversioni di matrice</span><span class="sxs-lookup"><span data-stu-id="3c947-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [<span data-ttu-id="3c947-118">Strutture</span><span class="sxs-lookup"><span data-stu-id="3c947-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="3c947-119">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="3c947-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="3c947-120">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="3c947-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)

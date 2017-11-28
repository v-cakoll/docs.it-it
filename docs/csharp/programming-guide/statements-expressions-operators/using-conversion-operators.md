---
title: Utilizzo degli operatori di conversione (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5a43332df795d853c3060a604360adeaea5e3fd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-conversion-operators-c-programming-guide"></a><span data-ttu-id="d263d-102">Utilizzo degli operatori di conversione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d263d-102">Using Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="d263d-103">È possibile utilizzare gli operatori di conversione `implicit`, che sono più facili da utilizzare, o gli operatori di conversione `explicit`, per indicare chiaramente a chiunque legga il codice che si sta convertendo un tipo.</span><span class="sxs-lookup"><span data-stu-id="d263d-103">You can use `implicit` conversion operators, which are easier to use, or `explicit` conversion operators, which clearly indicate to anyone reading the code that you're converting a type.</span></span> <span data-ttu-id="d263d-104">In questo argomento vengono illustrati entrambi i tipi di operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="d263d-104">This topic demonstrates both types of conversion operator.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d263d-105">Per informazioni sulle conversioni di tipi semplici, vedere [Procedura: convertire una stringa in un numero](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [Procedura: convertire una matrice di byte in un Integer](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Procedura: eseguire la conversione tra stringhe esadecimali e tipi numerici](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) o <xref:System.Convert>.</span><span class="sxs-lookup"><span data-stu-id="d263d-105">For information about simple type conversions, see [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), or <xref:System.Convert>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d263d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d263d-106">Example</span></span>  
 <span data-ttu-id="d263d-107">Questo è un esempio di un operatore di conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="d263d-107">This is an example of an explicit conversion operator.</span></span> <span data-ttu-id="d263d-108">Questo operatore esegue la conversione dal tipo <xref:System.Byte> in un tipo valore denominato `Digit`.</span><span class="sxs-lookup"><span data-stu-id="d263d-108">This operator converts from the type <xref:System.Byte> to a value type called `Digit`.</span></span> <span data-ttu-id="d263d-109">Poiché non tutti i byte possono essere convertiti in una cifra, la conversione è esplicita, ovvero è necessario utilizzare un cast, come illustrato nel metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="d263d-109">Because not all bytes can be converted to a digit, the conversion is explicit, meaning that a cast must be used, as shown in the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="d263d-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="d263d-110">Example</span></span>  
 <span data-ttu-id="d263d-111">In questo esempio viene illustrato un operatore di conversione implicita, definendo un operatore di conversione che annulla quello che è stato fatto nell'esempio precedente: esegue la conversione da una classe di valori denominata `Digit` nel tipo integrale <xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="d263d-111">This example demonstrates an implicit conversion operator by defining a conversion operator that undoes what the previous example did: it converts from a value class called `Digit` to the integral <xref:System.Byte> type.</span></span> <span data-ttu-id="d263d-112">Poiché qualsiasi cifra può essere convertita in un <xref:System.Byte>, non è necessario imporre agli utenti l'uso di una conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="d263d-112">Because any digit can be converted to a <xref:System.Byte>, there's no need to force users to be explicit about the conversion.</span></span>  
  
 [!code-csharp[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d263d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d263d-113">See Also</span></span>  
 [<span data-ttu-id="d263d-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d263d-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d263d-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d263d-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d263d-116">Operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="d263d-116">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
 [<span data-ttu-id="d263d-117">is</span><span class="sxs-lookup"><span data-stu-id="d263d-117">is</span></span>](../../../csharp/language-reference/keywords/is.md)

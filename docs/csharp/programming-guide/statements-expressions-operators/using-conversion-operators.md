---
title: Uso degli operatori di conversione - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
ms.openlocfilehash: 888339661ba1cb2e0b702f284d9f27b3217e74c1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973158"
---
# <a name="using-conversion-operators-c-programming-guide"></a><span data-ttu-id="b8180-102">Utilizzo degli operatori di conversione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b8180-102">Using Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="b8180-103">È possibile utilizzare gli operatori di conversione `implicit`, che sono più facili da utilizzare, o gli operatori di conversione `explicit`, per indicare chiaramente a chiunque legga il codice che si sta convertendo un tipo.</span><span class="sxs-lookup"><span data-stu-id="b8180-103">You can use `implicit` conversion operators, which are easier to use, or `explicit` conversion operators, which clearly indicate to anyone reading the code that you're converting a type.</span></span> <span data-ttu-id="b8180-104">In questo argomento vengono illustrati entrambi i tipi di operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="b8180-104">This topic demonstrates both types of conversion operator.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8180-105">Per informazioni sulle conversioni di tipi semplici, vedere [Procedura: Convertire una stringa in un numero](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [Procedura: Convertire una matrice di byte in un Integer](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Procedura: Eseguire la conversione tra stringhe esadecimali e tipi numerici](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) o <xref:System.Convert>.</span><span class="sxs-lookup"><span data-stu-id="b8180-105">For information about simple type conversions, see [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), or <xref:System.Convert>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8180-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8180-106">Example</span></span>  
 <span data-ttu-id="b8180-107">Questo è un esempio di un operatore di conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="b8180-107">This is an example of an explicit conversion operator.</span></span> <span data-ttu-id="b8180-108">Questo operatore esegue la conversione dal tipo <xref:System.Byte> in un tipo valore denominato `Digit`.</span><span class="sxs-lookup"><span data-stu-id="b8180-108">This operator converts from the type <xref:System.Byte> to a value type called `Digit`.</span></span> <span data-ttu-id="b8180-109">Poiché non tutti i byte possono essere convertiti in una cifra, la conversione è esplicita, ovvero è necessario utilizzare un cast, come illustrato nel metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="b8180-109">Because not all bytes can be converted to a digit, the conversion is explicit, meaning that a cast must be used, as shown in the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideStatements#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#11)]  
  
## <a name="example"></a><span data-ttu-id="b8180-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8180-110">Example</span></span>  
 <span data-ttu-id="b8180-111">In questo esempio viene illustrato un operatore di conversione implicita, definendo un operatore di conversione che annulla quello che è stato fatto nell'esempio precedente: esegue la conversione da una classe di valori denominata `Digit` nel tipo integrale <xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="b8180-111">This example demonstrates an implicit conversion operator by defining a conversion operator that undoes what the previous example did: it converts from a value class called `Digit` to the integral <xref:System.Byte> type.</span></span> <span data-ttu-id="b8180-112">Poiché qualsiasi cifra può essere convertita in un <xref:System.Byte>, non è necessario imporre agli utenti l'uso di una conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="b8180-112">Because any digit can be converted to a <xref:System.Byte>, there's no need to force users to be explicit about the conversion.</span></span>  
  
 [!code-csharp[csProgGuideStatements#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#12)]  
  
## <a name="see-also"></a><span data-ttu-id="b8180-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8180-113">See also</span></span>

- [<span data-ttu-id="b8180-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b8180-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="b8180-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b8180-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="b8180-116">Operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="b8180-116">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
- [<span data-ttu-id="b8180-117">is</span><span class="sxs-lookup"><span data-stu-id="b8180-117">is</span></span>](../../../csharp/language-reference/keywords/is.md)

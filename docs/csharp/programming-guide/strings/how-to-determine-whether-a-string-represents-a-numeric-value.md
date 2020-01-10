---
title: Come determinare se una stringa rappresenta una guida per la C# programmazione di valori numerici
ms.date: 07/20/2015
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
ms.openlocfilehash: bd89024a0a9bd62927d2d5e0eda248b57bb7d21d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711922"
---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a><span data-ttu-id="e5876-102">Come determinare se una stringa rappresenta un valore numerico (C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="e5876-102">How to determine whether a string represents a numeric value (C# Programming Guide)</span></span>
<span data-ttu-id="e5876-103">Per determinare se una stringa è una rappresentazione valida di un tipo numerico specificato, usare il metodo statico `TryParse` che viene implementato da tutti i tipi numerici primitivi e anche da tipi quali <xref:System.DateTime> e <xref:System.Net.IPAddress>.</span><span class="sxs-lookup"><span data-stu-id="e5876-103">To determine whether a string is a valid representation of a specified numeric type, use the static `TryParse` method that is implemented by all primitive numeric types and also by types such as <xref:System.DateTime> and <xref:System.Net.IPAddress>.</span></span> <span data-ttu-id="e5876-104">L'esempio seguente illustra come determinare se "108" è un tipo [int](../../language-reference/builtin-types/integral-numeric-types.md) valido.</span><span class="sxs-lookup"><span data-stu-id="e5876-104">The following example shows how to determine whether "108" is a valid [int](../../language-reference/builtin-types/integral-numeric-types.md).</span></span>  
  
```csharp  
int i = 0;   
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 <span data-ttu-id="e5876-105">Se la stringa contiene caratteri non numerici o se il valore numerico è o troppo grande o troppo piccolo per un determinato tipo specificato, `TryParse` restituisce false e imposta il parametro out su zero.</span><span class="sxs-lookup"><span data-stu-id="e5876-105">If the string contains nonnumeric characters or the numeric value is too large or too small for the particular type you have specified, `TryParse` returns false and sets the out parameter to zero.</span></span> <span data-ttu-id="e5876-106">In caso contrario, restituisce true e imposta il parametro out sul valore numerico della stringa.</span><span class="sxs-lookup"><span data-stu-id="e5876-106">Otherwise, it returns true and sets the out parameter to the numeric value of the string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5876-107">È possibile che una stringa contenga solo caratteri numeri e che non sia tuttavia valida per il tipo per il quale si usa il metodo `TryParse`.</span><span class="sxs-lookup"><span data-stu-id="e5876-107">A string may contain only numeric characters and still not be valid for the type whose `TryParse` method that you use.</span></span> <span data-ttu-id="e5876-108">Ad esempio, "256" non è un valore valido per `byte`, ma lo è per `int`.</span><span class="sxs-lookup"><span data-stu-id="e5876-108">For example, "256" is not a valid value for `byte` but it is valid for `int`.</span></span> <span data-ttu-id="e5876-109">"98,6" non è un valore valido per `int` ma è un valore `decimal` valido.</span><span class="sxs-lookup"><span data-stu-id="e5876-109">"98.6" is not a valid value for `int` but it is a valid `decimal`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5876-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="e5876-110">Example</span></span>  
 <span data-ttu-id="e5876-111">Gli esempi seguenti illustrano come usare `TryParse` con rappresentazioni di stringa di valori `long`, `byte` e `decimal`.</span><span class="sxs-lookup"><span data-stu-id="e5876-111">The following examples show how to use `TryParse` with string representations of `long`, `byte`, and `decimal` values.</span></span>  
  
 [!code-csharp[csProgGuideStrings#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#14)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e5876-112">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="e5876-112">Robust Programming</span></span>  
 <span data-ttu-id="e5876-113">I tipi numerici primitivi implementano anche il metodo statico `Parse`, che genera un'eccezione se la stringa non è un numero valido.</span><span class="sxs-lookup"><span data-stu-id="e5876-113">Primitive numeric types also implement the `Parse` static method, which throws an exception if the string is not a valid number.</span></span> <span data-ttu-id="e5876-114">Il metodo `TryParse` è in genere più efficiente in quanto restituisce false se il numero non è valido.</span><span class="sxs-lookup"><span data-stu-id="e5876-114">`TryParse` is generally more efficient because it just returns false if the number is not valid.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e5876-115">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e5876-115">.NET Framework Security</span></span>  
 <span data-ttu-id="e5876-116">Usare sempre i metodi `TryParse` o `Parse` per convalidare l'input dell'utente da controlli, come caselle di testo e caselle combinate.</span><span class="sxs-lookup"><span data-stu-id="e5876-116">Always use the `TryParse` or `Parse` methods to validate user input from controls such as text boxes and combo boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5876-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5876-117">See also</span></span>

- [<span data-ttu-id="e5876-118">Come convertire una matrice di byte in un valore int</span><span class="sxs-lookup"><span data-stu-id="e5876-118">How to convert a byte array to an int</span></span>](../types/how-to-convert-a-byte-array-to-an-int.md)
- [<span data-ttu-id="e5876-119">Come convertire una stringa in un numero</span><span class="sxs-lookup"><span data-stu-id="e5876-119">How to convert a string to a number</span></span>](../types/how-to-convert-a-string-to-a-number.md)
- [<span data-ttu-id="e5876-120">Come eseguire la conversione tra stringhe esadecimali e tipi numerici</span><span class="sxs-lookup"><span data-stu-id="e5876-120">How to convert between hexadecimal strings and numeric types</span></span>](../types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)
- [<span data-ttu-id="e5876-121">Analisi di stringhe numeriche</span><span class="sxs-lookup"><span data-stu-id="e5876-121">Parsing Numeric Strings</span></span>](../../../standard/base-types/parsing-numeric.md)
- [<span data-ttu-id="e5876-122">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="e5876-122">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)

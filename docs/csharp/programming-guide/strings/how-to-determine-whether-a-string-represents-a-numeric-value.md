---
title: 'Procedura: determinare se una stringa rappresenta un valore numerico (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d2f89f4a4771625389a04f5c92829c91d66eb207
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a><span data-ttu-id="fd161-102">Procedura: determinare se una stringa rappresenta un valore numerico (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="fd161-102">How to: Determine Whether a String Represents a Numeric Value (C# Programming Guide)</span></span>
<span data-ttu-id="fd161-103">Per determinare se una stringa è una rappresentazione valida di un tipo numerico specificato, usare il metodo statico `TryParse` che viene implementato da tutti i tipi numerici primitivi e anche da tipi quali <xref:System.DateTime> e <xref:System.Net.IPAddress>.</span><span class="sxs-lookup"><span data-stu-id="fd161-103">To determine whether a string is a valid representation of a specified numeric type, use the static `TryParse` method that is implemented by all primitive numeric types and also by types such as <xref:System.DateTime> and <xref:System.Net.IPAddress>.</span></span> <span data-ttu-id="fd161-104">L'esempio seguente illustra come determinare se "108" è un tipo [int](../../../csharp/language-reference/keywords/int.md) valido.</span><span class="sxs-lookup"><span data-stu-id="fd161-104">The following example shows how to determine whether "108" is a valid [int](../../../csharp/language-reference/keywords/int.md).</span></span>  
  
```  
int i = 0;   
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 <span data-ttu-id="fd161-105">Se la stringa contiene caratteri non numerici o se il valore numerico è o troppo grande o troppo piccolo per un determinato tipo specificato, `TryParse` restituisce false e imposta il parametro out su zero.</span><span class="sxs-lookup"><span data-stu-id="fd161-105">If the string contains nonnumeric characters or the numeric value is too large or too small for the particular type you have specified, `TryParse` returns false and sets the out parameter to zero.</span></span> <span data-ttu-id="fd161-106">In caso contrario, restituisce true e imposta il parametro out sul valore numerico della stringa.</span><span class="sxs-lookup"><span data-stu-id="fd161-106">Otherwise, it returns true and sets the out parameter to the numeric value of the string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd161-107">È possibile che una stringa contenga solo caratteri numeri e che non sia tuttavia valida per il tipo per il quale si usa il metodo `TryParse`.</span><span class="sxs-lookup"><span data-stu-id="fd161-107">A string may contain only numeric characters and still not be valid for the type whose `TryParse` method that you use.</span></span> <span data-ttu-id="fd161-108">Ad esempio, "256" non è un valore valido per `byte`, ma lo è per `int`.</span><span class="sxs-lookup"><span data-stu-id="fd161-108">For example, "256" is not a valid value for `byte` but it is valid for `int`.</span></span> <span data-ttu-id="fd161-109">"98,6" non è un valore valido per `int` ma è un valore `decimal` valido.</span><span class="sxs-lookup"><span data-stu-id="fd161-109">"98.6" is not a valid value for `int` but it is a valid `decimal`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd161-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd161-110">Example</span></span>  
 <span data-ttu-id="fd161-111">Gli esempi seguenti illustrano come usare `TryParse` con rappresentazioni di stringa di valori `long`, `byte` e `decimal`.</span><span class="sxs-lookup"><span data-stu-id="fd161-111">The following examples show how to use `TryParse` with string representations of `long`, `byte`, and `decimal` values.</span></span>  
  
 <span data-ttu-id="fd161-112">[!code-cs[csProgGuideStrings#14](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-determine-whether-a-string-represents-a-numeric-value_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fd161-112">[!code-cs[csProgGuideStrings#14](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-determine-whether-a-string-represents-a-numeric-value_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fd161-113">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="fd161-113">Robust Programming</span></span>  
 <span data-ttu-id="fd161-114">I tipi numerici primitivi implementano anche il metodo statico `Parse`, che genera un'eccezione se la stringa non è un numero valido.</span><span class="sxs-lookup"><span data-stu-id="fd161-114">Primitive numeric types also implement the `Parse` static method, which throws an exception if the string is not a valid number.</span></span> <span data-ttu-id="fd161-115">Il metodo `TryParse` è in genere più efficiente in quanto restituisce false se il numero non è valido.</span><span class="sxs-lookup"><span data-stu-id="fd161-115">`TryParse` is generally more efficient because it just returns false if the number is not valid.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="fd161-116">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fd161-116">.NET Framework Security</span></span>  
 <span data-ttu-id="fd161-117">Usare sempre i metodi `TryParse` o `Parse` per convalidare l'input dell'utente da controlli, come caselle di testo e caselle combinate.</span><span class="sxs-lookup"><span data-stu-id="fd161-117">Always use the `TryParse` or `Parse` methods to validate user input from controls such as text boxes and combo boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd161-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd161-118">See Also</span></span>  
 <span data-ttu-id="fd161-119">[Procedura: Convertire una matrice di byte in un Integer](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md) </span><span class="sxs-lookup"><span data-stu-id="fd161-119">[How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md) </span></span>  
 <span data-ttu-id="fd161-120">[Procedura: Convertire una stringa in un numero](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) </span><span class="sxs-lookup"><span data-stu-id="fd161-120">[How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) </span></span>  
 <span data-ttu-id="fd161-121">[Procedura: Eseguire la conversione tra stringhe esadecimali e tipi numerici](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) </span><span class="sxs-lookup"><span data-stu-id="fd161-121">[How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) </span></span>  
 <span data-ttu-id="fd161-122">[Analisi di stringhe numeriche](../../../standard/base-types/parsing-numeric.md) </span><span class="sxs-lookup"><span data-stu-id="fd161-122">[Parsing Numeric Strings](../../../standard/base-types/parsing-numeric.md) </span></span>  
 [<span data-ttu-id="fd161-123">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="fd161-123">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)


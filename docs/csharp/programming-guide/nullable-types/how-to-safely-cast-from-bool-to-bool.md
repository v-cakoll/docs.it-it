---
title: 'Procedura: eseguire il cast sicuro da bool? a bool (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
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
ms.openlocfilehash: c8a3dc3280b7dca802b327d9454c7f0ba9ed44be
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a><span data-ttu-id="324d7-102">Procedura: eseguire il cast sicuro da bool? a bool (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="324d7-102">How to: Safely Cast from bool? to bool (C# Programming Guide)</span></span>
<span data-ttu-id="324d7-103">Il tipo nullable `bool?` può contenere tre valori diversi: `true`, `false` e `null`.</span><span class="sxs-lookup"><span data-stu-id="324d7-103">The `bool?` nullable type can contain three different values: `true`, `false`, and `null`.</span></span> <span data-ttu-id="324d7-104">Pertanto il tipo `bool?` non può essere usato in istruzioni condizionali, ad esempio con `if`, `for` o `while`.</span><span class="sxs-lookup"><span data-stu-id="324d7-104">Therefore, the `bool?` type cannot be used in conditionals such as with `if`, `for`, or `while`.</span></span> <span data-ttu-id="324d7-105">Il codice seguente, ad esempio, causa un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="324d7-105">For example, the following code causes a compiler error.</span></span>  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 <span data-ttu-id="324d7-106">Questo codice non è consentito perché non è chiaro il significato di `null` nel contesto di un'istruzione condizionale.</span><span class="sxs-lookup"><span data-stu-id="324d7-106">This is not allowed because it is unclear what `null` means in the context of a conditional.</span></span> <span data-ttu-id="324d7-107">Prima di usare un tipo `bool?` in un'istruzione condizionale, verificare che il valore della proprietà <xref:System.Nullable%601.HasValue%2A> del tipo non sia `null`, quindi eseguire il cast a `bool`.</span><span class="sxs-lookup"><span data-stu-id="324d7-107">To use a `bool?` in a conditional statement, first check its <xref:System.Nullable%601.HasValue%2A> property to ensure that its value is not `null`, and then cast it to `bool`.</span></span> <span data-ttu-id="324d7-108">Per altre informazioni, vedere [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="324d7-108">For more information, see [bool](../../../csharp/language-reference/keywords/bool.md).</span></span> <span data-ttu-id="324d7-109">Se si esegue il cast per un `bool?` con valore `null`, nel testo condizionale viene aggiunta l'eccezione <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="324d7-109">If you perform the cast on a `bool?` with a value of `null`, a <xref:System.InvalidOperationException> will be thrown in the conditional test.</span></span> <span data-ttu-id="324d7-110">L'esempio seguente visualizza un modo sicuro per eseguire il cast da `bool?` a `bool`:</span><span class="sxs-lookup"><span data-stu-id="324d7-110">The following example shows one way to safely cast from `bool?` to `bool`:</span></span>  
  
## <a name="example"></a><span data-ttu-id="324d7-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="324d7-111">Example</span></span>  
  
```csharp  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="324d7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="324d7-112">See Also</span></span>  
 <span data-ttu-id="324d7-113">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="324d7-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="324d7-114">[Parole chiave letterali](../../../csharp/language-reference/keywords/literal-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="324d7-114">[Literal Keywords](../../../csharp/language-reference/keywords/literal-keywords.md) </span></span>  
 <span data-ttu-id="324d7-115">[Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="324d7-115">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="324d7-116">?? (operatore)</span><span class="sxs-lookup"><span data-stu-id="324d7-116">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)


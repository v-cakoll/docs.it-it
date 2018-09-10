---
title: typeof (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 2493e78fd0782eebee17afd979e1c429339d0a3f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486805"
---
# <a name="typeof-c-reference"></a><span data-ttu-id="df742-102">typeof (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="df742-102">typeof (C# Reference)</span></span>
<span data-ttu-id="df742-103">Viene usato per ottenere l'oggetto `System.Type` per un tipo.</span><span class="sxs-lookup"><span data-stu-id="df742-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="df742-104">L'espressione `typeof` assume il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="df742-104">A `typeof` expression takes the following form:</span></span>  
  
```csharp  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="df742-105">Note</span><span class="sxs-lookup"><span data-stu-id="df742-105">Remarks</span></span>  
 <span data-ttu-id="df742-106">Per ottenere il tipo di runtime di un'espressione, è possibile usare il metodo di .NET Framework <xref:System.Object.GetType%2A>, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="df742-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```csharp  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="df742-107">Non è possibile sottoporre l'operatore `typeof` a overload.</span><span class="sxs-lookup"><span data-stu-id="df742-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="df742-108">L'operatore `typeof` può essere usato anche su tipi generici aperti.</span><span class="sxs-lookup"><span data-stu-id="df742-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="df742-109">I tipi con più di un parametro di tipo devono avere il numero appropriato di virgole nella specifica.</span><span class="sxs-lookup"><span data-stu-id="df742-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="df742-110">Nell'esempio seguente viene illustrato come determinare se il tipo restituito di un metodo è un elemento <xref:System.Collections.Generic.IEnumerable%601> generico.</span><span class="sxs-lookup"><span data-stu-id="df742-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="df742-111"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> restituirà `null` se il tipo restituito non è un tipo generico <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="df742-111"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> will return `null` if the return type is not an <xref:System.Collections.Generic.IEnumerable%601> generic type.</span></span>
  
 [!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]   
  
## <a name="example"></a><span data-ttu-id="df742-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="df742-112">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="df742-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="df742-113">Example</span></span>  
 <span data-ttu-id="df742-114">Questo esempio usa il metodo <xref:System.Object.GetType%2A> per determinare il tipo usato per contenere il risultato di un calcolo numerico.</span><span class="sxs-lookup"><span data-stu-id="df742-114">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="df742-115">Ciò dipende dai requisiti di archiviazione del numero risultante.</span><span class="sxs-lookup"><span data-stu-id="df742-115">This depends on the storage requirements of the resulting number.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="df742-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="df742-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df742-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df742-117">See Also</span></span>

- <xref:System.Type?displayProperty=nameWithType>  
- [<span data-ttu-id="df742-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="df742-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="df742-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="df742-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="df742-120">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="df742-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="df742-121">is</span><span class="sxs-lookup"><span data-stu-id="df742-121">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
- [<span data-ttu-id="df742-122">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="df742-122">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

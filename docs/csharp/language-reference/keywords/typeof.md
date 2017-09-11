---
title: typeof (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeof
- typeof_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
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
ms.openlocfilehash: fdb335e44a5a3634520d3a86495a4508597b4f70
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="typeof-c-reference"></a><span data-ttu-id="9f0b8-102">typeof (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="9f0b8-102">typeof (C# Reference)</span></span>
<span data-ttu-id="9f0b8-103">Viene usato per ottenere l'oggetto `System.Type` per un tipo.</span><span class="sxs-lookup"><span data-stu-id="9f0b8-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="9f0b8-104">L'espressione `typeof` assume il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="9f0b8-104">A `typeof` expression takes the following form:</span></span>  
  
```  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="9f0b8-105">Note</span><span class="sxs-lookup"><span data-stu-id="9f0b8-105">Remarks</span></span>  
 <span data-ttu-id="9f0b8-106">Per ottenere il tipo di runtime di un'espressione, è possibile usare il metodo di .NET Framework <xref:System.Object.GetType%2A>, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="9f0b8-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="9f0b8-107">Non è possibile sottoporre l'operatore `typeof` a overload.</span><span class="sxs-lookup"><span data-stu-id="9f0b8-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="9f0b8-108">L'operatore `typeof` può essere usato anche su tipi generici aperti.</span><span class="sxs-lookup"><span data-stu-id="9f0b8-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="9f0b8-109">I tipi con più di un parametro di tipo devono avere il numero appropriato di virgole nella specifica.</span><span class="sxs-lookup"><span data-stu-id="9f0b8-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="9f0b8-110">Nell'esempio seguente viene illustrato come determinare se il tipo restituito di un metodo è un elemento <xref:System.Collections.Generic.IEnumerable%601> generico.</span><span class="sxs-lookup"><span data-stu-id="9f0b8-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="9f0b8-111">Si supponga che il metodo sia un'istanza di tipo MethodInfo:</span><span class="sxs-lookup"><span data-stu-id="9f0b8-111">Assume that method is an instance of a MethodInfo type:</span></span>  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a><span data-ttu-id="9f0b8-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f0b8-112">Example</span></span>  
 <span data-ttu-id="9f0b8-113">[!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9f0b8-113">[!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f0b8-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f0b8-114">Example</span></span>  
 <span data-ttu-id="9f0b8-115">Questo esempio usa il metodo <xref:System.Object.GetType%2A> per determinare il tipo usato per contenere il risultato di un calcolo numerico.</span><span class="sxs-lookup"><span data-stu-id="9f0b8-115">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="9f0b8-116">Ciò dipende dai requisiti di archiviazione del numero risultante.</span><span class="sxs-lookup"><span data-stu-id="9f0b8-116">This depends on the storage requirements of the resulting number.</span></span>  
  
 <span data-ttu-id="9f0b8-117">[!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9f0b8-117">[!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9f0b8-118">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="9f0b8-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9f0b8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f0b8-119">See Also</span></span>  
 <span data-ttu-id="9f0b8-120"><xref:System.Type?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9f0b8-120"><xref:System.Type?displayProperty=fullName></span></span>   
 <span data-ttu-id="9f0b8-121">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9f0b8-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9f0b8-122">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9f0b8-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9f0b8-123">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="9f0b8-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="9f0b8-124">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="9f0b8-124">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 [<span data-ttu-id="9f0b8-125">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="9f0b8-125">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)


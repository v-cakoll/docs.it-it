---
title: 'Procedura: utilizzare l''overload degli operatori per creare una classe di numeri complessi (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- complex numbers [C#]
- classes [C#], operator overloading
- operator overloading [C#], complex numbers
- operator overloading [C#], using to create classes
- operators [C#], overloading to create a complex number class
ms.assetid: c9b8d982-5112-413f-bae3-b42ae3248ddf
caps.latest.revision: 15
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
ms.openlocfilehash: 2ce629320744d46787aaabba48740f05c917fdcb
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-operator-overloading-to-create-a-complex-number-class-c-programming-guide"></a><span data-ttu-id="0180f-102">Procedura: utilizzare l'overload degli operatori per creare una classe di numeri complessi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="0180f-102">How to: Use Operator Overloading to Create a Complex Number Class (C# Programming Guide)</span></span>
<span data-ttu-id="0180f-103">Questo esempio mostra come usare l'overload degli operatori per creare una classe di numeri complessi `Complex` che definisce un'addizione complessa.</span><span class="sxs-lookup"><span data-stu-id="0180f-103">This example shows how you can use operator overloading to create a complex number class `Complex` that defines complex addition.</span></span> <span data-ttu-id="0180f-104">Il programma mostra la parte reale e quella immaginaria dei numeri e il risultato dell'addizione usando un override del metodo `ToString`.</span><span class="sxs-lookup"><span data-stu-id="0180f-104">The program displays the imaginary and the real parts of the numbers and the addition result using an override of the `ToString` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0180f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="0180f-105">Example</span></span>  
 <span data-ttu-id="0180f-106">[!code-cs[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-operator-overloading-to-create-a-complex-number-class_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0180f-106">[!code-cs[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-operator-overloading-to-create-a-complex-number-class_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0180f-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0180f-107">See Also</span></span>  
 <span data-ttu-id="0180f-108">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0180f-108">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0180f-109">[Operatori C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="0180f-109">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="0180f-110">[operator (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md) </span><span class="sxs-lookup"><span data-stu-id="0180f-110">[operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md) </span></span>  
 <span data-ttu-id="0180f-111">[Why are overloaded operators always static in C#?](http://go.microsoft.com/fwlink/?LinkId=112383) (Perché gli operatori sottoposti a overload sono sempre statici in C#?)</span><span class="sxs-lookup"><span data-stu-id="0180f-111">[Why are overloaded operators always static in C#?](http://go.microsoft.com/fwlink/?LinkId=112383)</span></span>


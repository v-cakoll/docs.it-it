---
title: 'Procedura: utilizzare l''overload degli operatori per creare una classe di numeri complessi (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- complex numbers [C#]
- classes [C#], operator overloading
- operator overloading [C#], complex numbers
- operator overloading [C#], using to create classes
- operators [C#], overloading to create a complex number class
ms.assetid: c9b8d982-5112-413f-bae3-b42ae3248ddf
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2053684a9b20c3ec8f4d8ac275832516b3f2c265
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-operator-overloading-to-create-a-complex-number-class-c-programming-guide"></a><span data-ttu-id="5eb57-102">Procedura: utilizzare l'overload degli operatori per creare una classe di numeri complessi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="5eb57-102">How to: Use Operator Overloading to Create a Complex Number Class (C# Programming Guide)</span></span>
<span data-ttu-id="5eb57-103">Questo esempio mostra come usare l'overload degli operatori per creare una classe di numeri complessi `Complex` che definisce un'addizione complessa.</span><span class="sxs-lookup"><span data-stu-id="5eb57-103">This example shows how you can use operator overloading to create a complex number class `Complex` that defines complex addition.</span></span> <span data-ttu-id="5eb57-104">Il programma mostra la parte reale e quella immaginaria dei numeri e il risultato dell'addizione usando un override del metodo `ToString`.</span><span class="sxs-lookup"><span data-stu-id="5eb57-104">The program displays the imaginary and the real parts of the numbers and the addition result using an override of the `ToString` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5eb57-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="5eb57-105">Example</span></span>  
 [!code-csharp[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-operator-overloading-to-create-a-complex-number-class_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="5eb57-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5eb57-106">See Also</span></span>  
 [<span data-ttu-id="5eb57-107">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5eb57-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5eb57-108">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="5eb57-108">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="5eb57-109">operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5eb57-109">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 <span data-ttu-id="5eb57-110">[Why are overloaded operators always static in C#?](http://go.microsoft.com/fwlink/?LinkId=112383) (Perché gli operatori sottoposti a overload sono sempre statici in C#?)</span><span class="sxs-lookup"><span data-stu-id="5eb57-110">[Why are overloaded operators always static in C#?](http://go.microsoft.com/fwlink/?LinkId=112383)</span></span>

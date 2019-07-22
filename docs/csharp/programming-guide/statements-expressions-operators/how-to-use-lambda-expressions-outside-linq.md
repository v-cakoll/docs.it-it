---
title: 'Procedura: Usare espressioni lambda al di fuori di LINQ - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: 947f80fdaa90b6b5f8176aac01dd8e3cf40e38cc
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363780"
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a><span data-ttu-id="5e7e5-102">Procedura: Usare espressioni lambda al di fuori di LINQ (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="5e7e5-102">How to: Use Lambda Expressions Outside LINQ (C# Programming Guide)</span></span>
<span data-ttu-id="5e7e5-103">Le espressioni lambda non sono limitate alle query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e7e5-103">Lambda expressions are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="5e7e5-104">È possibile usarle dove è previsto un valore delegate, ovvero dove può essere usato un metodo anonimo.</span><span class="sxs-lookup"><span data-stu-id="5e7e5-104">You can use them anywhere a delegate value is expected, that is, wherever an anonymous method can be used.</span></span> <span data-ttu-id="5e7e5-105">Nell'esempio seguente viene illustrato come usare un'espressione lambda in un gestore eventi Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5e7e5-105">The following example shows how to use a lambda expression in a Windows Forms event handler.</span></span> <span data-ttu-id="5e7e5-106">Si noti che i tipi degli input (<xref:System.Object> e <xref:System.Windows.Forms.MouseEventArgs>) vengono derivati tramite inferenza dal compilatore e non devono essere forniti in modo esplicito nei parametri di input dell'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="5e7e5-106">Notice that the types of the inputs (<xref:System.Object> and <xref:System.Windows.Forms.MouseEventArgs>) are inferred by the compiler and do not have to be explicitly given in the lambda input parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e7e5-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e7e5-107">Example</span></span>  
  
```csharp  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
       this.Click += (s, e) => { MessageBox.Show(((MouseEventArgs)e).Location.ToString());};  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e7e5-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e7e5-108">See also</span></span>

- [<span data-ttu-id="5e7e5-109">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="5e7e5-109">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="5e7e5-110">Language Integrated Query (LINQ))</span><span class="sxs-lookup"><span data-stu-id="5e7e5-110">Language Integrated Query (LINQ))</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)

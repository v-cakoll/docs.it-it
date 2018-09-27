---
title: 'Procedura: utilizzare espressioni lambda al di fuori di LINQ (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: eb9fea64b8aeb96a880b7e177673c1316b7aa4c1
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44261533"
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a><span data-ttu-id="2f3af-102">Procedura: utilizzare espressioni lambda al di fuori di LINQ (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="2f3af-102">How to: Use Lambda Expressions Outside LINQ (C# Programming Guide)</span></span>
<span data-ttu-id="2f3af-103">Le espressioni lambda non sono limitate alle query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f3af-103">Lambda expressions are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="2f3af-104">È possibile usarle dove è previsto un valore delegate, ovvero dove può essere usato un metodo anonimo.</span><span class="sxs-lookup"><span data-stu-id="2f3af-104">You can use them anywhere a delegate value is expected, that is, wherever an anonymous method can be used.</span></span> <span data-ttu-id="2f3af-105">Nell'esempio seguente viene illustrato come usare un'espressione lambda in un gestore eventi Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2f3af-105">The following example shows how to use a lambda expression in a Windows Forms event handler.</span></span> <span data-ttu-id="2f3af-106">Si noti che i tipi degli input (<xref:System.Object> e <xref:System.Windows.Forms.MouseEventArgs>) vengono derivati tramite inferenza dal compilatore e non devono essere forniti in modo esplicito nei parametri di input dell'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="2f3af-106">Notice that the types of the inputs (<xref:System.Object> and <xref:System.Windows.Forms.MouseEventArgs>) are inferred by the compiler and do not have to be explicitly given in the lambda input parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f3af-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f3af-107">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2f3af-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f3af-108">See Also</span></span>

- [<span data-ttu-id="2f3af-109">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="2f3af-109">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
- [<span data-ttu-id="2f3af-110">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="2f3af-110">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
- [<span data-ttu-id="2f3af-111">Language Integrated Query (LINQ))</span><span class="sxs-lookup"><span data-stu-id="2f3af-111">Language Integrated Query (LINQ))</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)

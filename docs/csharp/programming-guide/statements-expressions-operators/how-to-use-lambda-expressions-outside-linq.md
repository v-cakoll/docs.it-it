---
title: 'Procedura: Usare espressioni lambda al di fuori di LINQ - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: c66dea393ad2351402f54b2391d424701208eba2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619821"
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a>Procedura: Usare espressioni lambda al di fuori di LINQ (Guida per programmatori C#)
Le espressioni lambda non sono limitate alle query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. È possibile usarle dove è previsto un valore delegate, ovvero dove può essere usato un metodo anonimo. Nell'esempio seguente viene illustrato come usare un'espressione lambda in un gestore eventi Windows Forms. Si noti che i tipi degli input (<xref:System.Object> e <xref:System.Windows.Forms.MouseEventArgs>) vengono derivati tramite inferenza dal compilatore e non devono essere forniti in modo esplicito nei parametri di input dell'espressione lambda.  
  
## <a name="example"></a>Esempio  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [Metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
- [Language Integrated Query (LINQ))](../../../csharp/programming-guide/concepts/linq/index.md)

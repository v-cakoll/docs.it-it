---
title: 'Procedura: utilizzare espressioni lambda al di fuori di LINQ (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: a7b7d25adab7ce1fc777b3bdbe581666ab952413
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33328955"
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a>Procedura: utilizzare espressioni lambda al di fuori di LINQ (Guida per programmatori C#)
Le espressioni lambda non sono limitate alle query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. È possibile usarle dove è previsto un valore delegate, ovvero dove può essere usato un metodo anonimo. Nell'esempio seguente viene illustrato come usare un'espressione lambda in un gestore eventi Windows Forms. Si noti che i tipi degli input (<xref:System.Object> e <xref:System.Windows.Forms.MouseEventArgs>) vengono derivati tramite inferenza dal compilatore e non devono essere forniti in modo esplicito nei parametri di input dell'espressione lambda.  
  
## <a name="example"></a>Esempio  
  
```  
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
 [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [Metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)

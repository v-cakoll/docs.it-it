---
title: Uso della varianza nei delegati (C#)
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 980caf8d5e4699115d203a89fab7994d18cc1707
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168353"
---
# <a name="using-variance-in-delegates-c"></a>Uso della varianza nei delegati (C#)
Quando si assegna un metodo a un delegato, *covarianza* e *controvarianza* offrono flessibilità per la corrispondenza di un tipo delegato con una firma di metodo. La covarianza consente a un metodo di avere un tipo restituito più derivato di quello definito nel delegato. La controvarianza consente un metodo con tipi di parametro meno derivati rispetto a quelli del tipo delegato.  
  
## <a name="example-1-covariance"></a>Esempio 1: Covarianza  
  
### <a name="description"></a>DESCRIZIONE  
 In questo esempio viene illustrato in che modo si possono usare i delegati con i metodi che hanno tipi restituiti derivati dal tipo restituito nella firma del delegato. Il tipo di dati restituito da `DogsHandler` è di tipo `Dogs`, che deriva dal tipo `Mammals` definito nel delegato.  
  
### <a name="code"></a>Codice  
  
```csharp  
class Mammals {}  
class Dogs : Mammals {}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a>Esempio 2: Controvarianza  
  
### <a name="description"></a>DESCRIZIONE

In questo esempio viene illustrato in che modo si possono usare i delegati con i metodi che hanno parametri i cui tipi rappresentano tipi di base del tipo di parametro della firma del delegato. Con la controvarianza è possibile usare un solo gestore eventi anziché gestori separati. Nell'esempio seguente vengono usati due delegati:

- Un delegato <xref:System.Windows.Forms.KeyEventHandler> che definisce la firma dell'evento [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown). La firma è:

   ```csharp
   public delegate void KeyEventHandler(object sender, KeyEventArgs e)
   ```

- Un delegato <xref:System.Windows.Forms.MouseEventHandler> che definisce la firma dell'evento [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown). La firma è:

   ```csharp
   public delegate void MouseEventHandler(object sender, MouseEventArgs e)
   ```

Nell'esempio viene definito un gestore eventi con un parametro <xref:System.EventArgs> e viene usato per gestire entrambi gli eventi `Button.KeyDown` e `Button.MouseClick`. Ciò è possibile perché <xref:System.EventArgs> è un tipo di base sia di <xref:System.Windows.Forms.KeyEventArgs> che di <xref:System.Windows.Forms.MouseEventArgs>. 
  
### <a name="code"></a>Codice  
  
```csharp  
// Event handler that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method   
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Varianza nei delegati (C#)](./variance-in-delegates.md)
- [Uso della varianza per i delegati generici Func e Action (C#)](./using-variance-for-func-and-action-generic-delegates.md)

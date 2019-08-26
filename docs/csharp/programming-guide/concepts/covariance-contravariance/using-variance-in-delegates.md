---
title: Uso della varianza nei delegati (C#)
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 00e11d4ce755c8c75b73023fec14d95ebc96b4fe
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595271"
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="a5c17-102">Uso della varianza nei delegati (C#)</span><span class="sxs-lookup"><span data-stu-id="a5c17-102">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="a5c17-103">Quando si assegna un metodo a un delegato, *covarianza* e *controvarianza* offrono flessibilità per la corrispondenza di un tipo delegato con una firma di metodo.</span><span class="sxs-lookup"><span data-stu-id="a5c17-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="a5c17-104">La covarianza consente a un metodo di avere un tipo restituito più derivato di quello definito nel delegato.</span><span class="sxs-lookup"><span data-stu-id="a5c17-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="a5c17-105">La controvarianza consente un metodo con tipi di parametro meno derivati rispetto a quelli del tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="a5c17-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="a5c17-106">Esempio 1: Covarianza</span><span class="sxs-lookup"><span data-stu-id="a5c17-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="a5c17-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="a5c17-107">Description</span></span>  
 <span data-ttu-id="a5c17-108">In questo esempio viene illustrato in che modo si possono usare i delegati con i metodi che hanno tipi restituiti derivati dal tipo restituito nella firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="a5c17-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="a5c17-109">Il tipo di dati restituito da `DogsHandler` è di tipo `Dogs`, che deriva dal tipo `Mammals` definito nel delegato.</span><span class="sxs-lookup"><span data-stu-id="a5c17-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a5c17-110">Codice</span><span class="sxs-lookup"><span data-stu-id="a5c17-110">Code</span></span>  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="a5c17-111">Esempio 2: Controvarianza</span><span class="sxs-lookup"><span data-stu-id="a5c17-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="a5c17-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="a5c17-112">Description</span></span>  
 <span data-ttu-id="a5c17-113">In questo esempio viene illustrato in che modo si possono usare i delegati con i metodi che hanno parametri di un tipo che rappresentano tipi di base del tipo di parametro della firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="a5c17-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="a5c17-114">Con la controvarianza è possibile usare un solo gestore eventi anziché gestori separati.</span><span class="sxs-lookup"><span data-stu-id="a5c17-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="a5c17-115">Ad esempio, è possibile creare un gestore eventi che accetta un parametro di input `EventArgs` e usarlo con un evento `Button.MouseClick` che invia un tipo `MouseEventArgs` come parametro e anche con un evento `TextBox.KeyDown` che invia un parametro `KeyEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="a5c17-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a5c17-116">Codice</span><span class="sxs-lookup"><span data-stu-id="a5c17-116">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a5c17-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5c17-117">See also</span></span>

- [<span data-ttu-id="a5c17-118">Varianza nei delegati (C#)</span><span class="sxs-lookup"><span data-stu-id="a5c17-118">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
- [<span data-ttu-id="a5c17-119">Uso della varianza per i delegati generici Func e Action (C#)</span><span class="sxs-lookup"><span data-stu-id="a5c17-119">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)

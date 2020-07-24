---
title: Uso della varianza nei delegati (C#)
description: Informazioni su come usare la varianza nei delegati usando gli esempi di codice di covarianza e controvarianza inclusi.
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 62b0555ee29c5e7d2ba0954a8949d61596122cc7
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105686"
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="81936-103">Uso della varianza nei delegati (C#)</span><span class="sxs-lookup"><span data-stu-id="81936-103">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="81936-104">Quando si assegna un metodo a un delegato, *covarianza* e *controvarianza* offrono flessibilità per la corrispondenza di un tipo delegato con una firma di metodo.</span><span class="sxs-lookup"><span data-stu-id="81936-104">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="81936-105">La covarianza consente a un metodo di avere un tipo restituito più derivato di quello definito nel delegato.</span><span class="sxs-lookup"><span data-stu-id="81936-105">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="81936-106">La controvarianza consente un metodo con tipi di parametro meno derivati rispetto a quelli del tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="81936-106">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="81936-107">Esempio 1: covarianza</span><span class="sxs-lookup"><span data-stu-id="81936-107">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="81936-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81936-108">Description</span></span>  
 <span data-ttu-id="81936-109">In questo esempio viene illustrato in che modo si possono usare i delegati con i metodi che hanno tipi restituiti derivati dal tipo restituito nella firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="81936-109">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="81936-110">Il tipo di dati restituito da `DogsHandler` è di tipo `Dogs`, che deriva dal tipo `Mammals` definito nel delegato.</span><span class="sxs-lookup"><span data-stu-id="81936-110">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="81936-111">Codice</span><span class="sxs-lookup"><span data-stu-id="81936-111">Code</span></span>  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="81936-112">Esempio 2: controvarianza</span><span class="sxs-lookup"><span data-stu-id="81936-112">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="81936-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81936-113">Description</span></span>

<span data-ttu-id="81936-114">In questo esempio viene illustrato in che modo si possono usare i delegati con i metodi che hanno parametri i cui tipi rappresentano tipi di base del tipo di parametro della firma del delegato.</span><span class="sxs-lookup"><span data-stu-id="81936-114">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="81936-115">Con la controvarianza è possibile usare un solo gestore eventi anziché gestori separati.</span><span class="sxs-lookup"><span data-stu-id="81936-115">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="81936-116">Nell'esempio seguente vengono usati due delegati:</span><span class="sxs-lookup"><span data-stu-id="81936-116">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="81936-117">Un delegato <xref:System.Windows.Forms.KeyEventHandler> che definisce la firma dell'evento [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown).</span><span class="sxs-lookup"><span data-stu-id="81936-117">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="81936-118">La firma è:</span><span class="sxs-lookup"><span data-stu-id="81936-118">Its signature is:</span></span>

   ```csharp
   public delegate void KeyEventHandler(object sender, KeyEventArgs e)
   ```

- <span data-ttu-id="81936-119">Un delegato <xref:System.Windows.Forms.MouseEventHandler> che definisce la firma dell'evento [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown).</span><span class="sxs-lookup"><span data-stu-id="81936-119">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="81936-120">La firma è:</span><span class="sxs-lookup"><span data-stu-id="81936-120">Its signature is:</span></span>

   ```csharp
   public delegate void MouseEventHandler(object sender, MouseEventArgs e)
   ```

<span data-ttu-id="81936-121">Nell'esempio viene definito un gestore eventi con un parametro <xref:System.EventArgs> e viene usato per gestire entrambi gli eventi `Button.KeyDown` e `Button.MouseClick`.</span><span class="sxs-lookup"><span data-stu-id="81936-121">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="81936-122">Ciò è possibile perché <xref:System.EventArgs> è un tipo di base sia di <xref:System.Windows.Forms.KeyEventArgs> che di <xref:System.Windows.Forms.MouseEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="81936-122">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>
  
### <a name="code"></a><span data-ttu-id="81936-123">Codice</span><span class="sxs-lookup"><span data-stu-id="81936-123">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="81936-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81936-124">See also</span></span>

- [<span data-ttu-id="81936-125">Varianza nei delegati (C#)</span><span class="sxs-lookup"><span data-stu-id="81936-125">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
- [<span data-ttu-id="81936-126">Uso della varianza per i delegati generici Func e Action (C#)</span><span class="sxs-lookup"><span data-stu-id="81936-126">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)

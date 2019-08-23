---
title: Implementazione dei metodi nei controlli personalizzati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], method implementation
- custom controls [Windows Forms], overloading methods
- custom controls [Windows Forms], method implementation
- methods [Windows Forms]
- methods [Windows Forms], custom controls
ms.assetid: 35d14fca-4bb4-4a27-8211-1f7a98ea27de
ms.openlocfilehash: 867bf97ea13654de6f9c0209c64b9320824f9665
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931747"
---
# <a name="method-implementation-in-custom-controls"></a><span data-ttu-id="83b2d-102">Implementazione dei metodi nei controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="83b2d-102">Method Implementation in Custom Controls</span></span>
<span data-ttu-id="83b2d-103">Un metodo viene implementato in un controllo nello stesso modo in cui avviene in qualsiasi altro componente.</span><span class="sxs-lookup"><span data-stu-id="83b2d-103">A method is implemented in a control in the same manner a method would be implemented in any other component.</span></span>  
  
 <span data-ttu-id="83b2d-104">In Visual Basic, se un metodo deve restituire un valore, viene implementato come `Public Function`,</span><span class="sxs-lookup"><span data-stu-id="83b2d-104">In Visual Basic, if a method is required to return a value, it is implemented as a `Public Function`.</span></span> <span data-ttu-id="83b2d-105">mentre se non deve restituire alcun valore, viene implementato come `Public Sub`.</span><span class="sxs-lookup"><span data-stu-id="83b2d-105">If no value is returned, it is implemented as a `Public Sub`.</span></span> <span data-ttu-id="83b2d-106">I metodi vengono dichiarati usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="83b2d-106">Methods are declared using the following syntax:</span></span>  
  
```vb  
Public Function ConvertMatterToEnergy(Matter as Integer) As Integer  
   ' Conversion code goes here.  
End Function  
```  
  
 <span data-ttu-id="83b2d-107">Poiché le funzioni restituiscono un valore, devono specificare un tipo restituito come Integer, String, Object e così via.</span><span class="sxs-lookup"><span data-stu-id="83b2d-107">Because functions return a value, they must specify a return type, such as integer, string, object, and so on.</span></span> <span data-ttu-id="83b2d-108">È anche necessario specificare gli argomenti accettati dalle routine `Function` o `Sub`, se presenti.</span><span class="sxs-lookup"><span data-stu-id="83b2d-108">The arguments `Function` or `Sub` procedures take, if any, must also be specified.</span></span>  
  
 <span data-ttu-id="83b2d-109">A differenza di Visual Basic, C# non fa distinzione tra funzioni e routine.</span><span class="sxs-lookup"><span data-stu-id="83b2d-109">C# makes no distinction between functions and procedures, as Visual Basic does.</span></span> <span data-ttu-id="83b2d-110">Un metodo può restituire un valore o il risultato `void`.</span><span class="sxs-lookup"><span data-stu-id="83b2d-110">A method either returns a value or returns `void`.</span></span> <span data-ttu-id="83b2d-111">La sintassi per dichiarare un metodo pubblico in C# è la seguente:</span><span class="sxs-lookup"><span data-stu-id="83b2d-111">The syntax for declaring a C# public method is:</span></span>  
  
```csharp  
public int ConvertMatterToEnergy(int matter)  
{  
   // Conversion code goes here.  
}  
```  
  
 <span data-ttu-id="83b2d-112">Quando si dichiara un metodo, ove possibile dichiarare tutti gli argomenti come tipi di dati espliciti.</span><span class="sxs-lookup"><span data-stu-id="83b2d-112">When you declare a method, declare all of its arguments as explicit data types whenever possible.</span></span> <span data-ttu-id="83b2d-113">È necessario dichiarare gli argomenti che accettano i riferimenti agli oggetti come tipi di classe specifici, ad esempio `As Widget` anziché `As Object`.</span><span class="sxs-lookup"><span data-stu-id="83b2d-113">Arguments that take object references should be declared as specific class types — for example, `As Widget` instead of `As Object`.</span></span> <span data-ttu-id="83b2d-114">In Visual Basic, l'impostazione predefinita `Option Strict` applica automaticamente questa regola.</span><span class="sxs-lookup"><span data-stu-id="83b2d-114">In Visual Basic, the default setting `Option Strict` automatically enforces this rule.</span></span>  
  
 <span data-ttu-id="83b2d-115">Gli argomenti con tipo assegnato consentono di individuare molti errori degli sviluppatori al momento della compilazione, piuttosto che in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="83b2d-115">Typed arguments allow many developer errors to be caught by the compiler, rather than at run time.</span></span> <span data-ttu-id="83b2d-116">Il compilatore individua sempre gli errori, mentre i test in fase di esecuzione sono funzionali come la suite di test.</span><span class="sxs-lookup"><span data-stu-id="83b2d-116">The compiler always catches errors, whereas run-time testing is only as good as the test suite.</span></span>  
  
## <a name="overloaded-methods"></a><span data-ttu-id="83b2d-117">Metodi di overload</span><span class="sxs-lookup"><span data-stu-id="83b2d-117">Overloaded Methods</span></span>  
 <span data-ttu-id="83b2d-118">Per consentire agli utenti del controllo di specificare diverse combinazioni di parametri in un metodo, fornire più overload del metodo mediante la dichiarazione esplicita dei tipi di dati usati.</span><span class="sxs-lookup"><span data-stu-id="83b2d-118">If you want to allow users of your control to supply different combinations of parameters to a method, provide multiple overloads of the method, using explicit data types.</span></span> <span data-ttu-id="83b2d-119">Evitare di creare parametri dichiarati `As Object` che possono contenere qualsiasi tipo di dati, perché questo può causare errori che non vengono individuati nei test.</span><span class="sxs-lookup"><span data-stu-id="83b2d-119">Avoid creating parameters declared `As Object` that can contain any data type, as this can lead to errors that might not be caught in testing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83b2d-120">Il tipo di dati universale in è `Object` anziché `Variant`.</span><span class="sxs-lookup"><span data-stu-id="83b2d-120">The universal data type in the common language runtime is `Object` rather than `Variant`.</span></span> <span data-ttu-id="83b2d-121">`Variant` è stato rimosso dal linguaggio.</span><span class="sxs-lookup"><span data-stu-id="83b2d-121">`Variant` has been removed from the language.</span></span>  
  
 <span data-ttu-id="83b2d-122">Ad esempio, il metodo `Spin` di un ipotetico controllo `Widget` potrebbe consentire la specifica diretta della direzione e della velocità di rotazione oppure la specifica di un altro oggetto `Widget` da cui assorbire il momento angolare:</span><span class="sxs-lookup"><span data-stu-id="83b2d-122">For example, the `Spin` method of a hypothetical `Widget` control might allow either direct specification of spin direction and speed, or specification of another `Widget` object from which angular momentum is to be absorbed:</span></span>  
  
```vb  
Overloads Public Sub Spin( _  
   ByVal SpinDirection As SpinDirectionsEnum, _  
   ByVal RevolutionsPerSecond As Double)  
   ' Implementation code here.  
End Sub  
Overloads Public Sub Spin(ByVal Driver As Widget) _  
   ' Implementation code here.  
End Sub  
```  
  
```csharp  
public void Spin(SpinDirectionsEnum spinDirection, double revolutionsPerSecond)  
{  
   // Implementation code here.  
}  
  
public void Spin(Widget driver)  
{  
   // Implementation code here.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="83b2d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83b2d-123">See also</span></span>

- [<span data-ttu-id="83b2d-124">Eventi</span><span class="sxs-lookup"><span data-stu-id="83b2d-124">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="83b2d-125">Proprietà dei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="83b2d-125">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)

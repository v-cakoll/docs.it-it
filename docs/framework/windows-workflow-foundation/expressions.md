---
title: Espressioni-WF
ms.date: 03/30/2017
ms.assetid: c42341a9-43a1-462c-bffb-c5de004aa428
ms.openlocfilehash: 93d437ae6d20f5d31d80ef3a40f409c589ae084e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962411"
---
# <a name="expressions"></a><span data-ttu-id="90bc8-102">Espressioni</span><span class="sxs-lookup"><span data-stu-id="90bc8-102">Expressions</span></span>
<span data-ttu-id="90bc8-103">Un'espressione Windows Workflow Foundation (WF) è qualsiasi attività che restituisce un risultato.</span><span class="sxs-lookup"><span data-stu-id="90bc8-103">A Windows Workflow Foundation (WF) expression is any activity that returns a result.</span></span> <span data-ttu-id="90bc8-104">Tutte le attività di espressione derivano indirettamente da <xref:System.Activities.Activity%601>, che contiene una proprietà <xref:System.Activities.OutArgument> che viene denominata <xref:System.Activities.Activity%601.Result%2A> quando l'attività restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="90bc8-104">All expression activities derive indirectly from <xref:System.Activities.Activity%601>, which contains an <xref:System.Activities.OutArgument> property named <xref:System.Activities.Activity%601.Result%2A> as the activity’s return value.</span></span> [!INCLUDE[wf1](../../../includes/wf1-md.md)] <span data-ttu-id="90bc8-105">viene fornito con un'ampia gamma di attività di espressione, da quelle semplici come <xref:System.Activities.Expressions.VariableValue%601> e <xref:System.Activities.Expressions.VariableReference%601>, che consentono di accedere a variabili del flusso di lavoro attraverso attività dell'operatore, a quelle complesse come <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> e <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> che, per produrre il risultato, offrono l'accesso all'intera gamma di funzionalità del linguaggio Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="90bc8-105">ships with a wide range of expression activities from simple ones like <xref:System.Activities.Expressions.VariableValue%601> and <xref:System.Activities.Expressions.VariableReference%601>, which provide access to single workflow variable through operator activities, to complex activities such as <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> and <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> that offer access to the full breadth of Visual Basic language to produce the result.</span></span> <span data-ttu-id="90bc8-106">È possibile creare attività di espressione aggiuntive derivando dall'oggetto <xref:System.Activities.CodeActivity%601> o <xref:System.Activities.NativeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="90bc8-106">Additional expression activities can be created by deriving from <xref:System.Activities.CodeActivity%601> or <xref:System.Activities.NativeActivity%601>.</span></span>  
  
## <a name="using-expressions"></a><span data-ttu-id="90bc8-107">Uso di espressioni</span><span class="sxs-lookup"><span data-stu-id="90bc8-107">Using Expressions</span></span>  
 <span data-ttu-id="90bc8-108">Progettazione flussi di lavoro usa <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> e <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> per tutte le espressioni nei progetti Visual Basic e <xref:Microsoft.CSharp.Activities.CSharpValue%601> e <xref:Microsoft.CSharp.Activities.CSharpReference%601> per le espressioni nei progetti flusso di lavoro C#</span><span class="sxs-lookup"><span data-stu-id="90bc8-108">Workflow designer uses <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> and <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> for all expressions in Visual Basic projects, and <xref:Microsoft.CSharp.Activities.CSharpValue%601> and <xref:Microsoft.CSharp.Activities.CSharpReference%601> for expressions in C# workflow projects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90bc8-109">Il supporto C# per le espressioni nei progetti di flusso di lavoro è stato introdotto in .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="90bc8-109">Support for C# expressions in workflow projects was introduced in .NET Framework 4.5.</span></span> <span data-ttu-id="90bc8-110">Per ulteriori informazioni, vedere [ C# espressioni](csharp-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="90bc8-110">For more information, see [C# Expressions](csharp-expressions.md).</span></span>  
  
 <span data-ttu-id="90bc8-111">I flussi di lavoro prodotti dalla finestra di progettazione vengono salvati nel codice XAML, in cui le espressioni sono incluse tra parentesi quadre, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="90bc8-111">Workflows produced by designer are saved in XAML, where expressions appear enclosed in square brackets, as in the following example.</span></span>  
  
```xml  
<Sequence xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <Variable x:TypeArguments="x:Int32" Default="1" Name="a" />  
    <Variable x:TypeArguments="x:Int32" Default="2" Name="b" />  
    <Variable x:TypeArguments="x:Int32" Default="3" Name="c" />  
    <Variable x:TypeArguments="x:Int32" Default="0" Name="r" />  
  </Sequence.Variables>  
  <Assign>  
    <Assign.To>  
      <OutArgument x:TypeArguments="x:Int32">[r]</OutArgument>  
    </Assign.To>  
    <Assign.Value>  
      <InArgument x:TypeArguments="x:Int32">[a + b + c]</InArgument>  
    </Assign.Value>  
  </Assign>  
</Sequence>  
```  
  
 <span data-ttu-id="90bc8-112">Quando si definisce un flusso di lavoro nel codice, è possibile usare qualsiasi attività di espressione.</span><span class="sxs-lookup"><span data-stu-id="90bc8-112">When defining a workflow in code, any expression activities can be used.</span></span> <span data-ttu-id="90bc8-113">Nell'esempio seguente viene mostrato l'uso di una composizione di attività dell'operatore per aggiungere tre numeri.</span><span class="sxs-lookup"><span data-stu-id="90bc8-113">The following example shows the usage of a composition of operator activities to add three numbers.</span></span>  
  
```  
Variable<int> a = new Variable<int>("a", 1);  
Variable<int> b = new Variable<int>("b", 2);  
Variable<int> c = new Variable<int>("c", 3);  
Variable<int> r = new Variable<int>("r", 0);  
  
Sequence w = new Sequence  
{  
    Variables = { a, b, c, r },  
    Activities =   
    {  
        new Assign {  
            To = new OutArgument<int>(r),  
            Value = new InArgument<int> {  
                Expression = new Add<int, int, int> {  
                    Left = new Add<int, int, int> {  
                        Left = new InArgument<int>(a),  
                        Right = new InArgument<int>(b)  
                    },  
                    Right = new InArgument<int>(c)  
                }  
            }  
        }  
    }  
};  
```  
  
 <span data-ttu-id="90bc8-114">Lo stesso flusso di lavoro può essere espresso in modo più compatto usando le espressioni lambda di C#, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="90bc8-114">The same workflow can be expressed more compactly by using C# lambda expressions, as shown in the following example.</span></span>  
  
```  
Variable<int> a = new Variable<int>("a", 1);  
Variable<int> b = new Variable<int>("b", 2);  
Variable<int> c = new Variable<int>("c", 3);  
Variable<int> r = new Variable<int>("r", 0);  
  
Sequence w = new Sequence  
{  
    Variables = { a, b, c, r },  
    Activities =   
    {  
        new Assign {  
            To = new OutArgument<int>(r),  
            Value = new InArgument<int>((ctx) => a.Get(ctx) + b.Get(ctx) + c.Get(ctx))  
        }  
    }  
};  
```  
  
 <span data-ttu-id="90bc8-115">Il flusso di lavoro può essere espresso anche usando le espressioni di attività di Visual Basic, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="90bc8-115">The workflow can also be expressed by using Visual Basic expression activities, as shown in the following example.</span></span>  
  
```  
Variable<int> a = new Variable<int>("a", 1);  
Variable<int> b = new Variable<int>("b", 2);  
Variable<int> c = new Variable<int>("c", 3);  
Variable<int> r = new Variable<int>("r", 0);  
  
Sequence w = new Sequence  
{  
    Variables = { a, b, c, r },  
    Activities =   
    {  
        new Assign {  
            To = new OutArgument<int>(r),  
            Value = new InArgument<int>(new VisualBasicValue<int>("a + b + c"))  
        }  
    }  
};  
```  
  
## <a name="extending-available-expressions-with-custom-expression-activities"></a><span data-ttu-id="90bc8-116">Estensione di espressioni disponibili con attività di espressione personalizzate</span><span class="sxs-lookup"><span data-stu-id="90bc8-116">Extending Available Expressions with Custom Expression Activities</span></span>  
 <span data-ttu-id="90bc8-117">Le espressioni in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] possono essere estese consentendo la creazione di attività di espressione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="90bc8-117">Expressions in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] are extensible allowing for additional expression activities to be created.</span></span> <span data-ttu-id="90bc8-118">Nell'esempio seguente viene mostrata un'attività che restituisce una somma di tre valori Integer.</span><span class="sxs-lookup"><span data-stu-id="90bc8-118">The following example shows an activity that returns a sum of three integer values.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Activities;  
  
namespace ExpressionsDemo  
{  
    public sealed class AddThreeValues : CodeActivity<int>  
    {  
        public InArgument<int> Value1 { get; set; }  
        public InArgument<int> Value2 { get; set; }  
        public InArgument<int> Value3 { get; set; }  
  
        protected override int Execute(CodeActivityContext context)  
        {  
            return Value1.Get(context) +   
                   Value2.Get(context) +   
                   Value3.Get(context);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="90bc8-119">Con questa nuova attività è possibile riscrivere il flusso di lavoro precedente che ha aggiunto tre valori come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="90bc8-119">With this new activity you can rewrite the previous workflow that added three values as shown in the following example.</span></span>  
  
```  
Variable<int> a = new Variable<int>("a", 1);  
Variable<int> b = new Variable<int>("b", 2);  
Variable<int> c = new Variable<int>("c", 3);  
Variable<int> r = new Variable<int>("r", 0);  
  
Sequence w = new Sequence  
{  
    Variables = { a, b, c, r },  
    Activities =   
    {  
        new Assign {  
            To = new OutArgument<int>(r),  
            Value = new InArgument<int> {  
                Expression = new AddThreeValues() {  
                    Value1 = new InArgument<int>(a),  
                    Value2 = new InArgument<int>(b),  
                    Value3 = new InArgument<int>(c)  
                }  
            }  
        }  
    }  
};  
```  
  
 <span data-ttu-id="90bc8-120">Per ulteriori informazioni sull'utilizzo di espressioni nel codice, vedere [creazione di flussi di lavoro, attività ed espressioni tramite codice](authoring-workflows-activities-and-expressions-using-imperative-code.md)imperativo.</span><span class="sxs-lookup"><span data-stu-id="90bc8-120">For more information about using expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>

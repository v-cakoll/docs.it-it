---
title: 'Esercitazione: Implementare un contratto di servizio Windows Communication Foundation'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: 05923dc0a2223da5e5fcda483abc1ee1dd2d643f
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928701"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="fef7c-102">Esercitazione: Implementare un contratto di servizio Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="fef7c-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="fef7c-103">In questa esercitazione viene descritta la seconda delle cinque attività necessarie per creare un'applicazione di base Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fef7c-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="fef7c-104">Per una panoramica delle esercitazioni, vedere [esercitazione: Inizia a usare Windows Communication Foundation applicazioni](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="fef7c-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="fef7c-105">Il passaggio successivo per la creazione di un'applicazione WCF consiste nell'aggiungere codice per implementare l'interfaccia del servizio WCF creata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="fef7c-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="fef7c-106">In questo passaggio viene creata una classe denominata `CalculatorService` che implementa l'interfaccia definita `ICalculator` dall'utente.</span><span class="sxs-lookup"><span data-stu-id="fef7c-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="fef7c-107">Ogni metodo nel codice seguente chiama un'operazione del calcolatore e scrive il testo nella console per testarlo.</span><span class="sxs-lookup"><span data-stu-id="fef7c-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span> 

<span data-ttu-id="fef7c-108">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="fef7c-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="fef7c-109">Aggiungere il codice per implementare il contratto di servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="fef7c-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="fef7c-110">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="fef7c-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="fef7c-111">Aggiungere codice per implementare il contratto di servizio WCF</span><span class="sxs-lookup"><span data-stu-id="fef7c-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="fef7c-112">In **GettingStartedLib**aprire il file **Service1.cs** o **Service1. vb** e sostituirne il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fef7c-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

## <a name="edit-appconfig"></a><span data-ttu-id="fef7c-113">Modificare app. config</span><span class="sxs-lookup"><span data-stu-id="fef7c-113">Edit App.config</span></span>

<span data-ttu-id="fef7c-114">Modificare **app. config** in **GettingStartedLib** per riflettere le modifiche apportate al codice.</span><span class="sxs-lookup"><span data-stu-id="fef7c-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>

- <span data-ttu-id="fef7c-115">Per i C# progetti visivi:</span><span class="sxs-lookup"><span data-stu-id="fef7c-115">For Visual C# projects:</span></span>
  - <span data-ttu-id="fef7c-116">Modificare la riga 14 in`<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="fef7c-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="fef7c-117">Modificare la riga 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="fef7c-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="fef7c-118">Modificare la riga 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="fef7c-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="fef7c-119">Per i progetti di Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="fef7c-119">For Visual Basic projects:</span></span>
  - <span data-ttu-id="fef7c-120">Modificare la riga 14 in`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="fef7c-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="fef7c-121">Modificare la riga 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="fef7c-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="fef7c-122">Modificare la riga 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="fef7c-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="fef7c-123">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="fef7c-123">Compile the code</span></span>

<span data-ttu-id="fef7c-124">Compilare la soluzione per verificare che non siano presenti errori di compilazione.</span><span class="sxs-lookup"><span data-stu-id="fef7c-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="fef7c-125">Se si usa Visual Studio, scegliere **Compila soluzione** dal menu **Compila** oppure premere **CTRL**+**MAIUSC**+**B**.</span><span class="sxs-lookup"><span data-stu-id="fef7c-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fef7c-126">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fef7c-126">Next steps</span></span>

<span data-ttu-id="fef7c-127">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="fef7c-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="fef7c-128">Aggiungere il codice per implementare il contratto di servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="fef7c-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="fef7c-129">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="fef7c-129">Build the solution.</span></span>

<span data-ttu-id="fef7c-130">Passare all'esercitazione successiva per apprendere come eseguire il servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="fef7c-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fef7c-131">Esercitazione: Ospitare ed eseguire un servizio WCF di base</span><span class="sxs-lookup"><span data-stu-id="fef7c-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)

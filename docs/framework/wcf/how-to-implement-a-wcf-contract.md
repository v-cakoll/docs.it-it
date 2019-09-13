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
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>Esercitazione: Implementare un contratto di servizio Windows Communication Foundation

In questa esercitazione viene descritta la seconda delle cinque attività necessarie per creare un'applicazione di base Windows Communication Foundation (WCF). Per una panoramica delle esercitazioni, vedere [esercitazione: Inizia a usare Windows Communication Foundation applicazioni](getting-started-tutorial.md).

Il passaggio successivo per la creazione di un'applicazione WCF consiste nell'aggiungere codice per implementare l'interfaccia del servizio WCF creata nel passaggio precedente. In questo passaggio viene creata una classe denominata `CalculatorService` che implementa l'interfaccia definita `ICalculator` dall'utente. Ogni metodo nel codice seguente chiama un'operazione del calcolatore e scrive il testo nella console per testarlo. 

In questa esercitazione si imparerà a:
> [!div class="checklist"]
>
> - Aggiungere il codice per implementare il contratto di servizio WCF.
> - Compilare la soluzione.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>Aggiungere codice per implementare il contratto di servizio WCF

In **GettingStartedLib**aprire il file **Service1.cs** o **Service1. vb** e sostituirne il codice con il codice seguente:

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

## <a name="edit-appconfig"></a>Modificare app. config

Modificare **app. config** in **GettingStartedLib** per riflettere le modifiche apportate al codice.

- Per i C# progetti visivi:
  - Modificare la riga 14 in`<service name="GettingStartedLib.CalculatorService">`
  - Modificare la riga 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Modificare la riga 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

- Per i progetti di Visual Basic:
  - Modificare la riga 14 in`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
  - Modificare la riga 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Modificare la riga 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`

## <a name="compile-the-code"></a>Compilare il codice

Compilare la soluzione per verificare che non siano presenti errori di compilazione. Se si usa Visual Studio, scegliere **Compila soluzione** dal menu **Compila** oppure premere **CTRL**+**MAIUSC**+**B**.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
>
> - Aggiungere il codice per implementare il contratto di servizio WCF.
> - Compilare la soluzione.

Passare all'esercitazione successiva per apprendere come eseguire il servizio WCF.

> [!div class="nextstepaction"]
> [Esercitazione: Ospitare ed eseguire un servizio WCF di base](how-to-host-and-run-a-basic-wcf-service.md)

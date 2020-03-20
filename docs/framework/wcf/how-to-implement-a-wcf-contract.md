---
title: 'Esercitazione: Implementare un contratto di servizio di Windows Communication FoundationTutorial: Implement a Windows Communication Foundation service contract'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: debdeeac7064f5bae21622b2d9de84a4d8a0e66f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184064"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>Esercitazione: Implementare un contratto di servizio di Windows Communication FoundationTutorial: Implement a Windows Communication Foundation service contract

Questa esercitazione descrive la seconda delle cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF) di base. Per una panoramica delle esercitazioni, vedere [Esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).

Il passaggio successivo per la creazione di un'applicazione WCF consiste nell'aggiungere il codice per implementare l'interfaccia del servizio WCF creata nel passaggio precedente. In questo passaggio viene `CalculatorService` creata una classe `ICalculator` denominata che implementa l'interfaccia definita dall'utente. Ogni metodo nel codice seguente chiama un'operazione della calcolatrice e scrive testo nella console per testarlo.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Aggiungere il codice per implementare il contratto di servizio WCF.
> - Compilare la soluzione.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>Aggiungere codice per implementare il contratto di servizio WCFAdd code to implement the WCF service contract

In **GettingStartedLib**aprire il file **Service1.cs** o **Service1.vb** e sostituirne il codice con il codice seguente:

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

## <a name="edit-appconfig"></a>Modifica App.config

Modificare **App.config** in **GettingStartedLib** per riflettere le modifiche apportate al codice.

- Per i progetti di Visual C:
  - Cambia linea 14 in`<service name="GettingStartedLib.CalculatorService">`
  - Cambia linea 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Cambia linea 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

- Per i progetti di Visual Basic:
  - Cambia linea 14 in`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
  - Cambia linea 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Cambia linea 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`

## <a name="compile-the-code"></a>Compilare il codice

Compilare la soluzione per verificare che non siano presenti errori di compilazione. Se si utilizza Visual Studio, scegliere **Compila soluzione** dal menu **Compila** (o premere **CTRL**+**MAIUSC**+**B**).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> - Aggiungere il codice per implementare il contratto di servizio WCF.
> - Compilare la soluzione.

Passare all'esercitazione successiva per informazioni su come eseguire il servizio WCF.

> [!div class="nextstepaction"]
> [Esercitazione: Ospitare ed eseguire un servizio WCF di baseTutorial: Host and run a basic WCF service](how-to-host-and-run-a-basic-wcf-service.md)

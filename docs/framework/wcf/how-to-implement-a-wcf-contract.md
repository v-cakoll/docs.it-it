---
title: 'Esercitazione: Implementare un contratto di servizio Windows Communication Foundation'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: fcf96af11bae701585acd92001c8000125858449
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410082"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>Esercitazione: Implementare un contratto di servizio Windows Communication Foundation

Questa esercitazione illustra il secondo di cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF). Per una panoramica delle esercitazioni, vedere [esercitazione: Iniziare con le applicazioni di Windows Communication Foundation](getting-started-tutorial.md).

Il passaggio successivo per la creazione di un'applicazione WCF consiste nell'aggiungere codice per implementare l'interfaccia del servizio WCF creato nel passaggio precedente. In questo passaggio si crea una classe denominata `CalculatorService` che implementa il definito dall'utente `ICalculator` interfaccia. Ogni metodo nel codice seguente chiama un'operazione della calcolatrice e scrive il testo nella console per eseguire il test. 

In questa esercitazione si imparerà a:
> [!div class="checklist"]
> - Aggiungere codice per implementare il contratto di servizio WCF.
> - Compilare la soluzione.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>Aggiungere il codice per implementare il contratto di servizio WCF

Nelle **GettingStartedLib**, aprire il **Service1.cs** oppure **Service1.vb** file e sostituire il codice con il codice seguente:

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

Modificare **app. config** nelle **GettingStartedLib** in modo da riflettere le modifiche apportate al codice.
   - Per oggetto visivo C# progetti:
       - Modificare la riga 14 per `<service name="GettingStartedLib.CalculatorService">`
       - Modificare la riga 17 per `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
       - Modificare la riga 22 per `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

   - Per i progetti di Visual Basic:
       - Modificare la riga 14 per `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
       - Modificare la riga 17 per `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
       - Modificare la riga 22 per `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`


## <a name="compile-the-code"></a>Compilare il codice

Compilare la soluzione per verificare che non siano presenti errori di compilazione. Se si usa Visual Studio, nel **compilare** dal menu **Compila soluzione** (o premere **Ctrl**+**MAIUSC** + **B**).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
> - Aggiungere codice per implementare il contratto di servizio WCF.
> - Compilare la soluzione.

Passare all'esercitazione successiva per informazioni su come eseguire il servizio WCF.

> [!div class="nextstepaction"]
> [Esercitazione: Ospitare ed eseguire un servizio WCF di base](how-to-host-and-run-a-basic-wcf-service.md)

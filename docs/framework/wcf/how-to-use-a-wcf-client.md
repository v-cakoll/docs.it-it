---
title: 'Esercitazione: Usare un client Windows Communication FoundationTutorial: Use a Windows Communication Foundation client'
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: d2357c134aef8da204dcdb19d6c1fc93cfdc068c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184016"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a>Esercitazione: Usare un client Windows Communication FoundationTutorial: Use a Windows Communication Foundation client

Questa esercitazione descrive l'ultima delle cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF) di base. Per una panoramica delle esercitazioni, vedere [Esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).

Dopo aver creato e configurato un proxy Windows Communication Foundation (WCF), creare un'istanza client e compilare l'applicazione client. Viene quindi utilizzato per comunicare con il servizio WCF.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Aggiungere il codice per usare il client WCF.
> - Testare il client WCF.

## <a name="add-code-to-use-the-wcf-client"></a>Aggiungere codice per usare il client WCFAdd code to use the WCF client

Il codice client esegue i passaggi seguenti:The client code does the following steps:

- Crea un'istanza del client WCF.
- Chiamata delle operazioni del servizio dal proxy generato.
- Chiude il client al termine della chiamata all'operazione.

Aprire il file **Program.cs** o **Module1.vb** dal progetto **GettingStartedClient** e sostituirne il codice con il codice seguente:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using GettingStartedClient.ServiceReference1;

namespace GettingStartedClient
{
    class Program
    {
        static void Main(string[] args)
        {
            //Step 1: Create an instance of the WCF proxy.
            CalculatorClient client = new CalculatorClient();

            // Step 2: Call the service operations.
            // Call the Add service operation.
            double value1 = 100.00D;
            double value2 = 15.99D;
            double result = client.Add(value1, value2);
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

            // Call the Subtract service operation.
            value1 = 145.00D;
            value2 = 76.54D;
            result = client.Subtract(value1, value2);
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

            // Call the Multiply service operation.
            value1 = 9.00D;
            value2 = 81.25D;
            result = client.Multiply(value1, value2);
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

            // Call the Divide service operation.
            value1 = 22.00D;
            value2 = 7.00D;
            result = client.Divide(value1, value2);
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

            // Step 3: Close the client to gracefully close the connection and clean up resources.
            Console.WriteLine("\nPress <Enter> to terminate the client.");
            Console.ReadLine();
            client.Close();
        }
    }
}
```

```vb
Imports System.Collections.Generic
Imports System.Text
Imports System.ServiceModel
Imports GettingStartedClient.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy.
        Dim Client As New CalculatorClient()

        ' Step 2: Call the service operations.
        ' Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        ' Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        ' Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        ' Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Close the client to gracefully close the connection and clean up resources.
        Console.WriteLine()
        Console.WriteLine("Press <Enter> to terminate the client.")
        Console.ReadLine()
        Client.Close()

    End Sub

End Module
```

Si `using` noti l'istruzione `Imports` (per Visual Cè) `GettingStartedClient.ServiceReference1`o (per Visual Basic) che importa . Questa istruzione importa il codice generato da Visual Studio con la funzione Aggiungi riferimento al **servizio.** Il codice crea un'istanza del proxy WCF e chiama ognuna delle operazioni del servizio esposte dal servizio calcolatrice. Quindi chiude il proxy e termina il programma.

## <a name="test-the-wcf-client"></a>Testare il client WCFTest the WCF client

### <a name="test-the-application-from-visual-studio"></a>Testare l'applicazione da Visual StudioTest the application from Visual Studio

1. Salvare e generare la soluzione.

2. Selezionare la cartella **GettingStartedLib,** quindi scegliere Imposta come progetto di **avvio** dal menu di scelta rapida.

3. Da Progetti di **avvio**, selezionare **GettingStartedLib** dall'elenco a discesa, quindi selezionare **Esegui** o premere **F5**.

### <a name="test-the-application-from-a-command-prompt"></a>Testare l'applicazione da un prompt dei comandi

1. Aprire un prompt dei comandi come amministratore e quindi passare alla directory della soluzione di Visual Studio.Open a command prompt as an administrator, and then navigate to your Visual Studio solution directory.

2. Per avviare il servizio: immettere *GettingStartedHost, bin, Debug, GettingStartedHost.exe*.

3. Per avviare il client: aprire un altro prompt dei comandi, passare alla directory della soluzione di Visual Studio, quindi immettere *GettingStartedClient, bin, Debug, GettingStartedClient.exe*.

   *GettingStartedHost.exe* produce il seguente output:

   ```text
   The service is ready.
   Press <Enter> to terminate the service.

   Received Add(100,15.99)
   Return: 115.99
   Received Subtract(145,76.54)
   Return: 68.46
   Received Multiply(9,81.25)
   Return: 731.25
   Received Divide(22,7)
   Return: 3.14285714285714
   ```

   *GettingStartedClient.exe* produce il seguente output:

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a>Passaggi successivi

A questo punto sono state completate tutte le attività nell'esercitazione introduttiva di WCF. In questa esercitazione sono state illustrate le procedure per:

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Aggiungere il codice per usare il client WCF.
> - Testare il client WCF.

In caso di problemi o errori in uno dei passaggi, seguire i passaggi nell'articolo sulla risoluzione dei problemi per risolverli.

> [!div class="nextstepaction"]
> [Risolvere i problemi relativi alle esercitazioni per informazioni introduttive su WCFTroubleshoot the Get started with WCF tutorials](troubleshooting-the-getting-started-tutorial.md)

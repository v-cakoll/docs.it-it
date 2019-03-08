---
title: 'Procedura: Servizi di accesso con un contratto duplex'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: 366fd9d6aa220bcbec1ee8fb2a04d1b84755800a
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678683"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a>Procedura: Servizi di accesso con un contratto duplex

Una funzionalità di Windows Communication Foundation (WCF) è la possibilità di creare un servizio che usa un modello di messaggistica duplex. Questo modello consente a un servizio di comunicare con il client tramite un callback. Questo argomento illustra i passaggi per creare un client WCF in una classe client che implementa l'interfaccia di callback.

Un'associazione duale espone l'indirizzo IP del client al servizio. Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.

Per un'esercitazione sulla creazione di un servizio WCF di base e un client, vedere [esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md).

## <a name="to-access-a-duplex-service"></a>Per accedere a un servizio duplex

1. Creare un servizio che contiene due interfacce. La prima interfaccia è per il servizio, la seconda è per il callback. Per altre informazioni sulla creazione di un servizio duplex, vedere [come: Creare un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).

2. Eseguire il servizio.

3. Usare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare contratti (interfacce) per il client. Per informazioni su come eseguire questa operazione, vedere [come: Creare un Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).

4. Implementare l'interfaccia di callback nella classe client, come illustrato nell'esempio seguente.

    ```csharp
    public class CallbackHandler : ICalculatorDuplexCallback
    {
        public void Result(double result)
        {
            Console.WriteLine("Result ({0})", result);
        }
        public void Equation(string equation)
        {
            Console.WriteLine("Equation({0})", equation);
        }
    }
    ```

    ```vb
    Public Class CallbackHandler
    Implements ICalculatorDuplexCallback
       Public Sub Result (ByVal result As Double)
          Console.WriteLine("Result ({0})", result)
       End Sub
        Public Sub Equation(ByVal equation As String)
            Console.WriteLine("Equation({0})", equation)
        End Sub
    End Class
    ```

5. Creare un'istanza della classe <xref:System.ServiceModel.InstanceContext>. Il costruttore richiede un'istanza della classe client.

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. Creare un'istanza del client WCF usando il costruttore che richiede un <xref:System.ServiceModel.InstanceContext> oggetto. Il secondo parametro del costruttore è il nome di un endpoint contenuto nel file di configurazione.

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. Chiamare i metodi del client WCF in base alle esigenze.

## <a name="example"></a>Esempio

Nell'esempio di codice seguente viene descritto come creare una classe client che accede a un contratto duplex.

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md)
- [Procedura: Creare un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Procedura: Creare un Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [Procedura: Usare ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)

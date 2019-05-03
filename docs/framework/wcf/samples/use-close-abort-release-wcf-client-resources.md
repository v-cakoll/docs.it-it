---
title: Usare Chiudi e Interrompi per rilasciare risorse client WCF
description: Dispose può avere esito negativo e generano eccezioni quando si verifica un errore di rete. Che può causare comportamenti indesiderati. Invece utilizzare Chiudi e Interrompi per rilasciare le risorse del client quando la rete non è riuscita.
ms.date: 11/12/2018
ms.assetid: aff82a8d-933d-4bdc-b0c2-c2f7527204fb
ms.openlocfilehash: 58f828d9cd85806f5f04c349a7de18828ab5f6f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007573"
---
# <a name="close-and-abort-release-resources-safely-when-network-connections-have-dropped"></a>Chiusura e interruzione rilasciare le risorse in modo sicuro quando le connessioni di rete sono stato eliminato

In questo esempio viene illustrato come utilizzare il `Close` e `Abort` metodi per pulire le risorse quando si usa un client tipizzato. Il `using` istruzione genera eccezioni quando la connessione di rete non è affidabile. In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice. In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

In questo esempio vengono illustrati due dei problemi comuni che si verificano in caso di utilizzo dell'istruzione "using" di C# con i client tipizzati e il codice che pulisce correttamente le eccezioni.

L'istruzione "using" di C# genera una chiamata a `Dispose`(). Questo corrisponde a `Close`(), che può generare eccezioni quando si verifica un errore di rete. Poiché la chiamata a `Dispose`() si verifica implicitamente alla parentesi graffa di chiusura del blocco "using", è probabile che l'origine delle eccezioni non venga rilevata da chi scrive il codice e da chi lo legge. Questa situazione può causare errori dell'applicazione.

Il primo problema, illustrato nel metodo `DemonstrateProblemUsingCanThrow` è che la parentesi graffa di chiusura genera un'eccezione e il codice dopo che la parentesi graffa di chiusura non viene eseguito:

```csharp
using (CalculatorClient client = new CalculatorClient())
{
    ...
} // <-- this line might throw
Console.WriteLine("Hope this code wasn't important, because it might not happen.");
```

Anche se non vengono generate eccezioni nel blocco "using" o se tutte le eccezioni all'interno del blocco "using" vengono rilevate, `Console.WriteLine` potrebbe non verificarsi visto che la chiamata `Dispose`() implicita potrebbe generare un'eccezione alla parentesi graffa di chiusura.

Il secondo problema, illustrato nel metodo `DemonstrateProblemUsingCanThrowAndMask` deriva da un'altra implicazione della parentesi graffa di chiusura che genera un'eccezione:

```csharp
using (CalculatorClient client = new CalculatorClient())
{
    ...
    throw new ApplicationException("Hope this exception was not important, because "+
                                   "it might be masked by the Close exception.");
} // <-- this line might throw an exception.
```

Poiché `Dispose`() si verifica in un blocco "finally", `ApplicationException` non viene mai visualizzato al di fuori del blocco "using" se si verifica un errore in `Dispose`(). Se il codice esterno deve essere in grado di rilevare quando si verifica `ApplicationException`, si potrebbero verificare problemi se il costrutto "using" maschera questa eccezione.

Nell'esempio viene infine illustrato come pulire correttamente le eccezioni che si verificano in `DemonstrateCleanupWithExceptions`. Questa operazione utilizza un blocco try/catch per segnalare gli errori e chiamare `Abort`. Vedere le [eccezioni previsto](../../../../docs/framework/wcf/samples/expected-exceptions.md) esempio per ulteriori informazioni sul rilevamento delle eccezioni da chiamate del client.

```csharp
try
{
    ...
    client.Close();
}
catch (CommunicationException e)
{
    ...
    client.Abort();
}
catch (TimeoutException e)
{
    ...
    client.Abort();
}
catch (Exception e)
{
    ...
    client.Abort();
    throw;
}
```

> [!NOTE]
> L'istruzione using e ServiceHost: Molte applicazioni self-hosting poco più di ospitare un servizio e ServiceHost. Close raramente genera un'eccezione, in modo che tali applicazioni possono utilizzare in modo sicuro l'utilizzo dell'istruzione ServiceHost. Tuttavia, è consigliabile prendere in considerazione che ServiceHost.Close può generare un'eccezione `CommunicationException`, pertanto se l'applicazione è ancora in esecuzione dopo avere chiuso ServiceHost, è necessario evitare di usare l'istruzione using e seguire il modello fornito in precedenza.

Quando si esegue l'esempio, le risposte e le eccezioni dell'operazione vengono visualizzate nella finestra della console client.

Il processo client esegue tre scenari, ognuno dei quali tenta di chiamare `Divide`. Nel primo scenario viene descritto il codice ignorato a causa di un'eccezione da `Dispose`(). Nel secondo scenario viene illustrata un'eccezione importante mascherata a causa di un'eccezione da `Dispose`(). Nel terzo scenario viene illustrato come eseguire correttamente la pulizia.

L'output previsto dal processo client è:

```
=
= Demonstrating problem:  closing brace of using statement can throw.
=
Got System.ServiceModel.CommunicationException from Divide.
Got System.ServiceModel.Security.MessageSecurityException
=
= Demonstrating problem:  closing brace of using statement can mask other Exceptions.
=
Got System.ServiceModel.CommunicationException from Divide.
Got System.ServiceModel.Security.MessageSecurityException
=
= Demonstrating cleanup with Exceptions.
=
Calling client.Add(0.0, 0.0);
        client.Add(0.0, 0.0); returned 0
Calling client.Divide(0.0, 0.0);
Got System.ServiceModel.CommunicationException from Divide.

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\UsingUsing`

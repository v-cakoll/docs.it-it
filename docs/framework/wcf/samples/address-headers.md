---
title: Intestazioni di indirizzo
ms.date: 03/30/2017
ms.assetid: b0c94d4a-3bde-4b4d-bb6d-9f12bc3a6940
ms.openlocfilehash: 133826bbbea62b660bdcdd884ce657528ad30873
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576005"
---
# <a name="address-headers"></a>Intestazioni di indirizzo

Nell'esempio intestazioni di indirizzo viene illustrato come i client possono passare parametri di riferimento a un servizio utilizzando Windows Communication Foundation (WCF).

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

La specifica WS-Addressing definisce la nozione di un riferimento dell'endpoint come un modo di indirizzare un particolare endpoint servizio Web. In WCF, i riferimenti agli endpoint vengono modellati tramite la `EndpointAddress` classe `EndpointAddress` . è il tipo del campo Address della `ServiceEndpoint` classe.

Parte del modello di riferimento all'endpoint è che ogni riferimento può portare alcuni parametri per riferimento che aggiungono informazioni di identificazione aggiuntive. In WCF questi parametri di riferimento vengono modellati come istanze della `AddressHeader` classe.

In questo esempio, il client aggiunge un parametro per riferimento a `EndpointAddress` dell'endpoint client. Il servizio cerca questo parametro per riferimento e ne usa il valore nella logica dell'operazione del servizio "Hello".

## <a name="client"></a>Client

Il client deve aggiungere un `AddressHeader` al `EndpointAddress` del `ServiceEndpoint` per inviare un parametro di riferimento. Poiché la classe `EndpointAddress` è immutabile, è necessario modificare l'indirizzo endpoint utilizzando la classe `EndpointAddressBuilder`. Nel codice seguente il client viene inizializzato per inviare un parametro di riferimento come parte del messaggio.

```csharp
HelloClient client = new HelloClient();
EndpointAddressBuilder builder =
    new EndpointAddressBuilder(client.Endpoint.Address);
AddressHeader header =
    AddressHeader.CreateAddressHeader(IDName, IDNamespace, "John");
builder.Headers.Add(header);
client.Endpoint.Address = builder.ToEndpointAddress();
```

Il codice crea un `EndpointAddressBuilder` utilizzando il `EndpointAddress` originale come valore iniziale. Viene quindi aggiunta un'intestazione di indirizzo appena creata; la chiamata a `CreateAddressHeader` Crea un'intestazione con un nome, uno spazio dei nomi e un valore specifici. In questo esempio il valore è "John." Una volta aggiunta l'intestazione al generatore, il metodo `ToEndpointAddress()` converte nuovamente il generatore (mutevole) in un indirizzo endpoint (immutabile), il quale viene assegnato di nuovo al campo Indirizzo dell'endpoint client.

Quando il client chiama `Console.WriteLine(client.Hello());`, il servizio è in grado di ottenere il valore di questo parametro di indirizzo, come si può vedere nell'output risultante del client.

`Hello, John`

## <a name="server"></a>Server

L'implementazione dell'operazione del servizio `Hello()` utilizza il `OperationContext` corrente per controllare i valori delle intestazioni nel messaggio in arrivo.

```csharp
string id = null;
// look at headers on incoming message
for (int i = 0;
     i < OperationContext.Current.IncomingMessageHeaders.Count;
     ++i)
{
    MessageHeaderInfo h = OperationContext.Current.IncomingMessageHeaders[i];
    // for any reference parameters with the correct name & namespace
    if (h.IsReferenceParameter &&
        h.Name == IDName &&
        h.Namespace == IDNamespace)
    {
        // read the value of that header
        XmlReader xr = OperationContext.Current.IncomingMessageHeaders.GetReaderAtHeader(i);
        id = xr.ReadElementContentAsString();
    }
}
return "Hello, " + id;
```

Il codice scorre tutte le intestazioni nel messaggio in arrivo, cercando intestazioni che sono parametri di riferimento dotati del nome particolare. Una volta individuato il parametro, il codice legge il valore del parametro e lo archivia nella variabile "id".

#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\AddressHeaders`

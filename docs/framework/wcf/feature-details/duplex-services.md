---
title: Servizi duplex
description: Informazioni su come creare un contratto di servizio duplex in WCF, che consente a entrambi gli endpoint di inviare messaggi tra loro tramite un canale creato dal client.
ms.date: 05/09/2018
dev_langs:
- csharp
- vb
ms.assetid: 396b875a-d203-4ebe-a3a1-6a330d962e95
ms.openlocfilehash: a43bb63a0ccf1a34b79dce755c19f7ed4cb6c16c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247351"
---
# <a name="duplex-services"></a>Servizi duplex

Un contratto di servizio duplex è un modello di scambio di messaggi nel quale entrambi gli endpoint possono inviare messaggi l'uno all'altro in modo indipendente. Un servizio duplex, pertanto, può inviare messaggi all'endpoint client, fornendo un comportamento simile a quello degli eventi. Una comunicazione duplex ha luogo quando un client si connette a un servizio e fornisce a quest'ultimo un canale utilizzabile per inviare messaggi al client. Si noti che il comportamento simile a quello degli eventi di servizi duplex funziona solo all'interno di una sessione.

Per creare un contratto duplex è necessario creare una coppia di interfacce. La prima è l'interfaccia del contratto di servizio che descrive le operazioni che un client può richiamare. Il contratto di servizio deve specificare un *contratto di callback* nella <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> Proprietà. Il contratto callback è l'interfaccia che definisce le operazioni che il servizio può chiamare sull'endpoint client. Un contratto duplex non richiede sessioni, sebbene le associazioni duplex fornite dal sistema le utilizzino.

Di seguito è riportato un esempio di contratto duplex.

[!code-csharp[c_DuplexServices#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#0)]
[!code-vb[c_DuplexServices#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#0)]

La classe `CalculatorService` implementa l'interfaccia `ICalculatorDuplex` primaria. Il servizio usa la modalità di istanza <xref:System.ServiceModel.InstanceContextMode.PerSession> per gestire il risultato per ogni sessione. Una proprietà privata denominata `Callback` accede al canale callback al client. Il servizio utilizza il callback per inviare i messaggi al client tramite l'interfaccia callback, come illustrato nel codice di esempio seguente.

[!code-csharp[c_DuplexServices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#1)]
[!code-vb[c_DuplexServices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#1)]

Il client deve fornire una classe che implementi l'interfaccia callback del contratto duplex per ricevere messaggi dal servizio. Nel codice di esempio seguente viene illustrata una classe `CallbackHandler` che implementa l'interfaccia `ICalculatorDuplexCallback`.

[!code-csharp[c_DuplexServices#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#2)]
[!code-vb[c_DuplexServices#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#2)]

Il client WCF generato per un contratto duplex richiede la <xref:System.ServiceModel.InstanceContext> fornitura di una classe durante la costruzione. Questa classe <xref:System.ServiceModel.InstanceContext> viene usata come sito per un oggetto che implementa l'interfaccia callback e gestisce i messaggi restituiti dal servizio. Una classe <xref:System.ServiceModel.InstanceContext> viene costruita con un'istanza della classe `CallbackHandler`. Questo oggetto gestisce i messaggi inviati dal servizio al client sull'interfaccia di callback.

[!code-csharp[c_DuplexServices#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#3)]
[!code-vb[c_DuplexServices#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#3)]

La configurazione per il servizio deve essere impostata in modo da fornire un'associazione che supporta sia la comunicazione della sessione che la comunicazione duplex. L'elemento `wsDualHttpBinding` supporta la comunicazione della sessione e consente la comunicazione duplex fornendo connessioni HTTP doppie, una per ogni direzione.

Sul client, è necessario configurare un indirizzo utilizzabile dal server per la connessione al client, come illustrato nella configurazione di esempio seguente.

> [!NOTE]
> I client non duplex, la cui autenticazione mediante conversazione protetta non riesce, generano di norma un'eccezione <xref:System.ServiceModel.Security.MessageSecurityException>. Se, tuttavia, un client duplex che usa una conversazione protetta non viene autenticato, riceve un'eccezione <xref:System.TimeoutException>.

Quando si crea un client/servizio utilizzando l'elemento `WSHttpBinding` e non si include l'endpoint di callback client, verrà restituito l'errore seguente.

```console
HTTP could not register URL
htp://+:80/Temporary_Listen_Addresses/<guid> because TCP port 80 is being used by another application.
```

Nell'esempio di codice seguente viene illustrato come specificare l'indirizzo dell'endpoint client a livello di codice.

```csharp
WSDualHttpBinding binding = new WSDualHttpBinding();
EndpointAddress endptadr = new EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server");
binding.ClientBaseAddress = new Uri("http://localhost:8000/DuplexTestUsingCode/Client/");
```

```vb
Dim binding As New WSDualHttpBinding()
Dim endptadr As New EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server")
binding.ClientBaseAddress = New Uri("http://localhost:8000/DuplexTestUsingCode/Client/")
```

Nel codice di esempio seguente viene illustrato come specificare l'indirizzo endpoint client nella configurazione.

```xml
<client>
    <endpoint name ="ServerEndpoint"
          address="http://localhost:12000/DuplexTestUsingConfig/Server"
          bindingConfiguration="WSDualHttpBinding_IDuplexTest"
            binding="wsDualHttpBinding"
           contract="IDuplexTest" />
</client>
<bindings>
    <wsDualHttpBinding>
        <binding name="WSDualHttpBinding_IDuplexTest"
          clientBaseAddress="http://localhost:8000/myClient/" >
            <security mode="None"/>
         </binding>
    </wsDualHttpBinding>
</bindings>
```

> [!WARNING]
> Il modello duplex non rileva automaticamente quando un servizio o un client chiude il canale. Quindi, se un client termina in modo imprevisto, per impostazione predefinita il servizio non riceve una notifica o se un servizio termina in modo imprevisto, il client non riceverà alcuna notifica. Se si utilizza un servizio disconnesso, <xref:System.ServiceModel.CommunicationException> viene generata l'eccezione. Client e servizi sono in grado di implementare il proprio protocollo per inviarsi vicendevolmente una notifica, se necessario. Per ulteriori informazioni sulla gestione degli errori, vedere la pagina relativa alla [gestione degli errori WCF](../wcf-error-handling.md).

## <a name="see-also"></a>Vedere anche

- [Duplex](../samples/duplex.md)
- [Specifica del comportamento in fase di esecuzione dei client](../specifying-client-run-time-behavior.md)
- [Procedura: creare una channel factory e usarla per la creazione e la gestione di canali](how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels.md)

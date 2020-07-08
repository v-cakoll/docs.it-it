---
title: 'Procedura: scambiare messaggi in una sessione affidabile'
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 39dd6636f80b107ced1caac29869c6c66e67e21e
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052039"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a>Procedura: scambiare messaggi in una sessione affidabile

In questo argomento vengono delineati i passaggi necessari per attivare una sessione affidabile utilizzando una delle associazioni fornite dal sistema che supportano tale sessione, ma non per impostazione predefinita. Una sessione affidabile viene abilitata in modo imperativo tramite codice o in modo dichiarativo nel file di configurazione. Questa procedura usa i file di configurazione del client e del servizio per abilitare la sessione affidabile e per stabilire che i messaggi arrivano nello stesso ordine in cui sono stati inviati.

La parte principale di questa procedura è che l'elemento di configurazione dell'endpoint contiene un `bindingConfiguration` attributo che fa riferimento a una configurazione di associazione denominata `Binding1` . L' [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) elemento di configurazione fa riferimento a questo nome per abilitare sessioni affidabili impostando l' `enabled` attributo dell' [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) elemento su `true` . Le garanzie di recapito ordinato per la sessione affidabile vengono specificate impostando l'attributo `ordered` su `true`.

Per la copia di origine di questo esempio, vedere [WS Reliable Session](../samples/ws-reliable-session.md).

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il servizio con WSHttpBinding per l'utilizzo di una sessione affidabile

1. Definire un contratto di servizio per il tipo di servizio.

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. Implementare il contratto di servizio in una classe del servizio. Si noti che le informazioni sull'indirizzo o sull'associazione non sono specificate nell'implementazione del servizio. Non è necessario scrivere codice per recuperare l'indirizzo o le informazioni di binding dal file di configurazione.

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. Creare un file di *Web.config* per configurare un endpoint per il `CalculatorService` che utilizza il <xref:System.ServiceModel.WSHttpBinding> con la sessione affidabile abilitata e il recapito ordinato dei messaggi necessari.

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. Creare un file *Service. svc* contenente la riga:

   ```aspx-csharp
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. Inserire il file *Service. svc* nella directory virtuale Internet Information Services (IIS).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il client con WSHttpBinding per l'utilizzo di una sessione affidabile

1. Utilizzare lo [strumento ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) dalla riga di comando per generare codice dai metadati del servizio:

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Il client generato contiene l' `ICalculator` interfaccia che definisce il contratto di servizio che l'implementazione client deve soddisfare.

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. L'applicazione client generata contiene inoltre l'implementazione di `ClientCalculator`. Si noti che le informazioni sull'indirizzo e sull'associazione non sono specificate in un punto qualsiasi all'interno dell'implementazione del servizio. Non è necessario scrivere codice per recuperare l'indirizzo o le informazioni di binding dal file di configurazione.

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. *Svcutil.exe* inoltre genera la configurazione per il client che utilizza la <xref:System.ServiceModel.WSHttpBinding> classe. Denominare il file di configurazione *App.config* quando si usa Visual Studio.

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. Creare un'istanza di `ClientCalculator` in un'applicazione e chiamare le operazioni del servizio.

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. Compilare ed eseguire il client.

## <a name="example"></a>Esempio

Diverse associazioni fornite dal sistema supportano sessioni affidabili per impostazione predefinita. Tra queste sono incluse:

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

Per un esempio di come creare un'associazione personalizzata che supporta sessioni affidabili, vedere [procedura: creare un'associazione di sessione affidabile personalizzata con https](how-to-create-a-custom-reliable-session-binding-with-https.md).

## <a name="see-also"></a>Vedere anche

- [Sessioni affidabili](reliable-sessions.md)

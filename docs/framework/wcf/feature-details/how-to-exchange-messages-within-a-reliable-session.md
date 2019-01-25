---
title: 'Procedura: Scambiare messaggi in una sessione affidabile'
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 0b03845f9638a3646c72b1210de12dd94cf4cc9f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720054"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a>Procedura: Scambiare messaggi in una sessione affidabile

In questo argomento vengono delineati i passaggi necessari per attivare una sessione affidabile utilizzando una delle associazioni fornite dal sistema che supportano tale sessione, ma non per impostazione predefinita. Si attiva una sessione affidabile in modo imperativo tramite codice o in modo dichiarativo nel file di configurazione. Questa procedura Usa i file di configurazione client e servizio per abilitare la sessione affidabile e stabilire che i messaggi arrivino nello stesso ordine in cui sono stati inviati.

La parte principale di questa procedura è che l'elemento di configurazione endpoint contenga un `bindingConfiguration` attributo che fa riferimento a una configurazione di associazione denominata `Binding1`. Il [  **\<associazione >** ](../../../../docs/framework/misc/binding.md) elemento di configurazione fa riferimento a questo nome per attivare sessioni affidabili impostando il `enabled` attributo del [  **\<reliableSession >** ](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) elemento `true`. Le garanzie di recapito ordinato per la sessione affidabile vengono specificate impostando l'attributo `ordered` su `true`.

Per la copia di origine di questo esempio, vedere [sessioni affidabili WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il servizio con una classe WSHttpBinding per utilizzare una sessione affidabile

1. Definire un contratto di servizio per il tipo di servizio.

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. Implementare il contratto di servizio in una classe del servizio. Si noti che le informazioni di indirizzo o il binding non sono specificate nell'implementazione del servizio. Non è necessario scrivere codice per recuperare le informazioni di indirizzo o il binding dal file di configurazione.

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. Creare un *Web. config* file per configurare un endpoint per il `CalculatorService` che utilizza il <xref:System.ServiceModel.WSHttpBinding> con sessione affidabile attivata e recapito ordinato dei messaggi obbligatorio.

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. Creare un *Service. svc* file che contiene la riga:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1.  Sul posto di *Service. svc* file nella directory virtuale di Internet Information Services (IIS).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il client con una classe WSHttpBinding per utilizzare una sessione affidabile

1. Usare la [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) dalla riga di comando per generare codice dai metadati del servizio:

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Il client generato contiene le `ICalculator` interfaccia che definisce il contratto di servizio che l'implementazione client deve soddisfare.

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. L'applicazione client generata contiene inoltre l'implementazione di `ClientCalculator`. Si noti che le informazioni di associazione e indirizzo non sono specificate nell'implementazione del servizio. Non è necessario scrivere codice per recuperare le informazioni di indirizzo o il binding dal file di configurazione.

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. *Svcutil.exe* genera anche la configurazione per il client che utilizza il <xref:System.ServiceModel.WSHttpBinding> classe. Denominare il file di configurazione *app. config* quando si usa Visual Studio.

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. Creare un'istanza di `ClientCalculator` in un'applicazione e chiamare le operazioni del servizio.

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. Compilare ed eseguire il client.

## <a name="example"></a>Esempio

Diverse associazioni fornite dal sistema supportano sessioni affidabili per impostazione predefinita. Sono inclusi:

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

Per un esempio di come creare un'associazione personalizzata che supporta sessioni affidabili, vedere [come: Creare un'associazione di sessione affidabile personalizzata con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).

## <a name="see-also"></a>Vedere anche

- [Sessioni affidabili](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)

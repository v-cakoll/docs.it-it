---
title: 'Procedura: scambiare messaggi in una sessione affidabile'
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 80dea8545e9d813e68e67414151e2c96537db2e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491826"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a>Procedura: scambiare messaggi in una sessione affidabile

In questo argomento vengono delineati i passaggi necessari per attivare una sessione affidabile utilizzando una delle associazioni fornite dal sistema che supportano tale sessione, ma non per impostazione predefinita. Si attiva una sessione affidabile in modo imperativo tramite codice o in modo dichiarativo nel file di configurazione. Questa procedura utilizza i file di configurazione di client e il servizio per attivare la sessione affidabile e stabilire che i messaggi arrivino nello stesso ordine in cui sono stati inviati.

La parte principale di questa procedura è l'elemento di configurazione dell'endpoint che contiene un `bindingConfiguration` attributo che fa riferimento a una configurazione di associazione denominata `Binding1`. Il [  **\<associazione >** ](../../../../docs/framework/misc/binding.md) elemento di configurazione fa riferimento a questo nome per abilitare sessioni affidabili impostando il `enabled` attributo del [  **\<reliableSession >** ](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) elemento `true`. Le garanzie di recapito ordinato per la sessione affidabile vengono specificate impostando l'attributo `ordered` su `true`.

Per la copia di origine di questo esempio, vedere [sessione affidabile WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il servizio con una classe WSHttpBinding per utilizzare una sessione affidabile

1. Definire un contratto di servizio per il tipo di servizio.

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. Implementare il contratto di servizio in una classe del servizio. Si noti che le informazioni di indirizzo o il binding non sono specificate nell'implementazione del servizio. Non si è necessario scrivere codice per recuperare le informazioni di indirizzo o il binding dal file di configurazione.

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. Creare un *Web. config* file per configurare un endpoint per il `CalculatorService` che utilizza il <xref:System.ServiceModel.WSHttpBinding> con sessione affidabile attivata e recapito ordinato dei messaggi necessari.

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. Creare un *Service.svc* file che contiene la riga:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1.  Sul posto di *Service.svc* file nella directory virtuale di Internet Information Services (IIS).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurare il client con una classe WSHttpBinding per utilizzare una sessione affidabile

1. Utilizzare il [strumento ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) dalla riga di comando per generare codice dai metadati del servizio:

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Il client generato contiene il `ICalculator` interfaccia che definisce il contratto di servizio che l'implementazione client deve soddisfare.

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. L'applicazione client generata contiene inoltre l'implementazione di `ClientCalculator`. Si noti che le informazioni di associazione e indirizzo non sono specificate in un punto qualsiasi nell'implementazione del servizio. Non si è necessario scrivere codice per recuperare le informazioni di indirizzo o il binding dal file di configurazione.

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. *Svcutil.exe* genera inoltre la configurazione per il client che utilizza il <xref:System.ServiceModel.WSHttpBinding> classe. Denominare il file di configurazione *app. config* quando si utilizza Visual Studio.

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. Creare un'istanza di `ClientCalculator` in un'applicazione e chiamare le operazioni del servizio.

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. Compilare ed eseguire il client.

## <a name="example"></a>Esempio

Diverse associazioni fornite dal sistema supportano sessioni affidabili per impostazione predefinita. Sono inclusi:

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

Per un esempio di come creare un'associazione personalizzata che supporta le sessioni affidabili, vedere [procedura: creare un'associazione di sessione affidabile personalizzata con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).

## <a name="see-also"></a>Vedere anche

[Sessioni affidabili](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)

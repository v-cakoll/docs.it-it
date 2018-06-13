---
title: "Procedura: creare un'associazione di sessione affidabile personalizzata con HTTPS"
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: b3699593f783fff1227ec51194956e0cc8577dd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492762"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a>Procedura: creare un'associazione di sessione affidabile personalizzata con HTTPS

In questo argomento viene illustrato l'uso della protezione del trasporto SSL (Secure Sockets Layer) con sessioni affidabili. Per usare una sessione affidabile su HTTPS è necessario creare un'associazione personalizzata che usa una sessione affidabile e il trasporto HTTPS. Attivare la sessione affidabile in modo imperativo tramite codice o in modo dichiarativo nel file di configurazione. Questa procedura utilizza i file di configurazione di client e il servizio per attivare la sessione affidabile e [  **\<httpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) elemento.

La parte principale di questa procedura è che il  **\<endpoint >** elemento di configurazione contenga una `bindingConfiguration` attributo che fa riferimento a una configurazione di associazione personalizzata denominata `reliableSessionOverHttps`. Il [  **\<associazione >** ](../../../../docs/framework/misc/binding.md) elemento di configurazione fa riferimento a questo nome per specificare che viene utilizzata una sessione affidabile e il trasporto HTTPS includendo  **\< reliableSession >** e  **\<httpsTransport >** elementi.

Per la copia di origine di questo esempio, vedere [personalizzato associazione di sessione affidabile su HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Configurare il servizio con una CustomBinding per usare una sessione affidabile con HTTPS

1. Definire un contratto di servizio per il tipo di servizio.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. Implementare il contratto di servizio in una classe del servizio. Si noti che le informazioni di indirizzo o il binding non sono specificate nell'implementazione del servizio. Non si è necessaria per scrivere codice per recuperare le informazioni di indirizzo o il binding dal file di configurazione.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. Creare un *Web. config* file per configurare un endpoint per il `CalculatorService` con un'associazione personalizzata denominata `reliableSessionOverHttps` che utilizza una sessione affidabile e il trasporto HTTPS.

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. Creare un *Service.svc* file che contiene la riga:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. Sul posto di *Service.svc* file nella directory virtuale di Internet Information Services (IIS).

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Configurare il client con una CustomBinding per usare una sessione affidabile con HTTPS

1. Utilizzare il [strumento ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) dalla riga di comando per generare codice dai metadati del servizio.

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Il client generato contiene il `ICalculator` interfaccia che definisce il contratto di servizio che l'implementazione client deve soddisfare.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. L'applicazione client generata contiene inoltre l'implementazione di `ClientCalculator`. Si noti che le informazioni di associazione e indirizzo non sono specificate nell'implementazione del servizio. Non si è necessaria per scrivere codice per recuperare le informazioni di associazione e indirizzo dal file di configurazione.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. Configurare un'associazione personalizzata denominata `reliableSessionOverHttps` come utilizzare il trasporto HTTPS e sessioni affidabili.

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. Creare un'istanza di `ClientCalculator` in un'applicazione, quindi chiamare le operazioni del servizio.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. Compilare ed eseguire il client.  

## <a name="net-framework-security"></a>.NET Framework (sicurezza)

Poiché il certificato utilizzato in questo esempio è un certificato di prova creato con *Makecert.exe*, viene visualizzato un avviso di sicurezza quando si tenta di accedere a un indirizzo HTTPS, ad esempio `https://localhost/servicemodelsamples/service.svc`, dal browser.

## <a name="see-also"></a>Vedere anche

[Sessioni affidabili](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)

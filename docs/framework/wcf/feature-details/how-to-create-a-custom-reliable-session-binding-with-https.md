---
title: "Procedura: creare un'associazione di sessione affidabile personalizzata con HTTPS"
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: 70f8f4f33626ab0d1705e03750bfd9baa324e60a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598996"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a>Procedura: creare un'associazione di sessione affidabile personalizzata con HTTPS

In questo argomento viene illustrato l'uso della protezione del trasporto SSL (Secure Sockets Layer) con sessioni affidabili. Per usare una sessione affidabile su HTTPS è necessario creare un'associazione personalizzata che usa una sessione affidabile e il trasporto HTTPS. La sessione affidabile può essere abilitata in modo imperativo tramite codice o in modo dichiarativo nel file di configurazione. Questa procedura usa i file di configurazione del client e del servizio per abilitare la sessione affidabile e l' [**\<httpsTransport>**](../../configure-apps/file-schema/wcf/httpstransport.md) elemento.

La parte principale di questa procedura è che l' **\<endpoint>** elemento di configurazione contiene un `bindingConfiguration` attributo che fa riferimento a una configurazione di binding personalizzata denominata `reliableSessionOverHttps` . L' [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) elemento di configurazione fa riferimento a questo nome per specificare che una sessione affidabile e il trasporto HTTPS vengono utilizzati includendo **\<reliableSession>** **\<httpsTransport>** gli elementi e.

Per la copia di origine di questo esempio, vedere [Custom Binding Reliable Session over HTTPS](../samples/custom-binding-reliable-session-over-https.md).

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Configurare il servizio con un CustomBinding per usare una sessione affidabile con HTTPS

1. Definire un contratto di servizio per il tipo di servizio.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. Implementare il contratto di servizio in una classe del servizio. Si noti che le informazioni sull'indirizzo o sull'associazione non sono specificate nell'implementazione del servizio. Non è necessario scrivere codice per recuperare l'indirizzo o le informazioni di binding dal file di configurazione.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. Creare un file *Web. config* per configurare un endpoint per `CalculatorService` con un'associazione personalizzata denominata `reliableSessionOverHttps` che utilizza una sessione affidabile e il trasporto HTTPS.

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. Creare un file *Service. svc* contenente la riga:

   `<%@ServiceHost language=c# Service="CalculatorService" %>`

1. Inserire il file *Service. svc* nella directory virtuale Internet Information Services (IIS).

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Configurare il client con un CustomBinding per usare una sessione affidabile con HTTPS

1. Utilizzare lo [strumento ServiceModel Metadata Utility Tool (*Svcutil. exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) dalla riga di comando per generare codice dai metadati del servizio.

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Il client generato contiene l' `ICalculator` interfaccia che definisce il contratto di servizio che l'implementazione client deve soddisfare.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. L'applicazione client generata contiene inoltre l'implementazione di `ClientCalculator`. Si noti che le informazioni sull'indirizzo e sull'associazione non sono specificate nell'implementazione del servizio. Non è necessario scrivere codice per recuperare l'indirizzo e le informazioni di binding dal file di configurazione.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. Configurare un'associazione personalizzata denominata `reliableSessionOverHttps` per utilizzare il trasporto HTTPS e le sessioni affidabili.

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. Creare un'istanza di `ClientCalculator` in un'applicazione, quindi chiamare le operazioni del servizio.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. Compilare ed eseguire il client.  

## <a name="net-framework-security"></a>.NET Framework (sicurezza)

Poiché il certificato utilizzato in questo esempio è un certificato di prova creato con *Makecert. exe*, viene visualizzato un avviso di sicurezza quando si tenta di accedere a un indirizzo https, ad esempio `https://localhost/servicemodelsamples/service.svc` , dal browser.

## <a name="see-also"></a>Vedere anche

- [Sessioni affidabili](reliable-sessions.md)

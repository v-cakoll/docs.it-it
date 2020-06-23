---
title: 'Procedura: proteggere un servizio con credenziali di Windows'
description: Informazioni su come abilitare la sicurezza del trasporto in un servizio WCF che risiede in un dominio Windows e che viene chiamato dai client nello stesso dominio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
ms.assetid: d171b5ca-96ef-47ff-800c-c138023cf76e
ms.openlocfilehash: 8ef164e1475bfd5f047a99426a2bed43a7aa7353
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244633"
---
# <a name="how-to-secure-a-service-with-windows-credentials"></a>Procedura: proteggere un servizio con credenziali di Windows

In questo argomento viene illustrato come abilitare la sicurezza del trasporto in un servizio Windows Communication Foundation (WCF) che risiede in un dominio di Windows e viene chiamato dai client nello stesso dominio. Per ulteriori informazioni su questo scenario, vedere [sicurezza del trasporto con l'autenticazione di Windows](./feature-details/transport-security-with-windows-authentication.md). Per un'applicazione di esempio, vedere l'esempio [wsHttpBinding](./samples/wshttpbinding.md) .

In questo argomento si presuppone la presenza di un'interfaccia e di un'implementazione del contratto esistente già definite, alle quali vengono aggiunti elementi. È inoltre possibile modificare un servizio e un client esistenti.

È possibile proteggere un servizio con credenziali di Windows completamente nel codice. In alternativa, è possibile omettere parte del codice tramite un file di configurazione. In questo argomento vengono illustrate entrambe le modalità. Accertarsi di usare una sola modalità, non entrambe.

Nelle prime tre procedure viene illustrato come proteggere il servizio tramite il codice. Nella quarta e nella quinta procedura viene illustrato come eseguire questa operazione con un file di configurazione.

## <a name="using-code"></a>Uso del codice

Il codice completo per il servizio e il client si trova nella sezione Esempio alla fine di questo argomento.

Nella prima procedura vengono illustrate la creazione e la configurazione di una classe <xref:System.ServiceModel.WSHttpBinding> nel codice. Per l'associazione viene usata il trasporto HTTP. La stessa associazione viene usata nel client.

#### <a name="to-create-a-wshttpbinding-that-uses-windows-credentials-and-message-security"></a>Per creare un oggetto WSHttpBinding che usa le credenziali di Windows e la protezione dei messaggio

1. Il codice di questa procedura viene inserito all'inizio del metodo `Run` della classe `Test` nel codice del servizio riportato nella sezione Esempio.

2. Creare un'istanza della classe <xref:System.ServiceModel.WSHttpBinding>.

3. Impostare la proprietà <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> della classe <xref:System.ServiceModel.WSHttpSecurity> su <xref:System.ServiceModel.SecurityMode.Message>.

4. Impostare la proprietà <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> della classe <xref:System.ServiceModel.MessageSecurityOverHttp> su <xref:System.ServiceModel.MessageCredentialType.Windows>.

5. Il codice per questa procedura è il seguente:

    [!code-csharp[c_SecureWindowsService#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#1)]
    [!code-vb[c_SecureWindowsService#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#1)]

### <a name="using-the-binding-in-a-service"></a>Uso dell'associazione in un servizio.

Si tratta della seconda procedura, in cui viene illustrato l'uso dell'associazione in un servizio self-hosted. Per ulteriori informazioni sui servizi di hosting, vedere [servizi di hosting](hosting-services.md).

##### <a name="to-use-a-binding-in-a-service"></a>Per usare un'associazione in un servizio

1. Inserire il codice di questa procedura dopo il codice della procedura precedente.

2. Creare una variabile <xref:System.Type> denominata `contractType` e assegnarle il tipo dell'interfaccia (`ICalculator`). Quando si usa Visual Basic, usare l' `GetType` operatore. quando si usa C#, usare la `typeof` parola chiave.

3. Creare una seconda variabile <xref:System.Type> denominata `serviceType` e assegnarle il tipo del contratto implementato (`Calculator`).

4. Creare un'istanza della classe <xref:System.Uri> denominata `baseAddress` con l'indirizzo di base del servizio. L'indirizzo di base deve avere uno schema corrispondente al trasporto. In questo caso, lo schema di trasporto è HTTP e l'indirizzo include il Uniform Resource Identifier speciale (URI) "localhost" e un numero di porta (8036), nonché un indirizzo endpoint di base ("serviceModelSamples/): `http://localhost:8036/serviceModelSamples/` .

5. Creare un'istanza della classe <xref:System.ServiceModel.ServiceHost> class con le variabili `serviceType` e `baseAddress`.

6. Aggiungere un endpoint al servizio tramite l'interfaccia `contractType`, l'associazione e un nome di endpoint (secureCalculator). Un client deve concatenare l'indirizzo di base e il nome dell'endpoint quando avvia una chiamata al servizio.

7. Chiamare il metodo <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> per avviare il servizio. Il codice per questa procedura viene illustrato di seguito:

    [!code-csharp[c_SecureWindowsService#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#2)]
    [!code-vb[c_SecureWindowsService#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#2)]

### <a name="using-the-binding-in-a-client"></a>Uso dell'associazione in un client

In questa procedura viene illustrato come generare un proxy che comunica con il servizio. Il proxy viene generato con lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) che usa i metadati del servizio per creare il proxy.

In questa procedura viene anche creata un'istanza della classe <xref:System.ServiceModel.WSHttpBinding> per comunicare con il servizio, quindi viene chiamato il servizio.

In questo esempio, per creare il client viene usato solo codice. In alternativa, è possibile usare un file di configurazione, illustrato nella sezione successiva a questa procedura.

#### <a name="to-use-a-binding-in-a-client-with-code"></a>Per usare un'associazione in un client con codice

1. Usare lo strumento SvcUtil.exe per generare il codice del proxy tramite i metadati del servizio. Per altre informazioni, vedere [How to: Create a client](how-to-create-a-wcf-client.md). Il codice proxy generato eredita dalla <xref:System.ServiceModel.ClientBase%601> classe, che garantisce che ogni client disponga dei costruttori, dei metodi e delle proprietà necessari per comunicare con un servizio WCF. In questo esempio, il codice generato include la classe `CalculatorClient` che implementa l'interfaccia `ICalculator`, consentendo la compatibilità con il codice del servizio.

2. Il codice di questa procedura viene inserito all'inizio del metodo `Main` del programma client.

3. Creare un'istanza della classe <xref:System.ServiceModel.WSHttpBinding> e impostarne la modalità di sicurezza su `Message` e il tipo di credenziale client su `Windows`. Nell'esempio viene denominata la variabile `clientBinding`.

4. Creare un'istanza della classe <xref:System.ServiceModel.EndpointAddress> denominata `serviceAddress`. Inizializzare l'istanza con l'indirizzo di base concatenato al nome dell'endpoint.

5. Creare un'istanza della classe client generata con le variabili `serviceAddress` e `clientBinding`.

6. Chiamare il metodo <xref:System.ServiceModel.ClientBase%601.Open%2A>, come mostrato nel codice seguente.

7. Chiamare il servizio e visualizzare i risultati.

    [!code-csharp[c_secureWindowsClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#1)]
    [!code-vb[c_secureWindowsClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#1)]

## <a name="using-the-configuration-file"></a>Uso del file di configurazione

Anziché creare l'associazione con codice procedurale, è possibile usare il codice seguente illustrato per la sezione dell'associazione del file di configurazione.

Se non è già stato definito un servizio, vedere [progettazione e implementazione di servizi](designing-and-implementing-services.md)e [configurazione dei servizi](configuring-services.md).

> [!NOTE]
> Questo codice di configurazione viene usato nei file di configurazione del servizio e del client.

#### <a name="to-enable-transfer-security-on-a-service-in-a-windows-domain-using-configuration"></a>Per abilitare la protezione del trasferimento in un servizio in un dominio Windows usando la configurazione

1. Aggiungere un [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elemento alla [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) sezione dell'elemento del file di configurazione.

2. Aggiungere un `binding` elemento <> all'elemento <`WSHttpBinding`> e impostare l' `configurationName` attributo su un valore appropriato per l'applicazione.

3. Aggiungere un `security` elemento <> e impostare l' `mode` attributo su Message.

4. Aggiungere un `message` elemento <> e impostare l' `clientCredentialType` attributo su Windows.

5. Nel file di configurazione del servizio, sostituire la sezione `<bindings>` con il codice seguente. Se non si dispone già di un file di configurazione del servizio, vedere [utilizzo delle associazioni per configurare servizi e client](using-bindings-to-configure-services-and-clients.md).

    ```xml
    <bindings>
      <wsHttpBinding>
       <binding name = "wsHttpBinding_Calculator">
         <security mode="Message">
           <message clientCredentialType="Windows"/>
         </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    ```

### <a name="using-the-binding-in-a-client"></a>Uso dell'associazione in un client

In questa procedura viene illustrato come generare due file, un proxy che comunica con il servizio e un file di configurazione. Vengono inoltre descritte le modifiche apportate al programma client, ovvero il terzo file usato nel client.

#### <a name="to-use-a-binding-in-a-client-with-configuration"></a>Per usare un'associazione in un client con configurazione

1. Usare lo strumento SvcUtil.exe per generare il codice proxy e il file di configurazione tramite i metadati del servizio. Per altre informazioni, vedere [How to: Create a client](how-to-create-a-wcf-client.md).

2. Sostituire la [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) sezione del file di configurazione generato con il codice di configurazione della sezione precedente.

3. Il codice procedurale viene inserito all'inizio del metodo `Main` del programma client.

4. Creare un'istanza della classe client generata che passi il nome dell'associazione nel file di configurazione come parametro di input.

5. Chiamare il metodo <xref:System.ServiceModel.ClientBase%601.Open%2A>, come mostrato nel codice seguente.

6. Chiamare il servizio e visualizzare i risultati.

    [!code-csharp[c_secureWindowsClient#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#2)]

## <a name="example"></a>Esempio

[!code-csharp[c_SecureWindowsService#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#0)]

[!code-csharp[c_SecureWindowsClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#0)]
[!code-vb[c_SecureWindowsClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#0)]

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.WSHttpBinding>
- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Procedura: Creare un client](how-to-create-a-wcf-client.md)
- [Protezione dei servizi](securing-services.md)
- [Panoramica della sicurezza](./feature-details/security-overview.md)

---
title: "Procedura: ospitare un servizio WCF in un'applicazione gestita"
description: Informazioni su come ospitare un servizio WCF all'interno di un'applicazione gestita creando un servizio indipendente ed eseguendone il test.
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 7d1d61b683f60a6c643d2a2f03d367a6ae6c6c15
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246168"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a>Procedura: ospitare un servizio WCF in un'app gestita

Per ospitare un servizio all'interno di un'applicazione gestita, incorporare il codice per il servizio nel codice dell'applicazione, definire un endpoint per il servizio in modo imperativo nel codice, in modo dichiarativo tramite la configurazione o tramite endpoint predefiniti, quindi creare un'istanza di <xref:System.ServiceModel.ServiceHost>.

Per iniziare a ricevere messaggi, chiamare <xref:System.ServiceModel.ICommunicationObject.Open%2A> su <xref:System.ServiceModel.ServiceHost>. In tal modo viene creato e aperto il listener per il servizio. Questo tipo di hosting di un servizio viene spesso chiamato "self-hosting"" perché è la stessa applicazione gestita a svolgere il lavoro di hosting. Per chiudere il servizio, chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.ServiceHost>.

Un servizio può essere ospitato anche in un servizio Windows gestito, in Internet Information Services (IIS) o nel servizio Attivazione processo Windows (WAS). Per ulteriori informazioni sulle opzioni di hosting per un servizio, vedere [Hosting Services](hosting-services.md).

L'hosting di un servizio in un'applicazione gestita è l'opzione più flessibile perché richiede la distribuzione di un'infrastruttura minima. Per ulteriori informazioni sui servizi di hosting nelle applicazioni gestite, vedere [hosting in un'applicazione gestita](./feature-details/hosting-in-a-managed-application.md).

Nella procedura seguente viene illustrato come implementare un servizio indipendente in un'applicazione console.

## <a name="create-a-self-hosted-service"></a>Creazione di un servizio self-hosted

1. Creare una nuova applicazione console:

   1. Aprire Visual Studio e scegliere **nuovo**  >  **progetto** dal menu **file** .

   2. Nell'elenco **modelli installati** selezionare **Visual C#** o **Visual Basic**, quindi selezionare **desktop di Windows**.

   3. Selezionare il modello **applicazione console** . Digitare `SelfHost` nella casella **nome** , quindi scegliere **OK**.

2. Fare clic con il pulsante destro del mouse su **SelfHost** in **Esplora soluzioni** e scegliere **Aggiungi riferimento**. Selezionare **System. ServiceModel** dalla scheda **.NET** , quindi scegliere **OK**.

    > [!TIP]
    > Se la finestra **Esplora soluzioni** non è visibile, selezionare **Esplora soluzioni** dal menu **Visualizza** .

3. Fare doppio clic su **Program.cs** o **Module1. vb** in **Esplora soluzioni** per aprirlo nella finestra del codice, se non è già aperto. Aggiungere le seguenti istruzioni all'inizio del file:

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. Definire e implementare un contratto di servizio. In questo esempio viene definito un codice `HelloWorldService` che restituisce un messaggio in base all'input del servizio.

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > Per altre informazioni su come definire e implementare un'interfaccia del servizio, vedere [procedura: definire un contratto di servizio](how-to-define-a-wcf-service-contract.md) e [procedura: implementare un contratto di servizio](how-to-implement-a-wcf-contract.md).

5. All'inizio del metodo `Main`, creare un'istanza della classe <xref:System.Uri> con l'indirizzo di base del servizio.

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. Creare un'istanza della classe <xref:System.ServiceModel.ServiceHost>, passando un <xref:System.Type> che rappresenta il tipo di servizio e l'URI (Uniform Resource Identifier) dell'indirizzo di base a <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>. Abilitare la pubblicazione dei metadati, quindi chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A> sull'oggetto <xref:System.ServiceModel.ServiceHost> per inizializzare il servizio e prepararlo a ricevere messaggi.

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > In questo esempio vengono utilizzati endpoint predefiniti e per il servizio non è necessario alcun file di configurazione. Se non è specificato alcun endpoint, il runtime ne crea uno per ogni indirizzo di base per ciascun contratto di servizio implementato dal servizio. Per ulteriori informazioni sugli endpoint predefiniti, vedere [Configurazione semplificata](simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](./samples/simplified-configuration-for-wcf-services.md).

7. Premere **CTRL** + **MAIUSC** + **B** per compilare la soluzione.

## <a name="test-the-service"></a>Testare il servizio

1. Premere **CTRL** + **F5** per eseguire il servizio.

2. Aprire il **client di prova WCF**.

    > [!TIP]
    > Per aprire il **client di prova WCF**, aprire prompt dei comandi per gli sviluppatori per Visual Studio ed eseguire **WcfTestClient.exe**.

3. Scegliere **Aggiungi servizio** dal menu **file** .

4. Digitare `http://localhost:8080/hello` nella casella Address, quindi fare clic su **OK**.

    > [!TIP]
    > Verificare che il servizio sia in esecuzione. In caso contrario, il passaggio non viene eseguito. Se nel codice è stato modificato l'indirizzo di base, in questo passaggio utilizzare l'indirizzo di base modificato.

5. Fare doppio clic su **sayHello** nel nodo **progetti di servizio** . Digitare il nome nella colonna **valore** nell'elenco **richiesta** e fare clic su **richiama**.

   Un messaggio di risposta viene visualizzato nell'elenco **risposta** .

## <a name="example"></a>Esempio

Nell'esempio seguente viene creato un oggetto <xref:System.ServiceModel.ServiceHost> per ospitare un servizio di tipo `HelloWorldService`, quindi viene chiamato il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A> su <xref:System.ServiceModel.ServiceHost>. Nel codice viene fornito un indirizzo di base, viene abilitata la pubblicazione di metadati e vengono utilizzati endpoint predefiniti.

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [Procedura: ospitare un servizio WCF in IIS](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [Servizio indipendente](./samples/self-host.md)
- [Servizi di hosting](hosting-services.md)
- [Procedura: Definire un contratto di servizio](how-to-define-a-wcf-service-contract.md)
- [Procedura: Implementare un contratto di servizio](how-to-implement-a-wcf-contract.md)
- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Uso di associazioni per configurare servizi e client](using-bindings-to-configure-services-and-clients.md)
- [Associazioni fornite dal sistema](system-provided-bindings.md)

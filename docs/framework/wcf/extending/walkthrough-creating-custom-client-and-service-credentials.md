---
title: 'Procedura dettagliata: Creazione di credenziali client e del servizio personalizzate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b5ba5c3-0c6c-48e9-9e46-54acaec443ba
ms.openlocfilehash: d49df909521b3b5e5cf509c1367821856e91e30b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795478"
---
# <a name="walkthrough-creating-custom-client-and-service-credentials"></a>Procedura dettagliata: Creazione di credenziali client e del servizio personalizzate

In questo argomento viene illustrato come implementare credenziali client e del servizio personalizzate e come utilizzare credenziali personalizzate dal codice dell'applicazione.

## <a name="credentials-extensibility-classes"></a>Classi di estensibilità delle credenziali

Le <xref:System.ServiceModel.Description.ClientCredentials> classi <xref:System.ServiceModel.Description.ServiceCredentials> e sono i punti di ingresso principali per l'estendibilità di sicurezza Windows Communication Foundation (WCF). Queste classi delle credenziali forniscono le API che consentono al codice dell'applicazione di impostare le informazioni sulle credenziali e convertire i tipi di credenziali in token di sicurezza. I*token di sicurezza* sono il formato utilizzato per trasmettere le informazioni sulle credenziali all'interno di messaggi SOAP. Le responsabilità di queste classi di credenziali possono essere divise in due aree:

- Fornire le API affinché le applicazioni impostino le informazioni sulle credenziali.

- Fungere da factory per le implementazioni <xref:System.IdentityModel.Selectors.SecurityTokenManager>.

Le implementazioni predefinite fornite in WCF supportano i tipi di credenziali forniti dal sistema e creano un gestore del token di sicurezza in grado di gestire tali tipi di credenziali.

## <a name="reasons-to-customize"></a>Motivi di personalizzazione

Esistono più motivi per personalizzare classi di credenziali client o del servizio. Per prima cosa è necessario modificare il comportamento di sicurezza predefinito di WCF per quanto riguarda la gestione dei tipi di credenziali forniti dal sistema, in particolare per i motivi seguenti:

- Necessità di modifiche che non sono possibili utilizzando altri punti di estensibilità.

- Aggiunta di nuovi tipi di credenziali.

- Aggiunta di nuovi tipi di token di sicurezza personalizzati.

In questo argomento viene illustrato come implementare credenziali client e del servizio personalizzate e come utilizzarle dal codice dell'applicazione.

## <a name="first-in-a-series"></a>Primo passaggio

La creazione di una classe di credenziali personalizzate è solo il primo passaggio, perché il motivo per la personalizzazione delle credenziali consiste nel modificare il comportamento WCF relativo al provisioning delle credenziali, alla serializzazione dei token di sicurezza o all'autenticazione. Negli altri argomenti di questa sezione viene descritto come creare serializzatori e autenticatori personalizzati. In questo caso, la creazione di una classe di credenziali personalizzate è il primo tema dei passaggi. Le azioni successive (creazione di serializzatori e autenticatori personalizzati) possono essere eseguite solo dopo avere creato credenziali personalizzate. Gli argomenti aggiuntivi basati su questo argomento includono:

- [Procedura: Creare un provider di token di sicurezza personalizzato](how-to-create-a-custom-security-token-provider.md)

- [Procedura: Creare un autenticatore del token di sicurezza personalizzato](how-to-create-a-custom-security-token-authenticator.md)

- [Procedura: Creare un token](how-to-create-a-custom-token.md)personalizzato.

## <a name="procedures"></a>Procedure

#### <a name="to-implement-custom-client-credentials"></a>Per implementare le credenziali client personalizzate

1. Definire una nuova classe derivata dalla classe <xref:System.ServiceModel.Description.ClientCredentials>.

2. facoltativo. Aggiungere nuovi metodi o proprietà per nuovi tipi di credenziali. Se non vengono aggiunti nuovi tipi di credenziali, ignorare questo passaggio. Nell'esempio seguente viene aggiunta una proprietà `CreditCardNumber`.

3. Eseguire l'override del metodo <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> . Questo metodo viene chiamato automaticamente dall'infrastruttura di sicurezza WCF quando viene utilizzata la credenziale client personalizzata. Questo metodo è responsabile della creazione e della restituzione di un'istanza di un'implementazione della classe <xref:System.IdentityModel.Selectors.SecurityTokenManager>.

    > [!IMPORTANT]
    > È importante da notare che l'override del metodo <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> viene eseguito per creare un gestore del token di sicurezza personalizzato. Il gestore del token di sicurezza, derivato da <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> deve restituire un provider del token di sicurezza personalizzato, derivato da <xref:System.IdentityModel.Selectors.SecurityTokenProvider>, per creare il token di sicurezza effettivo. Se non si segue questo modello per creare token di sicurezza, l'applicazione potrebbe funzionare in modo non corretto quando gli oggetti <xref:System.ServiceModel.ChannelFactory> vengono memorizzati nella cache (comportamento predefinito dei proxy client WCF), provocando un potenziale attacco di tipo elevazione dei privilegi. L'oggetto credenziale personalizzata viene memorizzato nella cache come parte dell'oggetto <xref:System.ServiceModel.ChannelFactory>. L'oggetto <xref:System.IdentityModel.Selectors.SecurityTokenManager> personalizzato viene creato tuttavia a ogni chiamata in modo da limitare la minaccia alla sicurezza se la logica di creazione del token è presente nell'oggetto <xref:System.IdentityModel.Selectors.SecurityTokenManager>.

4. Eseguire l'override del metodo <xref:System.ServiceModel.Description.ClientCredentials.CloneCore%2A> .

    [!code-csharp[c_CustomCredentials#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#1)]
    [!code-vb[c_CustomCredentials#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#1)]

#### <a name="to-implement-a-custom-client-security-token-manager"></a>Per implementare un gestore del token di sicurezza client personalizzato

1. Definire una nuova classe derivata da <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>.

2. facoltativo. Eseguire l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> se è necessario creare un'implementazione <xref:System.IdentityModel.Selectors.SecurityTokenProvider> personalizzata. Per ulteriori informazioni sui provider di token di sicurezza personalizzati [, vedere Procedura: Creare un provider](how-to-create-a-custom-security-token-provider.md)di token di sicurezza personalizzato.

3. facoltativo. Eseguire l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%28System.IdentityModel.Selectors.SecurityTokenRequirement%2CSystem.IdentityModel.Selectors.SecurityTokenResolver%40%29> se è necessario creare un'implementazione <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> personalizzata. Per ulteriori informazioni sugli autenticatori del token di sicurezza personalizzati [, vedere Procedura: Creare un autenticatore](how-to-create-a-custom-security-token-authenticator.md)del token di sicurezza personalizzato.

4. facoltativo. Eseguire l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%2A> se è necessario creare un oggetto <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> personalizzato. Per ulteriori informazioni sui token di sicurezza personalizzati e sui serializzatori di token di sicurezza [personalizzati, vedere Procedura: Creare un token](how-to-create-a-custom-token.md)personalizzato.

    [!code-csharp[c_CustomCredentials#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#2)]
    [!code-vb[c_CustomCredentials#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#2)]

#### <a name="to-use-a-custom-client-credentials-from-application-code"></a>Per utilizzare credenziali client personalizzate dal codice dell'applicazione

1. Creare un'istanza del client generato che rappresenta l'interfaccia del servizio oppure creare un'istanza di <xref:System.ServiceModel.ChannelFactory> che punta a un servizio con il quale si desidera comunicare.

2. Rimuovere il comportamento delle credenziali client fornite dal sistema dalla raccolta <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>, alla quale è possibile accedere tramite la proprietà <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>.

3. Creare una nuova istanza di una classe di credenziali client personalizzate e aggiungerla alla raccolta <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>, alla quale è possibile accedere tramite la proprietà <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>.

    [!code-csharp[c_CustomCredentials#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#3)]
    [!code-vb[c_CustomCredentials#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#3)]

Nella procedura precedente viene illustrato come utilizzare credenziali client dal codice dell'applicazione. Le credenziali WCF possono essere configurate anche utilizzando il file di configurazione dell'applicazione. Spesso è preferibile utilizzare la configurazione dell'applicazione anziché la specifica a livello di codice, perché consente di modificare i parametri dell'applicazione senza dovere modificare l'origine, ricompilare e ridistribuire.

Nella prossima procedura viene illustrato come fornire supporto per la configurazione di credenziali personalizzate.

#### <a name="creating-a-configuration-handler-for-custom-client-credentials"></a>Creazione di un gestore di configurazione per credenziali client personalizzate

1. Definire una nuova classe derivata da <xref:System.ServiceModel.Configuration.ClientCredentialsElement>.

2. facoltativo. Aggiungere proprietà per tutti i parametri di configurazione aggiuntivi che si desidera esporre tramite la configurazione dell'applicazione. Nell'esempio seguente viene aggiunta una proprietà denominata `CreditCardNumber`.

3. Eseguire l'override della proprietà <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.BehaviorType%2A> per restituire il tipo di classe di credenziali client personalizzate creata con l'elemento di configurazione.

4. Eseguire l'override del metodo <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.CreateBehavior%2A> . Il metodo è responsabile della creazione e restituzione di un'istanza della classe di credenziali personalizzati basata sulle impostazioni caricate dal file di configurazione. Chiamare il metodo <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ApplyConfiguration%28System.ServiceModel.Description.ClientCredentials%29> di base da questo metodo per recuperare le impostazioni delle credenziali fornite dal sistema caricate nell'istanza delle credenziali client personalizzate.

5. facoltativo. Se nel passaggio 2 sono state aggiunte altre proprietà, è necessario eseguire l'override della proprietà <xref:System.Configuration.ConfigurationElement.Properties%2A> per registrare le impostazioni di configurazione aggiuntive affinché il framework di configurazione le riconosca. Combinare le proprietà con le proprietà della classe di base per consentire la configurazione delle impostazioni fornite dal sistema tramite questo elemento di configurazione delle credenziali client personalizzate.

    [!code-csharp[c_CustomCredentials#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#7)]
    [!code-vb[c_CustomCredentials#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#7)]

Una volta configurata la classe del gestore di configurazione, può essere integrata nel Framework di configurazione WCF. Ciò consente di utilizzare le credenziali client personalizzate negli elementi di comportamento dell'endpoint client, come illustrato nella procedura seguente.

#### <a name="to-register-and-use-a-custom-client-credentials-configuration-handler-in-the-application-configuration"></a>Per registrare e utilizzare un gestore di configurazione di credenziali client personalizzate nella configurazione dell'applicazione

1. Aggiungere un elemento`extensions`< > e un elemento`behaviorExtensions`< > al file di configurazione.

2. Aggiungere un elemento`add`< > all'elemento <`behaviorExtensions`> e impostare l' `name` attributo su un valore appropriato.

3. Impostare l'attributo `type` sul nome del tipo completo. Includere inoltre il nome e altri attributi dell'assembly.

    ```xml
    <system.serviceModel>
      <extensions>
        <behaviorExtensions>
          <add name="myClientCredentials" type="Microsoft.ServiceModel.Samples.MyClientCredentialsConfigHandler, CustomCredentials, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
        </behaviorExtensions>
      </extensions>
    <system.serviceModel>
    ```

4. Al termine della registrazione del gestore di configurazione, l'elemento credentials personalizzato può essere utilizzato all'interno dello stesso file di configurazione al posto`clientCredentials`dell'elemento > < fornito dal sistema. È possibile utilizzare sia le proprietà fornite dal sistema che qualsiasi nuova proprietà aggiunta all'implementazione del gestore di configurazione. Nell'esempio seguente viene impostato il valore di una proprietà personalizzata utilizzando l'attributo `creditCardNumber`.

    ```xml
    <behaviors>
      <endpointBehaviors>
        <behavior name="myClientCredentialsBehavior">
          <myClientCredentials creditCardNumber="123-123-123"/>
        </behavior>
      </endpointBehaviors>
    </behaviors>
    ```

#### <a name="to-implement-custom-service-credentials"></a>Per implementare credenziali del servizio personalizzate

1. Definire una nuova classe derivata da <xref:System.ServiceModel.Description.ServiceCredentials>.

2. facoltativo. Aggiungere nuove proprietà per fornire API per i nuovi valori delle credenziali che vengono aggiunte. Se non vengono aggiunti nuovi valori delle credenziali, ignorare questo passaggio. Nell'esempio seguente viene aggiunta una proprietà `AdditionalCertificate`.

3. Eseguire l'override del metodo <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> . Questo metodo viene chiamato automaticamente dall'infrastruttura WCF quando viene utilizzata la credenziale client personalizzata. Il metodo è responsabile della creazione e della restituzione di un'istanza di un'implementazione della classe <xref:System.IdentityModel.Selectors.SecurityTokenManager>, descritta nella procedura seguente.

4. facoltativo. Eseguire l'override del metodo <xref:System.ServiceModel.Description.ServiceCredentials.CloneCore%2A> . È richiesto solo se si aggiungono nuove proprietà o campi interni all'implementazione delle credenziali client personalizzate.

    [!code-csharp[c_CustomCredentials#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#4)]
    [!code-vb[c_CustomCredentials#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#4)]

#### <a name="to-implement-a-custom-service-security-token-manager"></a>Per implementare un gestore del token di sicurezza del servizio personalizzato

1. Definire una nuova classe derivata dalla classe <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>.

2. facoltativo. Eseguire l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%2A> se è necessario creare un'implementazione <xref:System.IdentityModel.Selectors.SecurityTokenProvider> personalizzata. Per ulteriori informazioni sui provider di token di sicurezza personalizzati [, vedere Procedura: Creare un provider](how-to-create-a-custom-security-token-provider.md)di token di sicurezza personalizzato.

3. facoltativo. Eseguire l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> se è necessario creare un'implementazione <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> personalizzata. Per ulteriori informazioni sugli autenticatori del token di sicurezza personalizzati [, vedere Procedura: Creare un](how-to-create-a-custom-security-token-authenticator.md) argomento dell'autenticatore del token di sicurezza personalizzato.

4. facoltativo. Eseguire l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%28System.IdentityModel.Selectors.SecurityTokenVersion%29> se è necessario creare un oggetto <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> personalizzato. Per ulteriori informazioni sui token di sicurezza personalizzati e sui serializzatori di token di sicurezza [personalizzati, vedere Procedura: Creare un token](how-to-create-a-custom-token.md)personalizzato.

    [!code-csharp[c_CustomCredentials#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#5)]
    [!code-vb[c_CustomCredentials#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#5)]

#### <a name="to-use-custom-service-credentials-from-application-code"></a>Per utilizzare credenziali del servizio personalizzate dal codice dell'applicazione

1. Creare un'istanza di <xref:System.ServiceModel.ServiceHost>.

2. Rimuovere il comportamento delle credenziali del servizio fornite dal sistema dalla raccolta <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>.

3. Creare una nuova istanza della classe di credenziali del servizio personalizzate e aggiungerla alla raccolta <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>.

    [!code-csharp[c_CustomCredentials#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#6)]
    [!code-vb[c_CustomCredentials#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#6)]

Aggiungere il supporto per la configurazione utilizzando i passaggi descritti in precedenza nelle procedure "`To create a configuration handler for custom client credentials`" e "`To register and use a custom client credentials configuration handler in the application configuration`." L'unica differenza è nell'utilizzo della classe <xref:System.ServiceModel.Configuration.ServiceCredentialsElement> invece che della classe <xref:System.ServiceModel.Configuration.ClientCredentialsElement> come classe base per il gestore della configurazione. L'elemento credenziale personalizzata del servizio può quindi essere utilizzato ovunque sia utilizzato l'elemento `<serviceCredentials>` fornito dal sistema.

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- <xref:System.ServiceModel.Security.SecurityCredentialsManager>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- [Procedura: Creare un provider di token di sicurezza personalizzato](how-to-create-a-custom-security-token-provider.md)
- [Procedura: Creare un autenticatore del token di sicurezza personalizzato](how-to-create-a-custom-security-token-authenticator.md)
- [Procedura: Creazione di un token personalizzato](how-to-create-a-custom-token.md)

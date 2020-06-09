---
title: 'Procedura: creare una classe WSFederationHttpBinding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: e54897d7-aa6c-46ec-a278-b2430c8c2e10
ms.openlocfilehash: ccc28c46e8be0b835cf08d372ef85b8a66e989ef
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595440"
---
# <a name="how-to-create-a-wsfederationhttpbinding"></a>Procedura: creare una classe WSFederationHttpBinding

In Windows Communication Foundation (WCF) la <xref:System.ServiceModel.WSFederationHttpBinding> classe ( [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) in configurazione) fornisce un meccanismo per esporre un servizio federato. ovvero un servizio che richiede ai client di autenticarsi usando un token di sicurezza rilasciato da un servizio token di sicurezza. In questo argomento viene illustrato come impostare una classe <xref:System.ServiceModel.WSFederationHttpBinding> nel codice e nella configurazione. Una volta creata l'associazione, è possibile impostare un endpoint per usarla.

 I passaggi di base sono elencati di seguito:

1. Selezionare una modalità di sicurezza. La classe <xref:System.ServiceModel.WSFederationHttpBinding> supporta `Message`, che assicura protezione end-to-end a livello di messaggio, anche su più hop, e `TransportWithMessageCredential`, che offre prestazioni migliori nei casi in cui il client e il servizio possono stabilire una connessione diretta su HTTPS.

    > [!NOTE]
    > La classe <xref:System.ServiceModel.WSFederationHttpBinding> supporta anche `None` come modalità di sicurezza. Questa modalità non è protetta e viene fornita solo a scopo di debug. Se un endpoint di servizio viene distribuito con un oggetto <xref:System.ServiceModel.WSFederationHttpBinding> con la relativa modalità di sicurezza impostata su `None` , l'associazione client risultante (generata dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)) è un oggetto <xref:System.ServiceModel.WSHttpBinding> con la modalità di sicurezza `None` .

     Diversamente da altre associazioni fornite dal sistema, non è necessario selezionare un tipo di credenziale client quando si usa `WSFederationHttpBinding`, poiché il tipo di credenziale client è sempre un token rilasciato. WCF acquisisce un token da un'autorità emittente specificata e presenta il token al servizio per autenticare il client.

2. Sui client federati, impostare la proprietà <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerAddress%2A> sull'URL del servizio token di sicurezza. Impostare la proprietà <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerBinding%2A> sull'associazione da usare per comunicare con il servizio token di sicurezza.

3. Facoltativa. Impostare la proprietà <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedTokenType%2A> sull'URI (Uniform Resource Identifier) di un tipo di token. Nei servizi federati, specificare il tipo di token previsto dal servizio. Sui client federati, specificare il tipo di token richiesto dal client al servizio token di sicurezza.

     Se non viene specificato alcun tipo di token, i client generano token RST (Request Security Token) WS-Trust senza un URI del tipo di token e i servizi prevedono che l'autenticazione client venga eseguita, per impostazione predefinita, usando un token SAML (Security Assertions Markup Language) 1.1.

     L'URI per un token SAML 1,1 è `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1` .

4. Facoltativa. Sui servizi federati, impostare la proprietà <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A> sull'URL dei metadati di un servizio token di sicurezza. L'endpoint dei metadati consente ai client del servizio di selezionare una coppia associazione/endpoint appropriata, se il servizio è configurato per pubblicare metadati. Per ulteriori informazioni sulla pubblicazione dei metadati, vedere la pagina relativa alla [pubblicazione di metadati](publishing-metadata.md).

 È inoltre possibile impostare altre proprietà, inclusi tipo di chiave usato come chiave di prova nel token rilasciato, gruppo di algoritmi da usare tra il client e il servizio, indicazione circa la necessità di negoziare o specificare esplicitamente la credenziale del servizio, tutte le attestazioni specifiche che il servizio prevede che il token rilasciato contenga e qualsiasi elemento XML aggiuntivo da aggiungere alla richiesta inviata dal client al servizio token di sicurezza.

> [!NOTE]
> La proprietà `NegotiateServiceCredential` è rilevante solo quando `SecurityMode` è impostata su `Message`. Se `SecurityMode` è impostata su `TransportWithMessageCredential`, la proprietà `NegotiateServiceCredential` viene ignorata.

## <a name="to-configure-a-wsfederationhttpbinding-in-code"></a>Per configurare una classe WSFederationHttpBinding nel codice

1. Creare un'istanza di <xref:System.ServiceModel.WSFederationHttpBinding>.

2. Impostare la proprietà <xref:System.ServiceModel.WSFederationHttpSecurity.Mode%2A> su <xref:System.ServiceModel.WSFederationHttpSecurityMode> o <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message> in base alle necessità. Se è necessaria una suite di algoritmi diversa <xref:System.ServiceModel.Security.SecurityAlgorithmSuite.Basic256%2A> da, impostare la <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.AlgorithmSuite%2A> proprietà su un valore tratto da <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> .

3. Impostare la proprietà <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.NegotiateServiceCredential%2A> in base alle necessità.

4. Impostare la <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedKeyType%2A> proprietà su <xref:System.IdentityModel.Tokens.SecurityKeyType> `SymmetricKey` o su.`AsymmetricKey` come richiesto.

5. Impostare la proprietà <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedTokenType%2A> sul valore appropriato. Se non è impostato alcun valore, il valore predefinito di WCF è `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1` , che indica i token SAML 1,1.

6. Obbligatorio sul client se non viene specificata alcuna emittente locale; facoltativo sul servizio. Creare una classe <xref:System.ServiceModel.EndpointAddress> che contenga le informazioni sull'indirizzo e l'identità del servizio token di sicurezza e assegnare l'istanza di <xref:System.ServiceModel.EndpointAddress> alla proprietà <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerAddress%2A>.

7. Obbligatorio sul client se non viene specificata alcuna emittente locale; non usato sul servizio. Creare un oggetto <xref:System.ServiceModel.Channels.Binding> per `SecurityTokenService` e assegnare l' <xref:System.ServiceModel.Channels.Binding> istanza alla <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerBinding%2A> Proprietà.

8. Non usato sul client; facoltativo sul servizio. Creare un'istanza di <xref:System.ServiceModel.EndpointAddress> per i metadati del servizio token di sicurezza e assegnarla alla proprietà `IssuerMetadataAddress`.

9. Facoltativo sul client e sul servizio. Creare e aggiungere una o più istanze di <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement> alla raccolta restituita dalla proprietà <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>.

10. Facoltativo sul client e sul servizio. Creare e aggiungere una o più istanze di <xref:System.Xml.XmlElement> alla raccolta restituita dalla proprietà <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>.

## <a name="to-create-a-federated-endpoint-in-configuration"></a>Per creare un endpoint federato nella configurazione

1. Creare un oggetto [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) come figlio dell' [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) elemento nel file di configurazione dell'applicazione.

2. Creare un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento come figlio di [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) e impostare l' `name` attributo su un valore appropriato.

3. Creare un `<security>` elemento come figlio dell' [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento.

4. Impostare l'attributo  nell'elemento  su un valore di  o , in base alle necessità.

5. Creare un elemento  come figlio dell'elemento .

6. Facoltativa. Impostare l'attributo `algorithmSuite` sull'elemento `<message>` con un valore appropriato. Il valore predefinito è `Basic256`.

7. Facoltativa. Se è necessaria una chiave di prova asimmetrica, impostare l'attributo `issuedKeyType` dell'elemento `<message>`. Il valore predefinito è `SymmetricKey`.

8. Facoltativa. Impostare l'attributo `issuedTokenType` sull'elemento `<message>`.

9. Obbligatorio sul client se non viene specificata alcuna emittente locale; facoltativo sul servizio. Creare un elemento `<issuer>` come figlio dell'elemento `<message>`.

10. Impostare l'attributo `address` sull'elemento `<issuer>` e specificare l'indirizzo in cui il servizio token di sicurezza accetta richieste del token.

11. Facoltativa. Aggiungere un elemento `<identity>` figlio e specificare l'identità del servizio token di sicurezza

12. Per altre informazioni, vedere [identità e autenticazione del servizio](service-identity-and-authentication.md).

13. Obbligatorio sul client se non viene specificata alcuna emittente locale; non usato sul servizio. Creare un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento nella sezione bindings che può essere utilizzato per comunicare con il servizio token di sicurezza. Per ulteriori informazioni sulla creazione di un'associazione, vedere [procedura: specificare un'associazione al servizio nella configurazione](../how-to-specify-a-service-binding-in-configuration.md).

14. Specificare l'associazione creata nel passaggio precedente impostando gli attributi `binding` e `bindingConfiguration` dell'elemento `<issuer>`.

15. Non usato sul client; facoltativo sul servizio. Creare un `<issuerMetadata>` elemento come figlio dell' `message` elemento <>. Quindi, in un attributo `address` sull'elemento `<issuerMetadata>`, specificare l'indirizzo in cui il servizio token di sicurezza deve pubblicare i propri metadati. Facoltativamente, aggiungere un elemento `<identity>` figlio e specificare l'identità del servizio token di sicurezza

16. Facoltativo sul client e sul servizio. Aggiungere un elemento  come figlio dell'elemento . Specificare le attestazioni obbligatorie e facoltative su cui si basa il servizio aggiungendo [\<add>](../../configure-apps/file-schema/wcf/add-of-claimtyperequirements.md) elementi all' `<claimTypeRequirements>` elemento e specificando il tipo di attestazione con l' `claimType` attributo. Specificare se una determinata attestazione è obbligatoria o facoltativa impostando l'attributo `isOptional`.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato il codice per l'impostazione di una classe `WSFederationHttpBinding` in modo imperativo.

[!code-csharp[c_FederationBinding#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_federationbinding/cs/source.cs#2)]
[!code-vb[c_FederationBinding#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_federationbinding/vb/source.vb#2)]

## <a name="see-also"></a>Vedere anche

- [Federazione](federation.md)
- [Esempio di federazione](../samples/federation-sample.md)
- [Procedura: disattivare sessioni protette in un'associazione WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)

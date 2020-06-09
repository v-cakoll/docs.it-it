---
title: 'Procedura: configurare un emittente locale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 15263371-514e-4ea6-90fb-14b4939154cd
ms.openlocfilehash: 7da3cd34d0840eea48c9ef0bb89fb6580b87623b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601244"
---
# <a name="how-to-configure-a-local-issuer"></a>Procedura: configurare un emittente locale

In questo argomento viene illustrato come configurare un client per utilizzare un emittente locale per i token emessi.

Spesso, quando un client comunica con un servizio federato, il servizio specifica l'indirizzo del servizio token di sicurezza previsto per l'emissione del token che il client utilizzerà per autenticarsi presso il servizio federato. In alcune situazioni, il client può essere configurato per l'uso di un' *autorità emittente locale*.

Windows Communication Foundation (WCF) usa un'autorità emittente locale nei casi in cui l'indirizzo dell'emittente di un'associazione federata è `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o `null` . In tali casi, è necessario configurare la classe <xref:System.ServiceModel.Description.ClientCredentials> con l'indirizzo dell'emittente locale e con l'associazione da utilizzare per comunicare con tale emittente.

> [!NOTE]
> Se la <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> proprietà della `ClientCredentials` classe è impostata su `true` , non viene specificato un indirizzo dell'emittente locale e l'indirizzo dell'autorità emittente specificato dall'oggetto o da un' [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) altra associazione federata è, `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self` `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o è `null` , viene utilizzata l'autorità emittente di Windows CardSpace.

## <a name="to-configure-the-local-issuer-in-code"></a>Per configurare l'emittente locale nel codice

1. Creare una variabile di tipo <xref:System.ServiceModel.Security.IssuedTokenClientCredential>.

2. Impostare la variabile sull'istanza restituita dalla proprietà <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> della classe `ClientCredentials`. L'istanza viene restituita dalla proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> del client (ereditata da <xref:System.ServiceModel.ClientBase%601>) o dalla proprietà <xref:System.ServiceModel.ChannelFactory.Credentials%2A> della classe <xref:System.ServiceModel.ChannelFactory>:

     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]

3. Impostare la proprietà <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> su una nuova istanza di <xref:System.ServiceModel.EndpointAddress>, con l'indirizzo dell'emittente locale come argomento per il costruttore.

     [!code-csharp[c_CreateSTS#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#10)]
     [!code-vb[c_CreateSTS#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#10)]

     In alternativa, creare una nuova istanza <xref:System.Uri> come argomento per il costruttore.

     [!code-csharp[c_CreateSTS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#11)]
     [!code-vb[c_CreateSTS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#11)]

     Il `addressHeaders` parametro è una matrice di <xref:System.ServiceModel.Channels.AddressHeader> istanze, come illustrato.

     [!code-csharp[c_CreateSTS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#12)]
     [!code-vb[c_CreateSTS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#12)]

4. Impostare l'associazione per l'emittente locale utilizzando la <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> Proprietà.

     [!code-csharp[c_CreateSTS#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#13)]
     [!code-vb[c_CreateSTS#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#13)]

5. Facoltativa. Aggiungere i comportamenti dell'endpoint configurati per l'emittente locale aggiungendo tali comportamenti alla raccolta restituita dalla proprietà <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A>.

     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]

## <a name="to-configure-the-local-issuer-in-configuration"></a>Per configurare l'emittente locale nella configurazione

1. Creare un [\<localIssuer>](../../configure-apps/file-schema/wcf/localissuer.md) elemento come figlio dell' [\<issuedToken>](../../configure-apps/file-schema/wcf/issuedtoken.md) elemento che è a sua volta un elemento figlio dell' [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) elemento in un comportamento dell'endpoint.

2. Impostare l'attributo `address` sull'indirizzo dell'emittente locale che accetterà richieste del token.

3. Impostare gli attributi `binding` e `bindingConfiguration` su valori che fanno riferimento all'associazione appropriata da utilizzare durante la comunicazione con l'endpoint dell'emittente locale.

4. Facoltativa. Impostare l' [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elemento come figlio dell' `localIssuer` elemento <> e specificare le informazioni sull'identità per l'emittente locale.

5. Facoltativa. Impostare l' [\<headers>](../../configure-apps/file-schema/wcf/headers.md) elemento come figlio dell' `localIssuer` elemento <> e specificare intestazioni aggiuntive necessarie per indirizzare correttamente l'emittente locale.

## <a name="net-framework-security"></a>Sicurezza di .NET Framework

Si noti che, se per una determinata associazione vengono specificati l'indirizzo dell'emittente e l'associazione, l'emittente locale non verrà utilizzato per gli endpoint che utilizzano tale associazione. Per i client che prevedono di utilizzare sempre l'emittente locale, è necessario accertarsi di non utilizzare tale associazione o di modificare l'associazione in modo che l'indirizzo dell'emittente sia `null`.

## <a name="see-also"></a>Vedere anche

- [Procedura: configurare le credenziali in un servizio federativo](how-to-configure-credentials-on-a-federation-service.md)
- [Procedura: creare un client federato](how-to-create-a-federated-client.md)
- [Procedura: Creare una classe WSFederationHttpBinding](how-to-create-a-wsfederationhttpbinding.md)

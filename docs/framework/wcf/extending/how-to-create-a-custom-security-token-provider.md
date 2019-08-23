---
title: 'Procedura: Creare un provider di token di sicurezza personalizzati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
ms.openlocfilehash: 8daf025212e34c5d37d09ae5108d186d13b99eca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951816"
---
# <a name="how-to-create-a-custom-security-token-provider"></a>Procedura: Creare un provider di token di sicurezza personalizzati
In questo argomento viene illustrato come creare nuovi tipi di token con un provider di token di sicurezza personalizzati e come integrare il provider con un gestore di token di sicurezza personalizzati.  
  
> [!NOTE]
> Creare un provider di token personalizzati se i token forniti dal sistema, presenti nello spazio dei nomi <xref:System.IdentityModel.Tokens>, non corrispondono ai propri requisiti.  
  
 Il provider di token di sicurezza crea una rappresentazione dei token di sicurezza in base alle informazioni presenti nelle credenziali del client o del servizio. Per utilizzare il provider di token di sicurezza personalizzato nella sicurezza Windows Communication Foundation (WCF), è necessario creare credenziali personalizzate e implementazioni del gestore del token di sicurezza.  
  
 Per ulteriori informazioni sulle credenziali personalizzate e sul gestore del token di [sicurezza, vedere la procedura dettagliata: Creazione di credenziali](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)client e del servizio personalizzate.  
  
### <a name="to-create-a-custom-security-token-provider"></a>Per creare un provider di token di sicurezza personalizzati  
  
1. Definire una nuova classe derivata dalla classe <xref:System.IdentityModel.Selectors.SecurityTokenProvider>.  
  
2. Implementare il metodo <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>. Il metodo è responsabile della creazione e della restituzione di un'istanza del token di sicurezza. Nell'esempio seguente viene creata una classe denominata `MySecurityTokenProvider` ed eseguito l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>, per restituire un'istanza della classe <xref:System.IdentityModel.Tokens.X509SecurityToken>. Il costruttore della classe richiede un'istanza della classe <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a>Per integrare un provider di token di sicurezza personalizzati con un gestore di token di sicurezza personalizzati  
  
1. Definire una nuova classe derivata dalla classe <xref:System.IdentityModel.Selectors.SecurityTokenManager>. L'esempio seguente deriva dalla classe <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>, che deriva dalla classe <xref:System.IdentityModel.Selectors.SecurityTokenManager>.  
  
2. Eseguire l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>, se non lo si è già fatto.  
  
     Il <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> metodo è responsabile della restituzione di un'istanza <xref:System.IdentityModel.Selectors.SecurityTokenProvider> della classe appropriata al <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parametro passato al metodo dal framework di sicurezza di WCF. Modificare il metodo per restituire l'implementazione del provider di token di sicurezza personalizzati (creato nella procedura precedente), quando il metodo viene chiamato con un parametro del token di sicurezza appropriato. Per ulteriori informazioni sul gestore del token di sicurezza, vedere [la procedura dettagliata: Creazione di credenziali](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)client e del servizio personalizzate.  
  
3. Aggiungere logica personalizzata al metodo, per consentire la restituzione del provider di token di sicurezza personalizzati in base al parametro <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>. Nell'esempio seguente viene restituito il provider di token di sicurezza personalizzati, se i requisiti dei token vengono soddisfatti. I requisiti includono un token di sicurezza X.509 e la direzione dei messaggi (è necessario che il token venga usato per l'output dei messaggi). Per tutti gli altri casi, il codice chiama la classe di base per mantenere il comportamento fornito dal sistema per gli altri requisiti dei token di sicurezza.  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata un'implementazione completa di <xref:System.IdentityModel.Selectors.SecurityTokenProvider>, insieme a un'implementazione di <xref:System.IdentityModel.Selectors.SecurityTokenManager> corrispondente.  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Selectors.SecurityTokenProvider>
- <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.IdentityModel.Tokens.X509SecurityToken>
- [Procedura dettagliata: Creazione di credenziali client e del servizio personalizzate](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)
- [Procedura: Creare un autenticatore del token di sicurezza personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)

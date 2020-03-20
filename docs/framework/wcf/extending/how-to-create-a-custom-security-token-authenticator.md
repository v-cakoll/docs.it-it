---
title: 'Procedura: creare un autenticatore di token di sicurezza personalizzatoHow to: create a custom security token authenticator'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: 10e245f7-d31e-42e7-82a2-d5780325d372
ms.openlocfilehash: 7bbe59958f59f76046c0a112463cfa64d09c14d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185583"
---
# <a name="how-to-create-a-custom-security-token-authenticator"></a>Procedura: creare un autenticatore di token di sicurezza personalizzatoHow to: create a custom security token authenticator
In questo argomento viene illustrato come creare un autenticatore del token di sicurezza personalizzato e come integrarlo con un gestore del token di sicurezza personalizzato. Un autenticatore del token di sicurezza codi sicurezzantenuto di un token di sicurezza fornito con un messaggio in ingresso. Se la convalida ha esito positivo, l'autenticatore restituisce una raccolta di istanze <xref:System.IdentityModel.Policy.IAuthorizationPolicy> che, quando valutata, restituisce un set di attestazioni.  
  
 Per usare un autenticatore di token di sicurezza personalizzato in Windows Communication Foundation (WCF), è innanzitutto necessario creare credenziali personalizzate e implementazioni del gestore di token di sicurezza. Per ulteriori informazioni sulla creazione di credenziali personalizzate e un gestore di token di sicurezza, vedere [Procedura dettagliata: creazione](walkthrough-creating-custom-client-and-service-credentials.md)di credenziali client e del servizio personalizzate .
  
## <a name="procedures"></a>Procedure  
  
#### <a name="to-create-a-custom-security-token-authenticator"></a>Per creare un autenticatore del token di sicurezza personalizzato  
  
1. Definire una nuova classe derivata dalla classe <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>.  
  
2. Eseguire l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.CanValidateTokenCore%2A> . Il metodo restituisce `true` o `false` a seconda che l'autenticatore personalizzato possa convalidare o meno il tipo di token in ingresso.  
  
3. Eseguire l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.ValidateTokenCore%2A> . Questo metodo deve convalidare in modo appropriato il contenuto del token. Se il token supera il passo di convalida, restituisce una raccolta di istanze <xref:System.IdentityModel.Policy.IAuthorizationPolicy>. Nell'esempio seguente viene utilizzata un'implementazione di criteri di autorizzazione personalizzata che verrà creata nella procedura successiva.  
  
     [!code-csharp[C_CustomTokenAuthenticator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#1)]
     [!code-vb[C_CustomTokenAuthenticator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#1)]  
  
 Il codice precedente restituisce una raccolta di criteri di autorizzazione nel metodo <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.CanValidateToken%28System.IdentityModel.Tokens.SecurityToken%29>. WCF non fornisce un'implementazione pubblica di questa interfaccia. Nella procedura seguente viene illustrato come eseguire l'operazione in base ai propri requisiti.  
  
#### <a name="to-create-a-custom-authorization-policy"></a>Per creare un criterio di autorizzazione personalizzato  
  
1. Definire una nuova classe che implementa l'interfaccia <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.  
  
2. Implementare la proprietà di sola lettura <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A>. Un sistema per implementare questa proprietà consiste nel generare un identificatore univoco globale (GUID, Globally Unique Identifier) nel costruttore della classe e restituirlo ogni volta che viene richiesto il valore per questa proprietà.  
  
3. Implementare la proprietà di sola lettura <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A>. Questa proprietà deve restituire un emittente dei set di attestazioni ottenuti dal token. Tale emittente deve corrispondere all'emittente del token o a un'autorità responsabile della convalida del contenuto del token. Nell'esempio seguente viene utilizzata l'attestazione dell'emittente passata alla classe dall'autenticatore del token di sicurezza personalizzato creato nella procedura precedente. L'autenticatore del token di sicurezza personalizzato utilizza il set di attestazioni fornito dal sistema (restituito dalla proprietà <xref:System.IdentityModel.Claims.ClaimSet.System%2A>) per rappresentare l'emittente del token nome utente.  
  
4. Implementare il metodo <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A>. Questo metodo compila un'istanza della classe <xref:System.IdentityModel.Policy.EvaluationContext> (passata come argomento) con attestazioni basate sul contenuto del token di sicurezza in ingresso. Il metodo restituisce `true` al termine della valutazione. Nei casi in cui l'implementazione si basa sulla presenza di altri criteri di autorizzazione che forniscono informazioni aggiuntive al contesto di valutazione, questo metodo può restituire `false` se le informazioni necessarie non sono ancora presenti nel contesto di valutazione. In tal caso, WCF chiamerà nuovamente il metodo dopo la valutazione di tutti gli altri criteri di autorizzazione generati per il messaggio in arrivo se almeno uno di questi criteri di autorizzazione ha modificato il contesto di valutazione.  
  
     [!code-csharp[c_CustomTokenAuthenticator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#3)]
     [!code-vb[c_CustomTokenAuthenticator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#3)]  

 [Procedura dettagliata: creazione di credenziali client e del servizio personalizzate](walkthrough-creating-custom-client-and-service-credentials.md) viene descritto come creare credenziali personalizzate e un gestore di token di sicurezza personalizzato. Per utilizzare l'autenticatore del token di sicurezza personalizzato qui creato, viene modificata un'implementazione del gestore del token di sicurezza per restituire l'autenticatore personalizzato dal metodo <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A>. Il metodo restituisce un autenticatore quando viene passato un requisito di token di sicurezza appropriato.  
  
#### <a name="to-integrate-a-custom-security-token-authenticator-with-a-custom-security-token-manager"></a>Per integrare un autenticatore del token di sicurezza personalizzato con un gestore del token di sicurezza personalizzato  
  
1. Eseguire l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> nell'implementazione del gestore del token di sicurezza personalizzato.  
  
2. Aggiungere logica al metodo per consentire la restituzione dell'autenticatore del token di sicurezza personalizzato in base al parametro <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>. Nell'esempio seguente viene restituito un autenticatore del token di sicurezza personalizzato se il tipo di token dei requisiti di token è un nome utente (rappresentato dalla proprietà <xref:System.IdentityModel.Tokens.SecurityTokenTypes.UserName%2A>) e la direzione del messaggio per cui viene richiesto l'autenticatore del token di sicurezza è di input (rappresentata dal campo <xref:System.ServiceModel.Description.MessageDirection.Input>).  
  
     [!code-csharp[c_CustomTokenAuthenticator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#2)]
     [!code-vb[c_CustomTokenAuthenticator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#2)]  

## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.IdentityModel.Tokens.UserNameSecurityToken>
- [Procedura dettagliata: creazione di credenziali client e del servizio personalizzate](walkthrough-creating-custom-client-and-service-credentials.md)
- [Procedura: creare un provider di token di sicurezza personalizzati](how-to-create-a-custom-security-token-provider.md)

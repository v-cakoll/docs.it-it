---
title: 'Procedura: Usare un validator di nome utente e password personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 57bd650caef831f3ee886c0422e13cc4149d3416
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968801"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>Procedura: Usare un validator di nome utente e password personalizzato
Per impostazione predefinita, quando si usa un nome utente e una password per l'autenticazione, Windows Communication Foundation (WCF) usa Windows per convalidare il nome utente e la password. Tuttavia, WCF consente schemi di autenticazione con nome utente e password personalizzati, noti anche come *validator*. Per incorporare un validator personalizzato di nome utente e password, creare una classe che deriva da <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> e configurarla.  
  
 Per un'applicazione di esempio, vedere [validator nome utente password](../../../../docs/framework/wcf/samples/user-name-password-validator.md).  
  
### <a name="to-create-a-custom-user-name-and-password-validator"></a>Per creare un validator di nome utente e password personalizzato  
  
1. Creare una classe che deriva da <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2. Implementare lo schema di autenticazione personalizzato eseguendo l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     Non utilizzare il codice contenuto nell'esempio seguente, che esegue l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, in un ambiente di produzione. Sostituire il codice con lo schema di convalida di nome utente e password personalizzato, operazione che potrebbe comportare il recupero di coppie di nome utente e password da un database.  
  
     Affinché gli errori di autenticazione vengano restituiti al client, generare una classe <xref:System.ServiceModel.FaultException> nel metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a>Per configurare un servizio per l'utilizzo di un validator di nome utente e password personalizzato  
  
1. Configurare un'associazione che utilizza meccanismi di sicurezza a livello di messaggio su qualsiasi trasporto o meccanismi di sicurezza a livello di trasporto su HTTP(S).  
  
     Quando si utilizza la sicurezza dei messaggi, aggiungere una delle associazioni fornite dal sistema, ad esempio un [ \<> WSHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), o una [ \<> CustomBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) che supporta la sicurezza dei messaggi e `UserName` il tipo di credenziale.  
  
     Quando si utilizza la [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) sicurezza a livello di trasporto su http (S), aggiungere wsHttpBinding > o [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), un [ \<> NetTcpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) o un [ \<CustomBinding > ](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)che usa http (S) e lo `Basic` schema di autenticazione.  
  
    > [!NOTE]
    > Quando si utilizza [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] o versioni successive, è possibile utilizzare un validator di nome utente e password personalizzato con modalità di sicurezza dei messaggi e del trasporto. Con WinFX, un validator personalizzato di nome utente e password può essere utilizzato solo con la sicurezza dei messaggi.  
  
    > [!TIP]
    >  Per ulteriori informazioni sull'utilizzo \<della > NetTcpBinding in questo contesto, vedere [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
  
    1. Nel file di configurazione, sotto l' [ \<elemento System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) aggiungere un [ \<elemento bindings >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) .  
  
    2. Aggiungere un [ \<elemento WSHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) o [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) alla sezione Bindings. Per ulteriori informazioni sulla creazione di un elemento di associazione WCF [, vedere Procedura: Specificare un'associazione al servizio nella](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)configurazione.  
  
    3. Impostare l' `mode` attributo `Message` `TransportWithMessageCredential` `Transport` [ \<del > di sicurezza](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) o [ \<> di sicurezza](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) su, o.  
  
    4. Impostare l' `clientCredentialType` attributo [ \<dell'> del messaggio](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) o [ \<del > di trasporto](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).  
  
         Quando si utilizza la sicurezza del messaggio `clientCredentialType` , impostare l'attributo [ \<del messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) su. `UserName`  
  
         Quando si utilizza la `clientCredentialType` sicurezza a livello `Basic` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) di trasporto su http (S), impostare l'attributo del > di trasporto o [ \<del trasporto >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) su.  
  
        > [!NOTE]
        >  Quando un servizio WCF è ospitato in Internet Information Services (IIS) utilizzando la sicurezza a livello di trasporto <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> e la proprietà è <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>impostata su, lo schema di autenticazione personalizzato utilizza un subset dell'autenticazione di Windows. Ciò è dovuto al fatto che in questo scenario IIS esegue l'autenticazione di Windows prima che WCF richiami l'autenticatore personalizzato.  
  
     Per ulteriori informazioni sulla creazione di un elemento di associazione WCF [, vedere Procedura: Specificare un'associazione al servizio nella](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)configurazione.  
  
     Nell'esempio seguente viene illustrato il codice di configurazione per l'associazione.  
  
    ```xml  
    <system.serviceModel>   
      <bindings>  
      <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="UserName" />  
            </security>  
          </binding>          
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
2. Configurare un comportamento che specifica che un validator personalizzato di nome utente e password viene utilizzato per convalidare coppie di nome utente e password per i token di sicurezza <xref:System.IdentityModel.Tokens.UserNameSecurityToken> in arrivo.  
  
    1. Come elemento figlio dell' [ \<elemento > System. ServiceModel](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) , aggiungere un [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.  
  
    2. Aggiungere un [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) [ >serviceBehaviorsall'elementobehaviors>.\<](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
  
    3. Aggiungere un [ \<elemento behavior >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) e impostare l' `name` attributo su un valore appropriato.  
  
    4. Aggiungere un [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) [ >ServiceCredentialsalcomportamento>elemento.\<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)  
  
    5. Aggiungere un [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) [ >UserNameAuthenticational>ServiceCredentials.\<](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)  
  
    6. Impostare `userNamePasswordValidationMode` su `Custom`.  
  
        > [!IMPORTANT]
        >  Se il `userNamePasswordValidationMode` valore non è impostato, WCF usa l'autenticazione di Windows anziché il validator personalizzato di nome utente e password.  
  
    7. Impostare `customUserNamePasswordValidatorType` sul tipo che rappresenta il validator personalizzato di nome utente e password.  
  
     Nell'esempio seguente viene illustrato il frammento `<serviceCredentials>` fino a questo punto.  
  
    ```xml  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## <a name="example"></a>Esempio  
 Nel codice di esempio seguente viene dimostrato come creare un validator personalizzato di nome utente e password. Non utilizzare il codice che esegue l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> in un ambiente di produzione. Sostituire il codice con lo schema di convalida di nome utente e password personalizzato, operazione che potrebbe comportare il recupero di coppie di nome utente e password da un database.  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [Procedura: Usare il provider di appartenenze ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
- [Autenticazione](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)

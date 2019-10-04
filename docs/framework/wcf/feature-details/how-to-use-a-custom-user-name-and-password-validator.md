---
title: 'Procedura: Usare un validator di nome utente e password personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 98ffad7e717aac949509fa701c77d8ba2b80a695
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834700"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>Procedura: Usare un validator di nome utente e password personalizzato

Per impostazione predefinita, quando si usa un nome utente e una password per l'autenticazione, Windows Communication Foundation (WCF) usa Windows per convalidare il nome utente e la password. Tuttavia, WCF consente schemi di autenticazione con nome utente e password personalizzati, noti anche come *validator*. Per incorporare un validator personalizzato di nome utente e password, creare una classe che deriva da <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> e configurarla.

Per un'applicazione di esempio, vedere [validator nome utente password](../samples/user-name-password-validator.md).

### <a name="to-create-a-custom-user-name-and-password-validator"></a>Per creare un validator di nome utente e password personalizzato

1. Creare una classe che deriva da <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. Implementare lo schema di autenticazione personalizzato eseguendo l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.

    Non utilizzare il codice contenuto nell'esempio seguente, che esegue l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, in un ambiente di produzione. Sostituire il codice con lo schema di convalida di nome utente e password personalizzato, operazione che potrebbe comportare il recupero di coppie di nome utente e password da un database.

    Affinché gli errori di autenticazione vengano restituiti al client, generare una classe <xref:System.ServiceModel.FaultException> nel metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a>Per configurare un servizio per l'utilizzo di un validator di nome utente e password personalizzato

1. Configurare un'associazione che utilizza meccanismi di sicurezza a livello di messaggio su qualsiasi trasporto o meccanismi di sicurezza a livello di trasporto su HTTP(S).

    Quando si utilizza la sicurezza dei messaggi, aggiungere una delle associazioni fornite dal sistema, ad esempio un [> \<wsHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), o un [> \<customBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) che supporta la sicurezza dei messaggi e il tipo di credenziale `UserName`.

    Quando si usa la sicurezza a livello di trasporto su HTTP (S), aggiungere il [\<wsHttpBinding >](../../configure-apps/file-schema/wcf/wshttpbinding.md) o [\<basicHttpBinding >](../../configure-apps/file-schema/wcf/basichttpbinding.md), un @no__t > [-5netTcpBinding](../../configure-apps/file-schema/wcf/nettcpbinding.md) o un @no__t > [-7customBinding](../../configure-apps/file-schema/wcf/custombinding.md) che usa http (s) e il schema di autenticazione `Basic`.

    > [!NOTE]
    > Quando si utilizza [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] o versioni successive, è possibile utilizzare un validator di nome utente e password personalizzato con modalità di sicurezza dei messaggi e del trasporto. Con WinFX, un validator personalizzato di nome utente e password può essere utilizzato solo con la sicurezza dei messaggi.

    > [!TIP]
    > Per ulteriori informazioni sull'utilizzo di \<netTcpBinding > in questo contesto, vedere [\<security >](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md).

    1. Nel file di configurazione, sotto l'elemento [\<system. serviceModel >](../../configure-apps/file-schema/wcf/system-servicemodel.md) aggiungere un elemento [> @no__t 3bindings](../../configure-apps/file-schema/wcf/bindings.md) .

    2. Aggiungere un elemento [\<wsHttpBinding >](../../configure-apps/file-schema/wcf/wshttpbinding.md) o [\<basicHttpBinding >](../../configure-apps/file-schema/wcf/basichttpbinding.md) alla sezione Bindings. Per ulteriori informazioni sulla creazione di un elemento di associazione WCF, vedere [How per: Specificare un'associazione al servizio nella](../how-to-specify-a-service-binding-in-configuration.md)configurazione.

    3. Impostare l'attributo `mode` del [> \<Security](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) o [\<security >](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) su `Message`, `Transport` o `TransportWithMessageCredential`.

    4. Impostare l'attributo `clientCredentialType` del [> \<message](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) o [\<transport >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).

        Quando si usa la sicurezza del messaggio, impostare l'attributo `clientCredentialType` del [> \<message](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) su `UserName`.

        Quando si utilizza la sicurezza a livello di trasporto su HTTP (S), impostare l'attributo `clientCredentialType` del [> \<transport](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) o [\<transport >](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) su `Basic`.

        > [!NOTE]
        > Quando un servizio WCF è ospitato in Internet Information Services (IIS) utilizzando la sicurezza a livello di trasporto e la proprietà <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> è impostata su <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, lo schema di autenticazione personalizzato utilizza un subset dell'autenticazione di Windows. Ciò è dovuto al fatto che in questo scenario IIS esegue l'autenticazione di Windows prima che WCF richiami l'autenticatore personalizzato.

    Per ulteriori informazioni sulla creazione di un elemento di associazione WCF, vedere [How per: Specificare un'associazione al servizio nella](../how-to-specify-a-service-binding-in-configuration.md)configurazione.

    Nell'esempio seguente viene illustrato il codice di configurazione per l'associazione:

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

    1. Come elemento figlio dell'elemento [> \<system. ServiceModel](../../configure-apps/file-schema/wcf/system-servicemodel.md) , aggiungere un elemento [> @no__t 3behaviors](../../configure-apps/file-schema/wcf/behaviors.md) .

    2. Aggiungere un [> \<serviceBehaviors](../../configure-apps/file-schema/wcf/servicebehaviors.md) all'elemento [\<behaviors >](../../configure-apps/file-schema/wcf/behaviors.md) .

    3. Aggiungere un elemento [> \<behavior](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) e impostare l'attributo `name` su un valore appropriato.

    4. Aggiungere un [> \<serviceCredentials](../../configure-apps/file-schema/wcf/servicecredentials.md) all'elemento [\<behavior >](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) .

    5. Aggiungere un [> \<userNameAuthentication](../../configure-apps/file-schema/wcf/usernameauthentication.md) al [> @no__t 3serviceCredentials](../../configure-apps/file-schema/wcf/servicecredentials.md).

    6. Impostare `userNamePasswordValidationMode` su `Custom`.

        > [!IMPORTANT]
        > Se il valore `userNamePasswordValidationMode` non è impostato, WCF usa l'autenticazione di Windows anziché il validator personalizzato di nome utente e password.

    7. Impostare `customUserNamePasswordValidatorType` sul tipo che rappresenta il validator personalizzato di nome utente e password.

    Nell'esempio seguente viene illustrato il frammento `<serviceCredentials>` fino a questo punto:

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a>Esempio

Nel codice di esempio seguente viene dimostrato come creare un validator personalizzato di nome utente e password. Non utilizzare il codice che esegue l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> in un ambiente di produzione. Sostituire il codice con lo schema di convalida di nome utente e password personalizzato, operazione che potrebbe comportare il recupero di coppie di nome utente e password da un database.

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [Procedura: Usare il provider di appartenenze ASP.NET @ no__t-0
- [Autenticazione](authentication-in-wcf.md)

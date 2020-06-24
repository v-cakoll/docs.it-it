---
title: 'Procedura: usare provider di appartenenza ASP.NET'
description: Informazioni su come il provider di appartenenze ASP.NET supporta i siti Web che consentono agli utenti di creare un nome utente e una password per l'accesso senza avere un account di dominio di Windows.
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 6d527993dcf1fc5d5cd39bf22c3e772baf60e62f
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246727"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>Procedura: usare provider di appartenenza ASP.NET

Il provider di appartenenze ASP.NET è una funzionalità che consente agli sviluppatori ASP.NET di creare siti Web che consentono agli utenti di creare combinazioni univoche di nome utente e password. Con questa funzionalità qualsiasi utente può stabilire un account nel sito e accedere in modo esclusivo al sito e ai relativi servizi. Si tratta di una funzionalità in contrasto con la protezione di Windows, in base alla quale è necessario che gli utenti dispongano di un account in un dominio Windows. Al contrario, qualsiasi utente che fornisce le proprie credenziali (combinazione nome utente/password) può utilizzare il sito e i relativi servizi.

Per un'applicazione di esempio, vedere [appartenenza e provider di ruoli](../samples/membership-and-role-provider.md). Per informazioni sull'uso della funzionalità del provider di ruoli ASP.NET, vedere [procedura: usare il provider di ruoli ASP.NET con un servizio](how-to-use-the-aspnet-role-provider-with-a-service.md).

La funzionalità di appartenenza richiede l'utilizzo di un database SQL Server per archiviare le informazioni utente. La funzionalità include anche metodi per presentare una domanda agli utenti che hanno dimenticato la password.

Gli sviluppatori Windows Communication Foundation (WCF) possono avvalersi di queste funzionalità per motivi di sicurezza. Quando integrato in un'applicazione WCF, gli utenti devono fornire una combinazione di nome utente e password all'applicazione client WCF. Per trasferire i dati al servizio WCF, utilizzare un'associazione che supporta le credenziali nome utente/password, ad esempio <xref:System.ServiceModel.WSHttpBinding> (in configurazione, [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) ) e impostare il tipo di credenziale client su `UserName` . Nel servizio, la sicurezza WCF autentica l'utente in base al nome utente e alla password e assegna anche il ruolo specificato dal ruolo ASP.NET.

> [!NOTE]
> WCF non fornisce metodi per popolare il database con combinazioni di nome utente/password o altre informazioni utente.

### <a name="to-configure-the-membership-provider"></a>Per configurare il provider di appartenenza

1. Nel file di Web.config, nell' `system.web` elemento> <creare un `membership` elemento <>.

2. Sotto l'elemento `<membership>`, creare un elemento `<providers>`.

3. Come figlio dell' `providers` elemento> <, aggiungere un `<clear />` elemento per svuotare l'insieme di provider.

4. Nell' `<clear />` elemento creare un `add` elemento <> con gli attributi seguenti impostati sui valori appropriati: `name` , `type` , `connectionStringName` , `applicationName` , `enablePasswordRetrieval` , `enablePasswordReset` , `requiresQuestionAndAnswer` , `requiresUniqueEmail` e `passwordFormat` . L'attributo `name` viene utilizzato in seguito come valore nel file di configurazione. Nell'esempio seguente viene impostato su `SqlMembershipProvider`.

    Nell'esempio che segue viene illustrata la sezione di configurazione.

    ```xml
    <!-- Configure the Sql Membership Provider -->
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">
      <providers>
        <clear />
          <add
            name="SqlMembershipProvider"
            type="System.Web.Security.SqlMembershipProvider"
            connectionStringName="SqlConn"
            applicationName="MembershipAndRoleProviderSample"
            enablePasswordRetrieval="false"
            enablePasswordReset="false"
            requiresQuestionAndAnswer="false"
            requiresUniqueEmail="true"
            passwordFormat="Hashed" />
      </providers>
    </membership>
    ```

### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a>Per configurare la sicurezza del servizio per accettare la combinazione di nome utente/password

1. Nel file di configurazione, sotto l' [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento, aggiungere un [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) elemento.

2. Aggiungere un [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) alla sezione Bindings. Per ulteriori informazioni sulla creazione di un elemento di associazione WCF, vedere [procedura: specificare un'associazione al servizio nella configurazione](../how-to-specify-a-service-binding-in-configuration.md).

3. Impostare l'attributo `mode` dell'elemento `<security>` su `Message`.

4. Impostare l' `clientCredentialType` attributo dell'elemento <`message`> su `UserName` . Viene in questo modo specificato che un nome utente e una password saranno utilizzati come credenziale del client.

    Nell'esempio seguente viene illustrato il codice di configurazione per l'associazione.

    ```xml
    <system.serviceModel>
    <bindings>
      <wsHttpBinding>
      <!-- Set up a binding that uses UserName as the client credential type -->
        <binding name="MembershipBinding">
          <security mode ="Message">
            <message clientCredentialType ="UserName"/>
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    </system.serviceModel>
    ```

### <a name="to-configure-a-service-to-use-the-membership-provider"></a>Per configurare un servizio affinché utilizzi il provider di appartenenza

1. `<system.serviceModel>`Aggiungere un elemento come figlio dell'elemento [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md)

2. Aggiungere un oggetto [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) all' `behaviors` elemento <>.

3. Aggiungere un oggetto [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) e impostare l' `name` attributo su un valore appropriato.

4. Aggiungere un oggetto [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) all' `behavior` elemento <>.

5. Aggiungere un oggetto [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) all' `<serviceCredentials>` elemento.

6. Impostare l'attributo `userNamePasswordValidationMode` su `MembershipProvider`.

    > [!IMPORTANT]
    > Se il `userNamePasswordValidationMode` valore non è impostato, WCF usa l'autenticazione di Windows anziché il provider di appartenenze ASP.NET.

7. Impostare l'attributo `membershipProviderName` sul nome del provider (specificato al momento di aggiungere il provider nella prima procedura in questo argomento). Nell'esempio seguente viene illustrato il frammento `<serviceCredentials>` fino a questo punto.

    ```xml
    <behaviors>
       <serviceBehaviors>
          <behavior name="MyServiceBehavior">
             <serviceCredentials>
                <userNameAuthentication
                userNamePasswordValidationMode="MembershipProvider"
                membershipProviderName="SqlMembershipProvider" />
             </serviceCredentials>
          </behavior>
       </serviceBehaviors>
    </behaviors>
    ```

## <a name="example"></a>Esempio

Nel codice seguente viene mostrata la configurazione per un servizio che utilizza la funzionalità di appartenenza ASP.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">
        <endpoint address="http://microsoft.com/WCFservices/Calculator"
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />
      </service>
    </services>
    <behaviors>
      <serviceBehaviors>
        <behavior name="MyServiceBehavior">
          <serviceCredentials>
            <userNameAuthentication
              userNamePasswordValidationMode="MembershipProvider"
              membershipProviderName="SqlMembershipProvider" />
          </serviceCredentials>
        </behavior>
          </serviceBehaviors>
    </behaviors>
    <bindings>
      <wsHttpBinding>
        <binding name="MembershipBinding">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Procedura: usare il provider di ruoli ASP.NET con un servizio](how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Provider di appartenenza e di ruoli](../samples/membership-and-role-provider.md)

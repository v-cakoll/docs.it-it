---
title: 'Procedura: Usare provider di appartenenza ASP.NET'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 8011b026e857dd6e5815ef7da00c1c33db8b5b4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038714"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>Procedura: Usare provider di appartenenza ASP.NET
Il provider di appartenenza [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] è una funzionalità che consente agli sviluppatori di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] di creare siti Web che consentono agli utenti di creare combinazioni di nome utente e password univoche. Con questa funzionalità qualsiasi utente può stabilire un account nel sito e accedere in modo esclusivo al sito e ai relativi servizi. Si tratta di una funzionalità in contrasto con la protezione di Windows, in base alla quale è necessario che gli utenti dispongano di un account in un dominio Windows. Qualsiasi utente che fornisca le credenziali (ovvero nome utente e password) può utilizzare il sito e i relativi servizi.  
  
 Per un'applicazione di esempio, vedere [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Per informazioni sull'uso di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] funzionalità di provider di ruoli, vedere [come: Usare il Provider di ruoli ASP.NET con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
 La funzionalità di appartenenza richiede l'utilizzo di un database SQL Server per archiviare le informazioni utente. La funzionalità include anche metodi per presentare una domanda agli utenti che hanno dimenticato la password.  
  
 Gli sviluppatori di Windows Communication Foundation (WCF) possono sfruttare queste funzionalità per motivi di sicurezza. Se è integrato in un'applicazione WCF, gli utenti devono fornire una combinazione nome utente/password per l'applicazione client WCF. Per trasferire i dati al servizio WCF, utilizzare un'associazione che supporta le credenziali di nome e la password utente, ad esempio la <xref:System.ServiceModel.WSHttpBinding> (nella configurazione, il [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) e impostare il tipo di credenziale da client`UserName`. Nel servizio, autentica l'utente basato sul nome utente e la password, sicurezza WCF e assegna anche il ruolo specificato per il [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ruolo.  
  
> [!NOTE]
>  WCF non fornisce metodi per popolare il database con combinazioni di nome e la password utente o altre informazioni sull'utente.  
  
### <a name="to-configure-the-membership-provider"></a>Per configurare il provider di appartenenza  
  
1. Nel file Web. config, sotto il <`system.web`> elemento, creare un <`membership`> elemento.  
  
2. Sotto l'elemento `<membership>`, creare un elemento `<providers>`.  
  
3. Come finestra figlio di <`providers`> elemento, aggiungere un `<clear />` elemento per svuotare la raccolta di provider.  
  
4. Sotto il `<clear />` elemento, creare un <`add`> elemento con gli attributi seguenti impostati sui valori appropriati: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` , `requiresUniqueEmail`, e `passwordFormat`. L'attributo `name` viene utilizzato in seguito come valore nel file di configurazione. Nell'esempio seguente viene impostato su `SqlMembershipProvider`.  
  
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
  
1. Nel file di configurazione, sotto il [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento, aggiungere un [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento.  
  
2. Aggiungere un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) alla sezione delle associazioni. Per altre informazioni sulla creazione di un elemento di binding WCF, vedere [come: Specificare un'associazione al servizio nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
3. Impostare l'attributo `mode` dell'elemento `<security>` su `Message`.  
  
4. Impostare il `clientCredentialType` attributo del <`message`> elemento `UserName`. Viene in questo modo specificato che un nome utente e una password saranno utilizzati come credenziale del client.  
  
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
  
1. Come elemento figlio per il `<system.serviceModel>` elemento, aggiungere un' [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento  
  
2. Aggiungere un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) per la <`behaviors`> elemento.  
  
3. Aggiungere un [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) e impostare il `name` attributo su un valore appropriato.  
  
4. Aggiungere un [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) per la <`behavior`> elemento.  
  
5. Aggiungere un [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) per il `<serviceCredentials>` elemento.  
  
6. Impostare l'attributo `userNamePasswordValidationMode` su `MembershipProvider`.  
  
    > [!IMPORTANT]
    >  Se il `userNamePasswordValidationMode` valore non è impostato, WCF Usa l'autenticazione di Windows anziché il [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] provider di appartenenze.  
  
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

- [Procedura: Usare il Provider di ruoli ASP.NET con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Provider di appartenenza e di ruoli](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)

---
title: 'Procedura: usare provider di appartenenza ASP.NET'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 19fb83d21c77f3206c314a2e6c40562fcb75f151
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>Procedura: usare provider di appartenenza ASP.NET
Il provider di appartenenza [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] è una funzionalità che consente agli sviluppatori di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] di creare siti Web che consentono agli utenti di creare combinazioni di nome utente e password univoche. Con questa funzionalità qualsiasi utente può stabilire un account nel sito e accedere in modo esclusivo al sito e ai relativi servizi. Si tratta di una funzionalità in contrasto con la protezione di Windows, in base alla quale è necessario che gli utenti dispongano di un account in un dominio Windows. Qualsiasi utente che fornisca le credenziali (ovvero nome utente e password) può utilizzare il sito e i relativi servizi.  
  
 Per un'applicazione di esempio, vedere [Provider di appartenenze e ruoli](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Per informazioni sull'utilizzo di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] funzionalità del provider di ruoli, vedere [procedura: utilizzare il Provider di ruoli ASP.NET con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
 La funzionalità di appartenenza richiede l'utilizzo di un database SQL Server per archiviare le informazioni utente. La funzionalità include anche metodi per presentare una domanda agli utenti che hanno dimenticato la password.  
  
 Gli sviluppatori [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] possono sfruttare queste funzionalità a fini di sicurezza. In caso di integrazione in un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], gli utenti devono fornire una combinazione di nome utente e password all'applicazione client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Per trasferire i dati per il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] del servizio, utilizzare un'associazione che supporta le credenziali di nome e password utente, ad esempio il <xref:System.ServiceModel.WSHttpBinding> (nella configurazione, il [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) e impostare le credenziali client tipo di `UserName`. Nel servizio, la sicurezza [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] autentica l'utente sulla base del nome utente e della password, inoltre assegna il ruolo specificato dal ruolo [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non fornisce metodi per popolare il database con combinazioni di nome utente/password o altre informazioni utente.  
  
### <a name="to-configure-the-membership-provider"></a>Per configurare il provider di appartenenza  
  
1.  Nel file Web. config sotto il <`system.web`> elemento, creare una <`membership`> elemento.  
  
2.  Sotto l'elemento `<membership>`, creare un elemento `<providers>`.  
  
3.  Come elemento figlio di <`providers`> elemento, aggiungere un `<clear />` elemento per cancellare la raccolta di provider.  
  
4.  Sotto il `<clear />` elemento, creare un' <`add`> elemento con i seguenti attributi impostati su valori appropriati: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` , `requiresUniqueEmail`, e `passwordFormat`. L'attributo `name` viene utilizzato in seguito come valore nel file di configurazione. Nell'esempio seguente viene impostato su `SqlMembershipProvider`.  
  
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
  
1.  Nel file di configurazione, sotto il [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento, aggiungere un [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento.  
  
2.  Aggiungere un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) per la sezione delle associazioni. Per ulteriori informazioni sulla creazione di un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] elemento di associazione vedere [procedura: specificare un'associazione al servizio nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
3.  Impostare l'attributo `mode` dell'elemento `<security>` su `Message`.  
  
4.  Impostare il `clientCredentialType` attributo di <`message`> elemento `UserName`. Viene in questo modo specificato che un nome utente e una password saranno utilizzati come credenziale del client.  
  
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
  
1.  Come elemento figlio di `<system.serviceModel>` elemento, aggiungere un [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento  
  
2.  Aggiungere un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) per il <`behaviors`> elemento.  
  
3.  Aggiungere un [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) e impostare il `name` attributo su un valore appropriato.  
  
4.  Aggiungere un [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) per il <`behavior`> elemento.  
  
5.  Aggiungere un [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) per il `<serviceCredentials>` elemento.  
  
6.  Impostare l'attributo `userNamePasswordValidationMode` su `MembershipProvider`.  
  
    > [!IMPORTANT]
    >  Se il valore `userNamePasswordValidationMode` non è impostato, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza l'autenticazione di Windows invece del provider di appartenenza [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
7.  Impostare l'attributo `membershipProviderName` sul nome del provider (specificato al momento di aggiungere il provider nella prima procedura in questo argomento). Nell'esempio seguente viene illustrato il frammento `<serviceCredentials>` fino a questo punto.  
  
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
 [Procedura: Usare il provider di ruoli ASP.NET con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [Provider di appartenenza e di ruoli](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)

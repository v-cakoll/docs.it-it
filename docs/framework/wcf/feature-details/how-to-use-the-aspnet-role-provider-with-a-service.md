---
title: 'Procedura: Usare il Provider di ruoli ASP.NET con un servizio'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 0ad581a6967c759095d85d946a8557b47a075355
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658234"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Procedura: Usare il Provider di ruoli ASP.NET con un servizio
Il provider di ruoli [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] (insieme al provider di appartenenza [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]) è una funzionalità grazie alla quale gli sviluppatori [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] sono in grado di creare siti Web che consentono agli utenti di creare un account in un sito e di acquisire ruoli a scopo di autorizzazione. Con questa funzionalità qualsiasi utente può stabilire un account nel sito e accedere in modo esclusivo al sito e ai relativi servizi. Si tratta di una funzionalità in contrasto con la protezione di Windows, in base alla quale è necessario che gli utenti dispongano di un account in un dominio Windows. Qualsiasi utente che fornisca le credenziali (ovvero nome utente e password) può utilizzare il sito e i relativi servizi.  
  
 Per un'applicazione di esempio, vedere [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Per altre informazioni sul [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] funzionalità del provider di appartenenza, vedere [come: Usare il Provider di appartenenze ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
 La funzionalità del provider di ruoli utilizza un database SQL Server per archiviare informazioni utente. Gli sviluppatori di Windows Communication Foundation (WCF) possono sfruttare queste funzionalità per motivi di sicurezza. Se è integrato in un'applicazione WCF, gli utenti devono fornire una combinazione nome utente/password per l'applicazione client WCF. Per abilitare WCF a utilizzare il database, è necessario creare un'istanza del <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> classe, impostare relativi <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> proprietà <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>e aggiungere l'istanza alla raccolta dei comportamenti per il <xref:System.ServiceModel.ServiceHost> che ospita il servizio.  
  
### <a name="to-configure-the-role-provider"></a>Per configurare il provider di ruoli  
  
1.  Nel file Web. config, sotto il <`system.web`> elemento, aggiungere un <`roleManager`> e impostare relativo `enabled` attributo `true`.  
  
2.  Impostare l'attributo `defaultProvider` su `SqlRoleProvider`.  
  
3.  Come finestra figlio di <`roleManager`> elemento, aggiungere un <`providers`> elemento.  
  
4.  Come finestra figlio di <`providers`> elemento, aggiungere un <`add`> elemento con gli attributi seguenti impostati sui valori appropriati: `name`, `type`, `connectionStringName`, e `applicationName`, come illustrato nell'esempio seguente.  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"   
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"   
           type="System.Web.Security.SqlRoleProvider"   
           connectionStringName="SqlConn"   
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a>Per configurare il servizio per l'utilizzo del provider di ruoli  
  
1.  Nel file Web. config, aggiungere un [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento.  
  
2.  Aggiungere un [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento per il <`system.ServiceModel`> elemento.  
  
3.  Aggiungere un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) per la <`behaviors`> elemento.  
  
4.  Aggiungere un [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) e impostare il `name` attributo su un valore appropriato.  
  
5.  Aggiungere un [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) per la <`behavior`> elemento.  
  
6.  Impostare l'attributo `principalPermissionMode` su `UseAspNetRoles`.  
  
7.  Impostare l'attributo `roleProviderName` su `SqlRoleProvider`. Nell'esempio seguente viene illustrata una parte della configurazione.  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a>Vedere anche
- [Provider di appartenenza e di ruoli](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [Procedura: Usare il Provider di appartenenze ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)

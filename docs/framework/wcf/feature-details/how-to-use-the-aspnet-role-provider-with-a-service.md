---
title: 'Procedura: usare il provider di ruoli ASP.NET con un servizio'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: ddfedeb2491998f64ab241ceba303d50d0714351
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184766"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Procedura: usare il provider di ruoli ASP.NET con un servizio

Il provider di ruoli ASP.NET (in combinazione con il provider di appartenenze ASP.NET) è una funzionalità che consente agli sviluppatori di ASP.NET di creare siti Web che consentono agli utenti di creare un account con un sito e di assegnare ruoli per scopi di autorizzazione. Con questa funzionalità qualsiasi utente può stabilire un account nel sito e accedere in modo esclusivo al sito e ai relativi servizi. Si tratta di una funzionalità in contrasto con la protezione di Windows, in base alla quale è necessario che gli utenti dispongano di un account in un dominio Windows. Al contrario, qualsiasi utente che fornisce le proprie credenziali (la combinazione nome utente/password) può utilizzare il sito e i relativi servizi.  
  
Per un'applicazione di esempio, vedere [Provider di appartenenze e ruoli](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Per ulteriori informazioni sulla funzionalità del provider di appartenenze ASP.NET, vedere [Procedura: utilizzare il provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)di appartenenze ASP.NET .  
  
La funzionalità del provider di ruoli utilizza un database SQL Server per archiviare informazioni utente. Gli sviluppatori di Windows Communication Foundation (WCF) possono sfruttare queste funzionalità per motivi di sicurezza. Quando sono integrati in un'applicazione WCF, gli utenti devono fornire una combinazione nome utente/password all'applicazione client WCF. Per consentire a WCF di utilizzare il database, è <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> necessario <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>creare un'istanza della classe, impostarne <xref:System.ServiceModel.ServiceHost> la <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> proprietà su e aggiungere l'istanza alla raccolta di comportamenti all'hosting del servizio.  
  
## <a name="configure-the-role-provider"></a>Configurare il provider di ruoli  
  
1. Nel file Web.config, sotto `system.web` l'elemento <`roleManager`>, aggiungere `enabled` un `true`elemento <> e impostarne l'attributo su .  
  
2. Impostare l'attributo `defaultProvider` su `SqlRoleProvider`.  
  
3. Come elemento figlio `roleManager` all'elemento> `providers` <, aggiungere un elemento <>.  
  
4. Come elemento figlio `providers` dell'elemento <`add`> , aggiungere un elemento> `name` `type`<`connectionStringName`con `applicationName`i seguenti attributi impostati sui valori appropriati: , , e , come illustrato nell'esempio seguente.  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a>Configurare il servizio per l'utilizzo del provider di ruoliConfigure the service to use the role provider  
  
1. Nel file Web.config aggiungere un [ \<elemento system.serviceModel>.](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
2. Aggiungere [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) un elemento>dei `system.ServiceModel` comportamenti all'elemento <>.  
  
3. Aggiungere un [ \<>serviceBehaviors](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) all'elemento <`behaviors`>.  
  
4. Aggiungere [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) un elemento>`name` di comportamento e impostare l'attributo su un valore appropriato.  
  
5. Aggiungere un [ \<>serviceAuthorization](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) all'elemento> <. `behavior`  
  
6. Impostare l'attributo `principalPermissionMode` su `UseAspNetRoles`.  
  
7. Impostare l'attributo `roleProviderName` su `SqlRoleProvider`. Nell'esempio seguente viene illustrata una parte della configurazione.  
  
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
- [Procedura: usare provider di appartenenza ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)

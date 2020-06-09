---
title: 'Procedura: usare il provider di ruoli ASP.NET con un servizio'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 45eeda046e877b4379d7d0e5edd90fac305f5e44
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595297"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Procedura: usare il provider di ruoli ASP.NET con un servizio

Il provider di ruoli ASP.NET (insieme al provider di appartenenze ASP.NET) è una funzionalità che consente agli sviluppatori di ASP.NET di creare siti Web che consentono agli utenti di creare un account con un sito e di assegnare ruoli a scopo di autorizzazione. Con questa funzionalità qualsiasi utente può stabilire un account nel sito e accedere in modo esclusivo al sito e ai relativi servizi. Si tratta di una funzionalità in contrasto con la protezione di Windows, in base alla quale è necessario che gli utenti dispongano di un account in un dominio Windows. Al contrario, qualsiasi utente che fornisce le proprie credenziali (combinazione nome utente/password) può utilizzare il sito e i relativi servizi.  
  
Per un'applicazione di esempio, vedere [appartenenza e provider di ruoli](../samples/membership-and-role-provider.md). Per altre informazioni sulla funzionalità del provider di appartenenze ASP.NET, vedere [procedura: usare il provider di appartenenze ASP.NET](how-to-use-the-aspnet-membership-provider.md).  
  
La funzionalità del provider di ruoli utilizza un database SQL Server per archiviare informazioni utente. Gli sviluppatori Windows Communication Foundation (WCF) possono avvalersi di queste funzionalità per motivi di sicurezza. Quando integrato in un'applicazione WCF, gli utenti devono fornire una combinazione di nome utente e password all'applicazione client WCF. Per consentire a WCF di utilizzare il database, è necessario creare un'istanza della <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> classe, impostarne la <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> proprietà su <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> e aggiungere l'istanza alla raccolta di comportamenti nell'oggetto <xref:System.ServiceModel.ServiceHost> che ospita il servizio.  
  
## <a name="configure-the-role-provider"></a>Configurare il provider di ruoli  
  
1. Nel file Web. config, sotto l'elemento < `system.web` > aggiungere un `roleManager` elemento < > e impostare il relativo `enabled` attributo su `true` .  
  
2. Impostare l'attributo `defaultProvider` su `SqlRoleProvider`.  
  
3. Come elemento figlio dell'elemento <`roleManager`>, aggiungere un elemento <`providers`>.  
  
4. Come figlio dell' `providers` elemento> <, aggiungere un `add` elemento <> con gli attributi seguenti impostati sui valori appropriati: `name` , `type` , `connectionStringName` e `applicationName` , come illustrato nell'esempio seguente.  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a>Configurare il servizio per l'utilizzo del provider di ruoli  
  
1. Nel file Web. config aggiungere un [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento.  
  
2. Aggiungere un [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elemento all'elemento <`system.ServiceModel`>.  
  
3. Aggiungere un oggetto [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) all' `behaviors` elemento <>.  
  
4. Aggiungere un [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento e impostare l' `name` attributo su un valore appropriato.  
  
5. Aggiungere un oggetto [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) all' `behavior` elemento <>.  
  
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

- [Provider di appartenenza e di ruoli](../samples/membership-and-role-provider.md)
- [Procedura: usare provider di appartenenza ASP.NET](how-to-use-the-aspnet-membership-provider.md)

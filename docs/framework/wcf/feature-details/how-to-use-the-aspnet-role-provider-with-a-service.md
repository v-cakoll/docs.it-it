---
title: 'Procedura: usare il provider di ruoli ASP.NET con un servizio'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9180ebe687d61315a66160a6fc95569a0e6b8e72
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Procedura: usare il provider di ruoli ASP.NET con un servizio
Il provider di ruoli [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] (insieme al provider di appartenenza [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]) è una funzionalità grazie alla quale gli sviluppatori [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] sono in grado di creare siti Web che consentono agli utenti di creare un account in un sito e di acquisire ruoli a scopo di autorizzazione. Con questa funzionalità qualsiasi utente può stabilire un account nel sito e accedere in modo esclusivo al sito e ai relativi servizi. Si tratta di una funzionalità in contrasto con la protezione di Windows, in base alla quale è necessario che gli utenti dispongano di un account in un dominio Windows. Qualsiasi utente che fornisca le credenziali (ovvero nome utente e password) può utilizzare il sito e i relativi servizi.  
  
 Per un'applicazione di esempio, vedere [Provider di appartenenze e ruoli](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Per ulteriori informazioni sul [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] funzionalità del provider di appartenenza, vedere [procedura: utilizzare il Provider di appartenenze ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
 La funzionalità del provider di ruoli utilizza un database SQL Server per archiviare informazioni utente. Gli sviluppatori [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] possono sfruttare queste funzionalità a fini di sicurezza. Dopo l'integrazione in un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], gli utenti devono fornire nome utente e password all'applicazione client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Per attivare l'utilizzo del database in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], è necessario creare un'istanza della classe <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>, impostare la proprietà <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> su <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> e aggiungere l'istanza alla raccolta dei comportamenti nella classe <xref:System.ServiceModel.ServiceHost> in cui risiede il servizio.  
  
### <a name="to-configure-the-role-provider"></a>Per configurare il provider di ruoli  
  
1.  Nel file Web. config, sotto il <`system.web`> elemento, aggiungere un <`roleManager`> elemento e impostare il relativo `enabled` attributo `true`.  
  
2.  Impostare l'attributo `defaultProvider` su `SqlRoleProvider`.  
  
3.  Come elemento figlio di <`roleManager`> elemento, aggiungere un <`providers`> elemento.  
  
4.  Come elemento figlio di <`providers`> elemento, aggiungere un <`add`> elemento con i seguenti attributi impostati su valori appropriati: `name`, `type`, `connectionStringName`, e `applicationName`, come illustrato nell'esempio seguente.  
  
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
  
3.  Aggiungere un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) per il <`behaviors`> elemento.  
  
4.  Aggiungere un [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento e impostare il `name` attributo su un valore appropriato.  
  
5.  Aggiungere un [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) per il <`behavior`> elemento.  
  
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
 [Provider di appartenenza e di ruoli](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 [Procedura: Usare provider di appartenenza ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)

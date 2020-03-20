---
title: 'Procedura: usare il provider di ruoli ASP.NET di Gestione autorizzazioni con un servizio'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 009b96defdf27591ddb98afaa684745b5fcbe0d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184803"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>Procedura: usare il provider di ruoli ASP.NET di Gestione autorizzazioni con un servizio
Quando ASP.NET ospita un servizio Web, è possibile integrare Gestione autorizzazioni nell'applicazione per fornire l'autorizzazione al servizio. Gestione autorizzazioni consente a uno sviluppatore di applicazioni di definire singole operazioni che possono essere raggruppate per formare attività. Un amministratore può quindi autorizzare ruoli a eseguire attività specifiche o singole operazioni. Gestione autorizzazioni fornisce uno strumento di amministrazione come uno snap-in MMC (Microsoft Management Console) per gestire ruoli, attività, operazioni e utenti. Gli amministratori configurano un archivio criteri di Gestione autorizzazioni in un file XML, in Active Directory o in un archivio ADAM (Active Directory Application Mode).  
  
 Gestione autorizzazioni è integrato nell'applicazione configurando Gestione autorizzazioni ASP.NET provider di ruoli per l'applicazione ASP.NET che ospita il servizio Web. Analogamente ad altri provider di ruoli ASP.NET, `providers` il provider di ruoli ASP.NET Gestione autorizzazioni viene configurato utilizzando l'elemento <>.  
  
 L'esempio di codice seguente costituisce una parte di un file di configurazione per un servizio Web che sta integrando Gestione autorizzazioni nell'applicazione.  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 Per altre informazioni sull'integrazione di un provider di ruoli ASP.NET con un'applicazione WCF, vedere [Procedura: utilizzare il provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)di ruoli ASP.NET con un servizio . Per ulteriori informazioni sull'utilizzo di Gestione autorizzazioni con ASP.NET, vedere [Procedura: utilizzare Gestione autorizzazioni (AzMan) con ASP.NET 2.0.](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10))  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: usare il provider di ruoli ASP.NET con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)

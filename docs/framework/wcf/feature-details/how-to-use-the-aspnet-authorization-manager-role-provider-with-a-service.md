---
title: 'Procedura: Usare il provider di ruoli ASP.NET di Gestione autorizzazioni con un servizio'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 778af929b4cfc96ce0683d304be5f8fb87a0e47b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880193"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>Procedura: Usare il provider di ruoli ASP.NET di Gestione autorizzazioni con un servizio
Quando ASP.NET ospita un servizio Web, è possibile integrare Gestione autorizzazioni all'applicazione per fornire l'autorizzazione al servizio. Gestione autorizzazioni consente a uno sviluppatore di applicazioni di definire singole operazioni che possono essere raggruppate per formare attività. Un amministratore può quindi autorizzare ruoli a eseguire attività specifiche o singole operazioni. Gestione autorizzazioni fornisce uno strumento di amministrazione come uno snap-in MMC (Microsoft Management Console) per gestire ruoli, attività, operazioni e utenti. Gli amministratori configurano un archivio criteri di Gestione autorizzazioni in un file XML, in Active Directory o in un archivio ADAM (Active Directory Application Mode).  
  
 Gestione autorizzazioni viene integrato nell'applicazione configurando il provider di ruoli ASP.NET di gestione autorizzazioni per l'applicazione ASP.NET che ospita il servizio Web. Come altri provider di ruoli ASP.NET, il provider di ruoli ASP.NET di gestione autorizzazioni viene configurato tramite la <`providers`> elemento.  
  
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
  
 Per altre informazioni sull'integrazione di un provider di ruoli ASP.NET con un'applicazione WCF, vedere [come: Usare il Provider di ruoli ASP.NET con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md). Per altre informazioni sull'uso di gestione autorizzazioni con ASP.NET, vedere [come: Utilizzare Gestione autorizzazioni (AzMan) con ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Usare il Provider di ruoli ASP.NET con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)

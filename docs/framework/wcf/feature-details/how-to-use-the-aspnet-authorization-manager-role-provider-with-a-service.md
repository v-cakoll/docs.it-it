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
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="ca0e0-102">Procedura: Usare il provider di ruoli ASP.NET di Gestione autorizzazioni con un servizio</span><span class="sxs-lookup"><span data-stu-id="ca0e0-102">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>
<span data-ttu-id="ca0e0-103">Quando ASP.NET ospita un servizio Web, è possibile integrare Gestione autorizzazioni all'applicazione per fornire l'autorizzazione al servizio.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-103">When ASP.NET hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="ca0e0-104">Gestione autorizzazioni consente a uno sviluppatore di applicazioni di definire singole operazioni che possono essere raggruppate per formare attività.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-104">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="ca0e0-105">Un amministratore può quindi autorizzare ruoli a eseguire attività specifiche o singole operazioni.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-105">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="ca0e0-106">Gestione autorizzazioni fornisce uno strumento di amministrazione come uno snap-in MMC (Microsoft Management Console) per gestire ruoli, attività, operazioni e utenti.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-106">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="ca0e0-107">Gli amministratori configurano un archivio criteri di Gestione autorizzazioni in un file XML, in Active Directory o in un archivio ADAM (Active Directory Application Mode).</span><span class="sxs-lookup"><span data-stu-id="ca0e0-107">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="ca0e0-108">Gestione autorizzazioni viene integrato nell'applicazione configurando il provider di ruoli ASP.NET di gestione autorizzazioni per l'applicazione ASP.NET che ospita il servizio Web.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-108">Authorization Manager is Integrated into the application by configuring the Authorization Manager ASP.NET role provider for the ASP.NET application that is hosting the Web service.</span></span> <span data-ttu-id="ca0e0-109">Come altri provider di ruoli ASP.NET, il provider di ruoli ASP.NET di gestione autorizzazioni viene configurato tramite la <`providers`> elemento.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-109">Like other ASP.NET role providers, the Authorization Manager ASP.NET role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="ca0e0-110">L'esempio di codice seguente costituisce una parte di un file di configurazione per un servizio Web che sta integrando Gestione autorizzazioni nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-110">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
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
  
 <span data-ttu-id="ca0e0-111">Per altre informazioni sull'integrazione di un provider di ruoli ASP.NET con un'applicazione WCF, vedere [come: Usare il Provider di ruoli ASP.NET con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="ca0e0-111">For more information about integrating an ASP.NET role provider with a WCF application, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> <span data-ttu-id="ca0e0-112">Per altre informazioni sull'uso di gestione autorizzazioni con ASP.NET, vedere [come: Utilizzare Gestione autorizzazioni (AzMan) con ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).</span><span class="sxs-lookup"><span data-stu-id="ca0e0-112">For more information about using Authorization Manager with ASP.NET, see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca0e0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca0e0-113">See also</span></span>

- [<span data-ttu-id="ca0e0-114">Procedura: Usare il Provider di ruoli ASP.NET con un servizio</span><span class="sxs-lookup"><span data-stu-id="ca0e0-114">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)

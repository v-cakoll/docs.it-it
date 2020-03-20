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
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="9a611-102">Procedura: usare il provider di ruoli ASP.NET con un servizio</span><span class="sxs-lookup"><span data-stu-id="9a611-102">How to: Use the ASP.NET Role Provider with a Service</span></span>

<span data-ttu-id="9a611-103">Il provider di ruoli ASP.NET (in combinazione con il provider di appartenenze ASP.NET) è una funzionalità che consente agli sviluppatori di ASP.NET di creare siti Web che consentono agli utenti di creare un account con un sito e di assegnare ruoli per scopi di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a611-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="9a611-104">Con questa funzionalità qualsiasi utente può stabilire un account nel sito e accedere in modo esclusivo al sito e ai relativi servizi.</span><span class="sxs-lookup"><span data-stu-id="9a611-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="9a611-105">Si tratta di una funzionalità in contrasto con la protezione di Windows, in base alla quale è necessario che gli utenti dispongano di un account in un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="9a611-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="9a611-106">Al contrario, qualsiasi utente che fornisce le proprie credenziali (la combinazione nome utente/password) può utilizzare il sito e i relativi servizi.</span><span class="sxs-lookup"><span data-stu-id="9a611-106">Instead, any user who supplies their credentials (the user name/password combination) can use the site and its services.</span></span>  
  
<span data-ttu-id="9a611-107">Per un'applicazione di esempio, vedere [Provider di appartenenze e ruoli](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="9a611-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="9a611-108">Per ulteriori informazioni sulla funzionalità del provider di appartenenze ASP.NET, vedere [Procedura: utilizzare il provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)di appartenenze ASP.NET .</span><span class="sxs-lookup"><span data-stu-id="9a611-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
<span data-ttu-id="9a611-109">La funzionalità del provider di ruoli utilizza un database SQL Server per archiviare informazioni utente.</span><span class="sxs-lookup"><span data-stu-id="9a611-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="9a611-110">Gli sviluppatori di Windows Communication Foundation (WCF) possono sfruttare queste funzionalità per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9a611-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="9a611-111">Quando sono integrati in un'applicazione WCF, gli utenti devono fornire una combinazione nome utente/password all'applicazione client WCF.</span><span class="sxs-lookup"><span data-stu-id="9a611-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="9a611-112">Per consentire a WCF di utilizzare il database, è <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> necessario <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>creare un'istanza della classe, impostarne <xref:System.ServiceModel.ServiceHost> la <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> proprietà su e aggiungere l'istanza alla raccolta di comportamenti all'hosting del servizio.</span><span class="sxs-lookup"><span data-stu-id="9a611-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
## <a name="configure-the-role-provider"></a><span data-ttu-id="9a611-113">Configurare il provider di ruoli</span><span class="sxs-lookup"><span data-stu-id="9a611-113">Configure the role provider</span></span>  
  
1. <span data-ttu-id="9a611-114">Nel file Web.config, sotto `system.web` l'elemento <`roleManager`>, aggiungere `enabled` un `true`elemento <> e impostarne l'attributo su .</span><span class="sxs-lookup"><span data-stu-id="9a611-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="9a611-115">Impostare l'attributo `defaultProvider` su `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="9a611-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="9a611-116">Come elemento figlio `roleManager` all'elemento> `providers` <, aggiungere un elemento <>.</span><span class="sxs-lookup"><span data-stu-id="9a611-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="9a611-117">Come elemento figlio `providers` dell'elemento <`add`> , aggiungere un elemento> `name` `type`<`connectionStringName`con `applicationName`i seguenti attributi impostati sui valori appropriati: , , e , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9a611-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="9a611-118">Configurare il servizio per l'utilizzo del provider di ruoliConfigure the service to use the role provider</span><span class="sxs-lookup"><span data-stu-id="9a611-118">Configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="9a611-119">Nel file Web.config aggiungere un [ \<elemento system.serviceModel>.](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9a611-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="9a611-120">Aggiungere [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) un elemento>dei `system.ServiceModel` comportamenti all'elemento <>.</span><span class="sxs-lookup"><span data-stu-id="9a611-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="9a611-121">Aggiungere un [ \<>serviceBehaviors](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) all'elemento <`behaviors`>.</span><span class="sxs-lookup"><span data-stu-id="9a611-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="9a611-122">Aggiungere [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) un elemento>`name` di comportamento e impostare l'attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="9a611-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="9a611-123">Aggiungere un [ \<>serviceAuthorization](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) all'elemento> <. `behavior`</span><span class="sxs-lookup"><span data-stu-id="9a611-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="9a611-124">Impostare l'attributo `principalPermissionMode` su `UseAspNetRoles`.</span><span class="sxs-lookup"><span data-stu-id="9a611-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="9a611-125">Impostare l'attributo `roleProviderName` su `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="9a611-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="9a611-126">Nell'esempio seguente viene illustrata una parte della configurazione.</span><span class="sxs-lookup"><span data-stu-id="9a611-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9a611-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a611-127">See also</span></span>

- [<span data-ttu-id="9a611-128">Provider di appartenenza e di ruoli</span><span class="sxs-lookup"><span data-stu-id="9a611-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [<span data-ttu-id="9a611-129">Procedura: usare provider di appartenenza ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9a611-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)

---
title: 'Procedura: usare il provider di ruoli ASP.NET con un servizio'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bdddbd39a528e6abd6a0268db310b6173849f19b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="be989-102">Procedura: usare il provider di ruoli ASP.NET con un servizio</span><span class="sxs-lookup"><span data-stu-id="be989-102">How to: Use the ASP.NET Role Provider with a Service</span></span>
<span data-ttu-id="be989-103">Il provider di ruoli [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] (insieme al provider di appartenenza [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]) è una funzionalità grazie alla quale gli sviluppatori [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] sono in grado di creare siti Web che consentono agli utenti di creare un account in un sito e di acquisire ruoli a scopo di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="be989-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider (in conjunction with the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider) is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="be989-104">Con questa funzionalità qualsiasi utente può stabilire un account nel sito e accedere in modo esclusivo al sito e ai relativi servizi.</span><span class="sxs-lookup"><span data-stu-id="be989-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="be989-105">Si tratta di una funzionalità in contrasto con la protezione di Windows, in base alla quale è necessario che gli utenti dispongano di un account in un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="be989-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="be989-106">Qualsiasi utente che fornisca le credenziali (ovvero nome utente e password) può utilizzare il sito e i relativi servizi.</span><span class="sxs-lookup"><span data-stu-id="be989-106">Instead, any user who supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="be989-107">Per un'applicazione di esempio, vedere [Provider di appartenenze e ruoli](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="be989-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="be989-108">il [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] funzionalità del provider di appartenenza, vedere [procedura: utilizzare il Provider di appartenenze ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="be989-108"> the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
 <span data-ttu-id="be989-109">La funzionalità del provider di ruoli utilizza un database SQL Server per archiviare informazioni utente.</span><span class="sxs-lookup"><span data-stu-id="be989-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="be989-110">Gli sviluppatori [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] possono sfruttare queste funzionalità a fini di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="be989-110">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="be989-111">Dopo l'integrazione in un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], gli utenti devono fornire nome utente e password all'applicazione client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be989-111">When integrated into a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, users must supply a user name/password combination to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span> <span data-ttu-id="be989-112">Per attivare l'utilizzo del database in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], è necessario creare un'istanza della classe <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>, impostare la proprietà <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> su <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> e aggiungere l'istanza alla raccolta dei comportamenti nella classe <xref:System.ServiceModel.ServiceHost> in cui risiede il servizio.</span><span class="sxs-lookup"><span data-stu-id="be989-112">To enable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
### <a name="to-configure-the-role-provider"></a><span data-ttu-id="be989-113">Per configurare il provider di ruoli</span><span class="sxs-lookup"><span data-stu-id="be989-113">To configure the role provider</span></span>  
  
1.  <span data-ttu-id="be989-114">Nel file Web. config, sotto il <`system.web`> elemento, aggiungere un <`roleManager`> elemento e impostare il relativo `enabled` attributo `true`.</span><span class="sxs-lookup"><span data-stu-id="be989-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2.  <span data-ttu-id="be989-115">Impostare l'attributo `defaultProvider` su `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="be989-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3.  <span data-ttu-id="be989-116">Come elemento figlio di <`roleManager`> elemento, aggiungere un <`providers`> elemento.</span><span class="sxs-lookup"><span data-stu-id="be989-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4.  <span data-ttu-id="be989-117">Come elemento figlio di <`providers`> elemento, aggiungere un <`add`> elemento con i seguenti attributi impostati su valori appropriati: `name`, `type`, `connectionStringName`, e `applicationName`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="be989-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="be989-118">Per configurare il servizio per l'utilizzo del provider di ruoli</span><span class="sxs-lookup"><span data-stu-id="be989-118">To configure the service to use the role provider</span></span>  
  
1.  <span data-ttu-id="be989-119">Nel file Web. config, aggiungere un [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="be989-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="be989-120">Aggiungere un [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento per il <`system.ServiceModel`> elemento.</span><span class="sxs-lookup"><span data-stu-id="be989-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3.  <span data-ttu-id="be989-121">Aggiungere un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) per il <`behaviors`> elemento.</span><span class="sxs-lookup"><span data-stu-id="be989-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4.  <span data-ttu-id="be989-122">Aggiungere un [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento e impostare il `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="be989-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5.  <span data-ttu-id="be989-123">Aggiungere un [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) per il <`behavior`> elemento.</span><span class="sxs-lookup"><span data-stu-id="be989-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6.  <span data-ttu-id="be989-124">Impostare l'attributo `principalPermissionMode` su `UseAspNetRoles`.</span><span class="sxs-lookup"><span data-stu-id="be989-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7.  <span data-ttu-id="be989-125">Impostare l'attributo `roleProviderName` su `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="be989-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="be989-126">Nell'esempio seguente viene illustrata una parte della configurazione.</span><span class="sxs-lookup"><span data-stu-id="be989-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="be989-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be989-127">See Also</span></span>  
 [<span data-ttu-id="be989-128">Provider di appartenenze e ruoli</span><span class="sxs-lookup"><span data-stu-id="be989-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 [<span data-ttu-id="be989-129">Procedura: utilizzare il Provider di appartenenze ASP.NET</span><span class="sxs-lookup"><span data-stu-id="be989-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)

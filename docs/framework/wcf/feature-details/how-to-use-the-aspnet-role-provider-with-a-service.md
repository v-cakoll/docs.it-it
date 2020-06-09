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
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="640a9-102">Procedura: usare il provider di ruoli ASP.NET con un servizio</span><span class="sxs-lookup"><span data-stu-id="640a9-102">How to: Use the ASP.NET Role Provider with a Service</span></span>

<span data-ttu-id="640a9-103">Il provider di ruoli ASP.NET (insieme al provider di appartenenze ASP.NET) è una funzionalità che consente agli sviluppatori di ASP.NET di creare siti Web che consentono agli utenti di creare un account con un sito e di assegnare ruoli a scopo di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="640a9-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="640a9-104">Con questa funzionalità qualsiasi utente può stabilire un account nel sito e accedere in modo esclusivo al sito e ai relativi servizi.</span><span class="sxs-lookup"><span data-stu-id="640a9-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="640a9-105">Si tratta di una funzionalità in contrasto con la protezione di Windows, in base alla quale è necessario che gli utenti dispongano di un account in un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="640a9-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="640a9-106">Al contrario, qualsiasi utente che fornisce le proprie credenziali (combinazione nome utente/password) può utilizzare il sito e i relativi servizi.</span><span class="sxs-lookup"><span data-stu-id="640a9-106">Instead, any user who supplies their credentials (the user name/password combination) can use the site and its services.</span></span>  
  
<span data-ttu-id="640a9-107">Per un'applicazione di esempio, vedere [appartenenza e provider di ruoli](../samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="640a9-107">For a sample application, see [Membership and Role Provider](../samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="640a9-108">Per altre informazioni sulla funzionalità del provider di appartenenze ASP.NET, vedere [procedura: usare il provider di appartenenze ASP.NET](how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="640a9-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
<span data-ttu-id="640a9-109">La funzionalità del provider di ruoli utilizza un database SQL Server per archiviare informazioni utente.</span><span class="sxs-lookup"><span data-stu-id="640a9-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="640a9-110">Gli sviluppatori Windows Communication Foundation (WCF) possono avvalersi di queste funzionalità per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="640a9-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="640a9-111">Quando integrato in un'applicazione WCF, gli utenti devono fornire una combinazione di nome utente e password all'applicazione client WCF.</span><span class="sxs-lookup"><span data-stu-id="640a9-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="640a9-112">Per consentire a WCF di utilizzare il database, è necessario creare un'istanza della <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> classe, impostarne la <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> proprietà su <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> e aggiungere l'istanza alla raccolta di comportamenti nell'oggetto <xref:System.ServiceModel.ServiceHost> che ospita il servizio.</span><span class="sxs-lookup"><span data-stu-id="640a9-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
## <a name="configure-the-role-provider"></a><span data-ttu-id="640a9-113">Configurare il provider di ruoli</span><span class="sxs-lookup"><span data-stu-id="640a9-113">Configure the role provider</span></span>  
  
1. <span data-ttu-id="640a9-114">Nel file Web. config, sotto l'elemento < `system.web` > aggiungere un `roleManager` elemento < > e impostare il relativo `enabled` attributo su `true` .</span><span class="sxs-lookup"><span data-stu-id="640a9-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="640a9-115">Impostare l'attributo `defaultProvider` su `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="640a9-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="640a9-116">Come elemento figlio dell'elemento <`roleManager`>, aggiungere un elemento <`providers`>.</span><span class="sxs-lookup"><span data-stu-id="640a9-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="640a9-117">Come figlio dell' `providers` elemento> <, aggiungere un `add` elemento <> con gli attributi seguenti impostati sui valori appropriati: `name` , `type` , `connectionStringName` e `applicationName` , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="640a9-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="640a9-118">Configurare il servizio per l'utilizzo del provider di ruoli</span><span class="sxs-lookup"><span data-stu-id="640a9-118">Configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="640a9-119">Nel file Web. config aggiungere un [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="640a9-119">In the Web.config file, add a [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="640a9-120">Aggiungere un [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elemento all'elemento <`system.ServiceModel`>.</span><span class="sxs-lookup"><span data-stu-id="640a9-120">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="640a9-121">Aggiungere un oggetto [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) all' `behaviors` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="640a9-121">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="640a9-122">Aggiungere un [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento e impostare l' `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="640a9-122">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="640a9-123">Aggiungere un oggetto [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) all' `behavior` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="640a9-123">Add a [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="640a9-124">Impostare l'attributo `principalPermissionMode` su `UseAspNetRoles`.</span><span class="sxs-lookup"><span data-stu-id="640a9-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="640a9-125">Impostare l'attributo `roleProviderName` su `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="640a9-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="640a9-126">Nell'esempio seguente viene illustrata una parte della configurazione.</span><span class="sxs-lookup"><span data-stu-id="640a9-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="640a9-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="640a9-127">See also</span></span>

- [<span data-ttu-id="640a9-128">Provider di appartenenza e di ruoli</span><span class="sxs-lookup"><span data-stu-id="640a9-128">Membership and Role Provider</span></span>](../samples/membership-and-role-provider.md)
- [<span data-ttu-id="640a9-129">Procedura: usare provider di appartenenza ASP.NET</span><span class="sxs-lookup"><span data-stu-id="640a9-129">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)

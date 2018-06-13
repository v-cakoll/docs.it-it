---
title: 'Procedura: usare il provider di ruoli ASP.NET con un servizio'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 846caf59816ee23166fb382a0c36ac0fed9df151
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492958"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="84a03-102">Procedura: usare il provider di ruoli ASP.NET con un servizio</span><span class="sxs-lookup"><span data-stu-id="84a03-102">How to: Use the ASP.NET Role Provider with a Service</span></span>
<span data-ttu-id="84a03-103">Il provider di ruoli [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] (insieme al provider di appartenenza [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]) è una funzionalità grazie alla quale gli sviluppatori [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] sono in grado di creare siti Web che consentono agli utenti di creare un account in un sito e di acquisire ruoli a scopo di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="84a03-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider (in conjunction with the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider) is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="84a03-104">Con questa funzionalità qualsiasi utente può stabilire un account nel sito e accedere in modo esclusivo al sito e ai relativi servizi.</span><span class="sxs-lookup"><span data-stu-id="84a03-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="84a03-105">Si tratta di una funzionalità in contrasto con la protezione di Windows, in base alla quale è necessario che gli utenti dispongano di un account in un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="84a03-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="84a03-106">Qualsiasi utente che fornisca le credenziali (ovvero nome utente e password) può utilizzare il sito e i relativi servizi.</span><span class="sxs-lookup"><span data-stu-id="84a03-106">Instead, any user who supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="84a03-107">Per un'applicazione di esempio, vedere [Provider di appartenenze e ruoli](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="84a03-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="84a03-108">Per ulteriori informazioni sul [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] funzionalità del provider di appartenenza, vedere [procedura: utilizzare il Provider di appartenenze ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="84a03-108">For more information about the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
 <span data-ttu-id="84a03-109">La funzionalità del provider di ruoli utilizza un database SQL Server per archiviare informazioni utente.</span><span class="sxs-lookup"><span data-stu-id="84a03-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="84a03-110">Gli sviluppatori di Windows Communication Foundation (WCF) possono sfruttare queste funzionalità per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="84a03-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="84a03-111">Quando è integrato in un'applicazione WCF, gli utenti devono fornire una combinazione nome utente/password per l'applicazione client WCF.</span><span class="sxs-lookup"><span data-stu-id="84a03-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="84a03-112">Per abilitare WCF di utilizzare il database, è necessario creare un'istanza del <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> , impostare il relativo <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> proprietà da <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>e aggiungere l'istanza alla raccolta di comportamenti al <xref:System.ServiceModel.ServiceHost> che ospita il servizio.</span><span class="sxs-lookup"><span data-stu-id="84a03-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
### <a name="to-configure-the-role-provider"></a><span data-ttu-id="84a03-113">Per configurare il provider di ruoli</span><span class="sxs-lookup"><span data-stu-id="84a03-113">To configure the role provider</span></span>  
  
1.  <span data-ttu-id="84a03-114">Nel file Web. config, sotto il <`system.web`> elemento, aggiungere un <`roleManager`> elemento e impostare il relativo `enabled` attributo `true`.</span><span class="sxs-lookup"><span data-stu-id="84a03-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2.  <span data-ttu-id="84a03-115">Impostare l'attributo `defaultProvider` su `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="84a03-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3.  <span data-ttu-id="84a03-116">Come elemento figlio di <`roleManager`> elemento, aggiungere un <`providers`> elemento.</span><span class="sxs-lookup"><span data-stu-id="84a03-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4.  <span data-ttu-id="84a03-117">Come elemento figlio di <`providers`> elemento, aggiungere un <`add`> elemento con i seguenti attributi impostati su valori appropriati: `name`, `type`, `connectionStringName`, e `applicationName`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="84a03-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="84a03-118">Per configurare il servizio per l'utilizzo del provider di ruoli</span><span class="sxs-lookup"><span data-stu-id="84a03-118">To configure the service to use the role provider</span></span>  
  
1.  <span data-ttu-id="84a03-119">Nel file Web. config, aggiungere un [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="84a03-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="84a03-120">Aggiungere un [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento per il <`system.ServiceModel`> elemento.</span><span class="sxs-lookup"><span data-stu-id="84a03-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3.  <span data-ttu-id="84a03-121">Aggiungere un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) per il <`behaviors`> elemento.</span><span class="sxs-lookup"><span data-stu-id="84a03-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4.  <span data-ttu-id="84a03-122">Aggiungere un [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento e impostare il `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="84a03-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5.  <span data-ttu-id="84a03-123">Aggiungere un [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) per il <`behavior`> elemento.</span><span class="sxs-lookup"><span data-stu-id="84a03-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6.  <span data-ttu-id="84a03-124">Impostare l'attributo `principalPermissionMode` su `UseAspNetRoles`.</span><span class="sxs-lookup"><span data-stu-id="84a03-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7.  <span data-ttu-id="84a03-125">Impostare l'attributo `roleProviderName` su `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="84a03-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="84a03-126">Nell'esempio seguente viene illustrata una parte della configurazione.</span><span class="sxs-lookup"><span data-stu-id="84a03-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="84a03-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84a03-127">See Also</span></span>  
 [<span data-ttu-id="84a03-128">Provider di appartenenza e di ruoli</span><span class="sxs-lookup"><span data-stu-id="84a03-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 [<span data-ttu-id="84a03-129">Procedura: Usare provider di appartenenza ASP.NET</span><span class="sxs-lookup"><span data-stu-id="84a03-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)

---
title: '&lt;IdentityModel&gt;'
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: c7261d20ae2379ad33679cadecdef484f2afdecf
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075218"
---
# <a name="ltsystemidentitymodelservicesgt"></a><span data-ttu-id="d953a-102">&lt;IdentityModel&gt;</span><span class="sxs-lookup"><span data-stu-id="d953a-102">&lt;system.identityModel.services&gt;</span></span>
<span data-ttu-id="d953a-103">Sezione di configurazione per l'autenticazione usando il protocollo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="d953a-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
 <span data-ttu-id="d953a-104">\<IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="d953a-104">\<system.identityModel.services></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d953a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d953a-105">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d953a-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d953a-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d953a-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d953a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d953a-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="d953a-108">Attributes</span></span>  
 <span data-ttu-id="d953a-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="d953a-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d953a-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d953a-110">Child Elements</span></span>  
  
|<span data-ttu-id="d953a-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="d953a-111">Element</span></span>|<span data-ttu-id="d953a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d953a-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d953a-113">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="d953a-113">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="d953a-114">Contiene le impostazioni che consentono di configurare il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e il <xref:System.IdentityModel.Services.SessionAuthenticationModule> moduli HTTP (SAM).</span><span class="sxs-lookup"><span data-stu-id="d953a-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d953a-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d953a-115">Parent Elements</span></span>  
 <span data-ttu-id="d953a-116">nessuno</span><span class="sxs-lookup"><span data-stu-id="d953a-116">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d953a-117">Note</span><span class="sxs-lookup"><span data-stu-id="d953a-117">Remarks</span></span>  
 <span data-ttu-id="d953a-118">Aggiungere un `<system.identityModel.services>` sezione al file di configurazione dell'applicazione per fornire le impostazioni per il SAM e WSFAM.</span><span class="sxs-lookup"><span data-stu-id="d953a-118">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d953a-119">Quando si usa il <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o il <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo di accesso basato sulle attestazioni nel codice, il gestore di autorizzazione delle attestazioni (<xref:System.Security.Claims.ClaimsAuthorizationManager>) e i criteri utilizzati per prendere decisioni di autorizzazione vengono configurate mediante un `<identityConfiguration>` elemento che fa in modo implicito o esplicito da un `<federationConfiguration>` elemento in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d953a-119">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="d953a-120">Per altre informazioni, vedere la **osservazioni** sotto il [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d953a-120">For more information, see the **Remarks** under the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="d953a-121">Il `<system.identityModel.services>` sezione è rappresentata dal <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> classe.</span><span class="sxs-lookup"><span data-stu-id="d953a-121">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="d953a-122">La raccolta di figlio `<federationConfiguration>` rappresentato da configurati nella sezione elementi di <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> classe.</span><span class="sxs-lookup"><span data-stu-id="d953a-122">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d953a-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="d953a-123">Example</span></span>  
 <span data-ttu-id="d953a-124">Il codice XML seguente viene illustrato come aggiungere un `<system.identityModel.services>` sezione in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d953a-124">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="d953a-125">È innanzitutto necessario aggiungere le dichiarazioni della sezione sia per il `<system.identityModel.services>` sezione e `<system.identityModel>` sezioni.</span><span class="sxs-lookup"><span data-stu-id="d953a-125">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="d953a-126">(Quando si aggiunge un `<system.identityModel.services>` sezione, è necessario aggiungere anche una dichiarazione per il `<system.identityModel>` sezione per garantire che un valore predefinito `<identityConfiguration>` sezione possa essere creata dal runtime se necessario.) Dopo che sono state aggiunte le dichiarazioni di sezione, è possibile configurare le impostazioni di autenticazione federata sotto il `<system.identityModel.services>` elemento.</span><span class="sxs-lookup"><span data-stu-id="d953a-126">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true"   
        issuer="http://localhost:15839/wsFederationSTS/Issue"   
        realm="http://localhost:50969/" reply="http://localhost:50969/"   
        requireHttps="false"   
        signOutReply="http://localhost:50969/SignedOutPage.html"   
        signOutQueryString="Param1=value2&Param2=value2"   
        persistentCookiesOnPassiveRedirects="true" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
  
</configuration>  
```

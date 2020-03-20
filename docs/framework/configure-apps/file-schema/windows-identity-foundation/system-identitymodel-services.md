---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152504"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="47896-102">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="47896-102">\<system.identityModel.services></span></span>
<span data-ttu-id="47896-103">Sezione di configurazione per l'autenticazione tramite il protocollo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="47896-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
<span data-ttu-id="47896-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="47896-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="47896-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span><span class="sxs-lookup"><span data-stu-id="47896-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47896-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47896-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47896-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="47896-107">Attributes and Elements</span></span>  
 <span data-ttu-id="47896-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="47896-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47896-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="47896-109">Attributes</span></span>  
 <span data-ttu-id="47896-110">nessuno</span><span class="sxs-lookup"><span data-stu-id="47896-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="47896-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="47896-111">Child Elements</span></span>  
  
|<span data-ttu-id="47896-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="47896-112">Element</span></span>|<span data-ttu-id="47896-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47896-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47896-114">\<>di configurazione</span><span class="sxs-lookup"><span data-stu-id="47896-114">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="47896-115">Contiene le impostazioni <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> che configurano i <xref:System.IdentityModel.Services.SessionAuthenticationModule> moduli HTTP (WSFAM) e SAM.</span><span class="sxs-lookup"><span data-stu-id="47896-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47896-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="47896-116">Parent Elements</span></span>  
 <span data-ttu-id="47896-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="47896-117">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47896-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="47896-118">Remarks</span></span>  
 <span data-ttu-id="47896-119">Aggiungere `<system.identityModel.services>` una sezione al file di configurazione dell'applicazione per fornire le impostazioni per SAM e WSFAM.</span><span class="sxs-lookup"><span data-stu-id="47896-119">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="47896-120">Quando si <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> utilizza <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> la classe o per fornire il controllo di<xref:System.Security.Claims.ClaimsAuthorizationManager>accesso basato sulle attestazioni nel codice, `<identityConfiguration>` il gestore di autorizzazioni delle `<federationConfiguration>` attestazioni ( ) e i criteri utilizzati per prendere decisioni di autorizzazione vengono configurati tramite un elemento a cui viene fatto riferimento in modo implicito o esplicito da un elemento di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="47896-120">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="47896-121">Per altre informazioni, vedere le **osservazioni** nell'elemento [ \<federationConfiguration>.](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="47896-121">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="47896-122">La `<system.identityModel.services>` sezione è <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> rappresentata dalla classe .</span><span class="sxs-lookup"><span data-stu-id="47896-122">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="47896-123">La raccolta `<federationConfiguration>` di elementi figlio configurati nella <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> sezione è rappresentata dalla classe .</span><span class="sxs-lookup"><span data-stu-id="47896-123">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47896-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="47896-124">Example</span></span>  
 <span data-ttu-id="47896-125">Nel codice XML seguente `<system.identityModel.services>` viene illustrato come aggiungere una sezione a un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="47896-125">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="47896-126">È innanzitutto necessario aggiungere le `<system.identityModel.services>` dichiarazioni `<system.identityModel>` di sezione per la sezione e le sezioni.</span><span class="sxs-lookup"><span data-stu-id="47896-126">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="47896-127">Quando si aggiunge `<system.identityModel.services>` una sezione, è inoltre `<system.identityModel>` necessario aggiungere una `<identityConfiguration>` dichiarazione per la sezione per garantire che una sezione predefinita possa essere creata dal runtime, se necessario. Dopo aver aggiunto le dichiarazioni di sezione, è `<system.identityModel.services>` possibile configurare le impostazioni di autenticazione federata sotto l'elemento.</span><span class="sxs-lookup"><span data-stu-id="47896-127">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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

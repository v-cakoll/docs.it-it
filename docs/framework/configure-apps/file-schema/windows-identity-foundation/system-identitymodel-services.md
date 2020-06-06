---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152504"
---
# \<system.identityModel.services>
<span data-ttu-id="491ac-102">Sezione di configurazione per l'autenticazione tramite il protocollo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="491ac-102">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel.services>**  
  
## <a name="syntax"></a><span data-ttu-id="491ac-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="491ac-103">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="491ac-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="491ac-104">Attributes and Elements</span></span>  
 <span data-ttu-id="491ac-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="491ac-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="491ac-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="491ac-106">Attributes</span></span>  
 <span data-ttu-id="491ac-107">nessuno</span><span class="sxs-lookup"><span data-stu-id="491ac-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="491ac-108">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="491ac-108">Child Elements</span></span>  
  
|<span data-ttu-id="491ac-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="491ac-109">Element</span></span>|<span data-ttu-id="491ac-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="491ac-110">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="491ac-111">Contiene le impostazioni che configurano i <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> moduli HTTP (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam).</span><span class="sxs-lookup"><span data-stu-id="491ac-111">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="491ac-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="491ac-112">Parent Elements</span></span>  
 <span data-ttu-id="491ac-113">nessuno</span><span class="sxs-lookup"><span data-stu-id="491ac-113">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="491ac-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="491ac-114">Remarks</span></span>  
 <span data-ttu-id="491ac-115">Aggiungere una `<system.identityModel.services>` sezione al file di configurazione dell'applicazione per specificare le impostazioni per Sam e WSFAM.</span><span class="sxs-lookup"><span data-stu-id="491ac-115">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="491ac-116">Quando si usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo degli accessi in base alle attestazioni nel codice, il gestore delle autorizzazioni delle attestazioni ( <xref:System.Security.Claims.ClaimsAuthorizationManager> ) e i criteri usati per prendere decisioni di autorizzazione vengono configurati tramite un `<identityConfiguration>` elemento a cui viene fatto riferimento in modo implicito o esplicito da un `<federationConfiguration>` elemento in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="491ac-116">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="491ac-117">Per ulteriori informazioni, vedere la **sezione Osservazioni** sotto l' [\<federationConfiguration>](federationconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="491ac-117">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="491ac-118">La `<system.identityModel.services>` sezione è rappresentata dalla <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> classe.</span><span class="sxs-lookup"><span data-stu-id="491ac-118">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="491ac-119">La raccolta di `<federationConfiguration>` elementi figlio configurati nella sezione è rappresentata dalla <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> classe.</span><span class="sxs-lookup"><span data-stu-id="491ac-119">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="491ac-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="491ac-120">Example</span></span>  
 <span data-ttu-id="491ac-121">Nel codice XML seguente viene illustrato come aggiungere una `<system.identityModel.services>` sezione a un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="491ac-121">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="491ac-122">È necessario innanzitutto aggiungere dichiarazioni di sezione per la `<system.identityModel.services>` sezione e le `<system.identityModel>` sezioni.</span><span class="sxs-lookup"><span data-stu-id="491ac-122">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="491ac-123">Quando si aggiunge una `<system.identityModel.services>` sezione, è inoltre necessario aggiungere una dichiarazione per la `<system.identityModel>` sezione per assicurarsi che, `<identityConfiguration>` se necessario, una sezione predefinita possa essere creata dal runtime. Una volta aggiunte le dichiarazioni di sezione, è possibile configurare le impostazioni di autenticazione federata nell' `<system.identityModel.services>` elemento.</span><span class="sxs-lookup"><span data-stu-id="491ac-123">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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

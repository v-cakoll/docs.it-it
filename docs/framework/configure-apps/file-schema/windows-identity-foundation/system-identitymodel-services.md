---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: e9488c0681e1a5f0fe94112a36b65ec73bf9fd09
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251804"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="fdb66-102">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="fdb66-102">\<system.identityModel.services></span></span>
<span data-ttu-id="fdb66-103">Sezione di configurazione per l'autenticazione tramite il protocollo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="fdb66-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
<span data-ttu-id="fdb66-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fdb66-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fdb66-105">&nbsp;&nbsp; **\<System. identityModel. Services >**</span><span class="sxs-lookup"><span data-stu-id="fdb66-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdb66-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fdb66-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdb66-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fdb66-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fdb66-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fdb66-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdb66-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="fdb66-109">Attributes</span></span>  
 <span data-ttu-id="fdb66-110">Nessuna</span><span class="sxs-lookup"><span data-stu-id="fdb66-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fdb66-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fdb66-111">Child Elements</span></span>  
  
|<span data-ttu-id="fdb66-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="fdb66-112">Element</span></span>|<span data-ttu-id="fdb66-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="fdb66-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fdb66-114">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="fdb66-114">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="fdb66-115">Contiene le impostazioni che configurano i <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> moduli HTTP (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule> e (Sam).</span><span class="sxs-lookup"><span data-stu-id="fdb66-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fdb66-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fdb66-116">Parent Elements</span></span>  
 <span data-ttu-id="fdb66-117">Nessuna</span><span class="sxs-lookup"><span data-stu-id="fdb66-117">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdb66-118">Note</span><span class="sxs-lookup"><span data-stu-id="fdb66-118">Remarks</span></span>  
 <span data-ttu-id="fdb66-119">Aggiungere una `<system.identityModel.services>` sezione al file di configurazione dell'applicazione per specificare le impostazioni per Sam e WSFAM.</span><span class="sxs-lookup"><span data-stu-id="fdb66-119">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fdb66-120">Quando si usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo degli accessi in base alle attestazioni nel codice, il<xref:System.Security.Claims.ClaimsAuthorizationManager>gestore delle autorizzazioni delle attestazioni () e il criterio usato per prendere `<identityConfiguration>` decisioni di autorizzazione vengono configurati tramite un elemento a cui viene fatto riferimento in modo implicito o esplicito da un `<federationConfiguration>` elemento in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="fdb66-120">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="fdb66-121">Per ulteriori informazioni, vedere la **sezione Osservazioni** sotto l' [ \<elemento federationConfiguration >](federationconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="fdb66-121">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="fdb66-122">La `<system.identityModel.services>` sezione è rappresentata <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="fdb66-122">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="fdb66-123">La raccolta di elementi `<federationConfiguration>` figlio configurati nella sezione è rappresentata <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="fdb66-123">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdb66-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="fdb66-124">Example</span></span>  
 <span data-ttu-id="fdb66-125">Nel codice XML seguente viene illustrato come aggiungere `<system.identityModel.services>` una sezione a un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fdb66-125">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="fdb66-126">È necessario innanzitutto aggiungere dichiarazioni di sezione per la `<system.identityModel.services>` sezione e le `<system.identityModel>` sezioni.</span><span class="sxs-lookup"><span data-stu-id="fdb66-126">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="fdb66-127">Quando si aggiunge una `<system.identityModel.services>` sezione, è inoltre necessario aggiungere una dichiarazione per la `<system.identityModel>` sezione per assicurarsi che, se necessario `<identityConfiguration>` , una sezione predefinita possa essere creata dal runtime. Una volta aggiunte le dichiarazioni di sezione, è possibile configurare le impostazioni di autenticazione federata nell' `<system.identityModel.services>` elemento.</span><span class="sxs-lookup"><span data-stu-id="fdb66-127">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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

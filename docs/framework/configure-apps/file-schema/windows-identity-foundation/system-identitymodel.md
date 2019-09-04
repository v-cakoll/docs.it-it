---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: a54f5ce86aee1a5e831c0b10aa1471d4a82f40a5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251797"
---
# <a name="systemidentitymodel"></a><span data-ttu-id="5b938-102">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="5b938-102">\<system.identityModel></span></span>
<span data-ttu-id="5b938-103">Fornisce la configurazione per abilitare le opzioni di Windows Identity Foundation (WIF) nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="5b938-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
<span data-ttu-id="5b938-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5b938-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5b938-105">&nbsp;&nbsp; **\<System. identityModel >**</span><span class="sxs-lookup"><span data-stu-id="5b938-105">&nbsp;&nbsp;**\<system.identityModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b938-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b938-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b938-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5b938-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5b938-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5b938-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b938-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="5b938-109">Attributes</span></span>  
 <span data-ttu-id="5b938-110">Nessuna</span><span class="sxs-lookup"><span data-stu-id="5b938-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5b938-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5b938-111">Child Elements</span></span>  
  
|<span data-ttu-id="5b938-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b938-112">Element</span></span>|<span data-ttu-id="5b938-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="5b938-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b938-114">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5b938-114">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="5b938-115">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="5b938-115">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b938-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5b938-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5b938-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b938-117">Element</span></span>|<span data-ttu-id="5b938-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b938-118">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="5b938-119">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5b938-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b938-120">Note</span><span class="sxs-lookup"><span data-stu-id="5b938-120">Remarks</span></span>  
 <span data-ttu-id="5b938-121">Aggiungere una `<system.identityModel>` sezione al file di configurazione per configurare un servizio o un'applicazione per l'utilizzo di Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="5b938-121">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="5b938-122">L' `<system.identityModel>` elemento è rappresentato <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="5b938-122">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b938-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="5b938-123">Example</span></span>  
 <span data-ttu-id="5b938-124">Nell'esempio seguente viene illustrato come aggiungere una `<system.identityModel>` sezione a un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="5b938-124">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="5b938-125">È innanzitutto necessario aggiungere la sezione di configurazione e la dichiarazione dello `<configSections>` spazio dei nomi nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="5b938-125">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="5b938-126">È quindi possibile aggiungere l' `<system.IdentityModel>` elemento al file di configurazione per specificare una o più configurazioni di identità.</span><span class="sxs-lookup"><span data-stu-id="5b938-126">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b938-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b938-127">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>

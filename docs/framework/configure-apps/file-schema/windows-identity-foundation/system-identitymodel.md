---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: 2f0040fb7084b9d53adbd1a114f1cfc62d58e5a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110006"
---
# <a name="systemidentitymodel"></a><span data-ttu-id="04683-102">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="04683-102">\<system.identityModel></span></span>
<span data-ttu-id="04683-103">Fornisce la configurazione per l'attivazione di opzioni di Windows Identity Foundation (WIF) nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="04683-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
 <span data-ttu-id="04683-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="04683-104">\<system.identityModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04683-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04683-105">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04683-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="04683-106">Attributes and Elements</span></span>  
 <span data-ttu-id="04683-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="04683-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04683-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="04683-108">Attributes</span></span>  
 <span data-ttu-id="04683-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="04683-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="04683-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="04683-110">Child Elements</span></span>  
  
|<span data-ttu-id="04683-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="04683-111">Element</span></span>|<span data-ttu-id="04683-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04683-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04683-113">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="04683-113">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="04683-114">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="04683-114">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04683-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="04683-115">Parent Elements</span></span>  
  
|<span data-ttu-id="04683-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="04683-116">Element</span></span>|<span data-ttu-id="04683-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04683-117">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="04683-118">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="04683-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04683-119">Note</span><span class="sxs-lookup"><span data-stu-id="04683-119">Remarks</span></span>  
 <span data-ttu-id="04683-120">Aggiungere un `<system.identityModel>` sezione al file di configurazione per configurare un servizio o applicazione per l'uso di Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="04683-120">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="04683-121">Il `<system.identityModel>` elemento è rappresentato dal <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> classe.</span><span class="sxs-lookup"><span data-stu-id="04683-121">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04683-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="04683-122">Example</span></span>  
 <span data-ttu-id="04683-123">Nell'esempio seguente viene illustrato come aggiungere un `<system.identityModel>` sezione in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="04683-123">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="04683-124">È innanzitutto necessario aggiungere la dichiarazione di sezione e dello spazio dei nomi di configurazione sotto il `<configSections>` elemento.</span><span class="sxs-lookup"><span data-stu-id="04683-124">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="04683-125">Sarà quindi possibile aggiungere il `<system.IdentityModel>` elemento nel file di configurazione per specificare uno o più configurazioni di identità.</span><span class="sxs-lookup"><span data-stu-id="04683-125">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="04683-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04683-126">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>

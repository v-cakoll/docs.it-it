---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 3f3d79d3567c1714a79423b7767ce3f454b9d52d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152788"
---
# <a name="certificatevalidator"></a><span data-ttu-id="a62e5-101">\<> certificateValidator</span><span class="sxs-lookup"><span data-stu-id="a62e5-101">\<certificateValidator></span></span>
<span data-ttu-id="a62e5-102">Specifica un tipo personalizzato per la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="a62e5-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="a62e5-103">Questo tipo viene utilizzato `certificateValidationMode` solo se l'attributo dell'elemento [ \<certificateValidation>](certificatevalidation.md) è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="a62e5-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="a62e5-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a62e5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a62e5-105">&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="a62e5-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="a62e5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="a62e5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="a62e5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateConvalida>**](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="a62e5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="a62e5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>certificateValidator**</span><span class="sxs-lookup"><span data-stu-id="a62e5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a62e5-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a62e5-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a62e5-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a62e5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a62e5-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a62e5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a62e5-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="a62e5-112">Attributes</span></span>  
  
|<span data-ttu-id="a62e5-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="a62e5-113">Attribute</span></span>|<span data-ttu-id="a62e5-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a62e5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a62e5-115">type</span><span class="sxs-lookup"><span data-stu-id="a62e5-115">type</span></span>|<span data-ttu-id="a62e5-116">Specifica un tipo personalizzato che <xref:System.IdentityModel.Selectors.X509CertificateValidator> deriva dalla classe.</span><span class="sxs-lookup"><span data-stu-id="a62e5-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="a62e5-117">Impostare `certificateValidationMode` l'attributo dell'elemento [ \<certificateValidation>](certificatevalidation.md) su "Custom" per utilizzare questo tipo.</span><span class="sxs-lookup"><span data-stu-id="a62e5-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="a62e5-118">Per ulteriori informazioni su `type` come specificare l'attributo, vedere Riferimenti ai tipi [personalizzati](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="a62e5-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="a62e5-119">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a62e5-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a62e5-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a62e5-120">Child Elements</span></span>  
 <span data-ttu-id="a62e5-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="a62e5-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a62e5-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a62e5-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a62e5-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="a62e5-123">Element</span></span>|<span data-ttu-id="a62e5-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a62e5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a62e5-125">\<certificateConvalida></span><span class="sxs-lookup"><span data-stu-id="a62e5-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="a62e5-126">Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="a62e5-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a62e5-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="a62e5-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```

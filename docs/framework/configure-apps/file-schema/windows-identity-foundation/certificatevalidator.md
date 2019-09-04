---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 30f81dd5948a7d366c1116cffd347c85a396f5ae
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252118"
---
# <a name="certificatevalidator"></a><span data-ttu-id="4cdad-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="4cdad-101">\<certificateValidator></span></span>
<span data-ttu-id="4cdad-102">Specifica un tipo personalizzato per la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="4cdad-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="4cdad-103">Questo tipo viene utilizzato solo se l' `certificateValidationMode` attributo [ \<dell'elemento > CertificateValidation](certificatevalidation.md) è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="4cdad-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="4cdad-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4cdad-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4cdad-105">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="4cdad-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="4cdad-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="4cdad-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="4cdad-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> certificateValidation**](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="4cdad-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="4cdad-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> certificateValidator**</span><span class="sxs-lookup"><span data-stu-id="4cdad-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cdad-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4cdad-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4cdad-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4cdad-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4cdad-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4cdad-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4cdad-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4cdad-112">Attributes</span></span>  
  
|<span data-ttu-id="4cdad-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="4cdad-113">Attribute</span></span>|<span data-ttu-id="4cdad-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4cdad-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4cdad-115">type</span><span class="sxs-lookup"><span data-stu-id="4cdad-115">type</span></span>|<span data-ttu-id="4cdad-116">Specifica un tipo personalizzato che deriva dalla <xref:System.IdentityModel.Selectors.X509CertificateValidator> classe.</span><span class="sxs-lookup"><span data-stu-id="4cdad-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="4cdad-117">Impostare l' `certificateValidationMode` attributo [ \<dell'elemento > CertificateValidation](certificatevalidation.md) su "Custom" per usare questo tipo.</span><span class="sxs-lookup"><span data-stu-id="4cdad-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="4cdad-118">Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="4cdad-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="4cdad-119">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4cdad-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4cdad-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4cdad-120">Child Elements</span></span>  
 <span data-ttu-id="4cdad-121">Nessuna</span><span class="sxs-lookup"><span data-stu-id="4cdad-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4cdad-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4cdad-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4cdad-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="4cdad-123">Element</span></span>|<span data-ttu-id="4cdad-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4cdad-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4cdad-125">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="4cdad-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="4cdad-126">Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="4cdad-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4cdad-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="4cdad-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```

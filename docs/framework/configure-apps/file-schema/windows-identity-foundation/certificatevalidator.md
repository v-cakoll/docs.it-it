---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: c25f183679f41f51ffee4f482bfe7a64763647d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941908"
---
# <a name="certificatevalidator"></a><span data-ttu-id="dd092-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="dd092-101">\<certificateValidator></span></span>
<span data-ttu-id="dd092-102">Specifica un tipo personalizzato per la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="dd092-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="dd092-103">Questo tipo viene utilizzato solo se l' `certificateValidationMode` attributo [ \<dell'elemento > CertificateValidation](certificatevalidation.md) è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="dd092-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="dd092-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="dd092-104">\<system.identityModel></span></span>  
<span data-ttu-id="dd092-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="dd092-105">\<identityConfiguration></span></span>  
<span data-ttu-id="dd092-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="dd092-106">\<certificateValidation></span></span>  
<span data-ttu-id="dd092-107">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="dd092-107">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd092-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd092-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd092-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dd092-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dd092-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dd092-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd092-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="dd092-111">Attributes</span></span>  
  
|<span data-ttu-id="dd092-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="dd092-112">Attribute</span></span>|<span data-ttu-id="dd092-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="dd092-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd092-114">type</span><span class="sxs-lookup"><span data-stu-id="dd092-114">type</span></span>|<span data-ttu-id="dd092-115">Specifica un tipo personalizzato che deriva dalla <xref:System.IdentityModel.Selectors.X509CertificateValidator> classe.</span><span class="sxs-lookup"><span data-stu-id="dd092-115">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="dd092-116">Impostare l' `certificateValidationMode` attributo [ \<dell'elemento > CertificateValidation](certificatevalidation.md) su "Custom" per usare questo tipo.</span><span class="sxs-lookup"><span data-stu-id="dd092-116">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="dd092-117">Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="dd092-117">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="dd092-118">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd092-118">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd092-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dd092-119">Child Elements</span></span>  
 <span data-ttu-id="dd092-120">Nessuna</span><span class="sxs-lookup"><span data-stu-id="dd092-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd092-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dd092-121">Parent Elements</span></span>  
  
|<span data-ttu-id="dd092-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd092-122">Element</span></span>|<span data-ttu-id="dd092-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd092-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd092-124">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="dd092-124">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="dd092-125">Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="dd092-125">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dd092-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd092-126">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```

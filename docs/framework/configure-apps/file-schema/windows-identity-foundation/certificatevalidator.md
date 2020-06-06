---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 3f3d79d3567c1714a79423b7767ce3f454b9d52d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152788"
---
# \<certificateValidator>
<span data-ttu-id="ddfbf-101">Specifica un tipo personalizzato per la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-101">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="ddfbf-102">Questo tipo viene utilizzato solo se l' `certificateValidationMode` attributo dell' [\<certificateValidation>](certificatevalidation.md) elemento è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="ddfbf-102">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**  
  
## <a name="syntax"></a><span data-ttu-id="ddfbf-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ddfbf-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddfbf-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ddfbf-104">Attributes and Elements</span></span>  
 <span data-ttu-id="ddfbf-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddfbf-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="ddfbf-106">Attributes</span></span>  
  
|<span data-ttu-id="ddfbf-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="ddfbf-107">Attribute</span></span>|<span data-ttu-id="ddfbf-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddfbf-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ddfbf-109">type</span><span class="sxs-lookup"><span data-stu-id="ddfbf-109">type</span></span>|<span data-ttu-id="ddfbf-110">Specifica un tipo personalizzato che deriva dalla <xref:System.IdentityModel.Selectors.X509CertificateValidator> classe.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-110">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="ddfbf-111">Impostare l' `certificateValidationMode` attributo dell' [\<certificateValidation>](certificatevalidation.md) elemento su "Custom" per usare questo tipo.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-111">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="ddfbf-112">Per ulteriori informazioni su come specificare l' `type` attributo, vedere [riferimenti ai tipi personalizzati](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="ddfbf-112">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="ddfbf-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ddfbf-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ddfbf-114">Child Elements</span></span>  
 <span data-ttu-id="ddfbf-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="ddfbf-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ddfbf-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ddfbf-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ddfbf-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ddfbf-117">Element</span></span>|<span data-ttu-id="ddfbf-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddfbf-118">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="ddfbf-119">Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-119">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ddfbf-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="ddfbf-120">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```

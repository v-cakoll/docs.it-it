---
title: Enumerazione CorGenericParamAttr
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e40613d790baed5bd89bee1e1f5ca57043bfe76a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="07692-102">Enumerazione CorGenericParamAttr</span><span class="sxs-lookup"><span data-stu-id="07692-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="07692-103">Contiene valori che descrivono il <xref:System.Type> parametri per i tipi generici, come utilizzati nelle chiamate a [IMetaDataEmit2:: DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="07692-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07692-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07692-104">Syntax</span></span>  
  
```  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,   
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,   
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="07692-105">Membri</span><span class="sxs-lookup"><span data-stu-id="07692-105">Members</span></span>  
  
|<span data-ttu-id="07692-106">Membro</span><span class="sxs-lookup"><span data-stu-id="07692-106">Member</span></span>|<span data-ttu-id="07692-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07692-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="07692-108">La varianza di parametro si applica solo a parametri generici per interfacce e delegati.</span><span class="sxs-lookup"><span data-stu-id="07692-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="07692-109">Indica l'assenza di varianza.</span><span class="sxs-lookup"><span data-stu-id="07692-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="07692-110">Indica la covarianza.</span><span class="sxs-lookup"><span data-stu-id="07692-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="07692-111">Indica la controvarianza.</span><span class="sxs-lookup"><span data-stu-id="07692-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="07692-112">I vincoli speciali possono applicare a qualsiasi <xref:System.Type> parametro.</span><span class="sxs-lookup"><span data-stu-id="07692-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="07692-113">Indica che nessun vincolo si applica al <xref:System.Type> parametro.</span><span class="sxs-lookup"><span data-stu-id="07692-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="07692-114">Indica che il <xref:System.Type> parametro deve essere un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="07692-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="07692-115">Indica che il <xref:System.Type> parametro deve essere un tipo di valore non può essere un valore null.</span><span class="sxs-lookup"><span data-stu-id="07692-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="07692-116">Indica che il <xref:System.Type> parametro deve avere un costruttore pubblico predefinito che non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="07692-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07692-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="07692-117">Requirements</span></span>  
 <span data-ttu-id="07692-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07692-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07692-119">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="07692-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="07692-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07692-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07692-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07692-121">See Also</span></span>  
 [<span data-ttu-id="07692-122">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="07692-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

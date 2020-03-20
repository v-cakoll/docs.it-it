---
title: Enumerazione CorGenericParamAttr
ms.date: 03/30/2017
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
ms.openlocfilehash: bf0008ce9429671f0c156df4256bed0b2aaee184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176175"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="7c4fd-102">Enumerazione CorGenericParamAttr</span><span class="sxs-lookup"><span data-stu-id="7c4fd-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="7c4fd-103">Contiene valori che <xref:System.Type> descrivono i parametri per i tipi generici, utilizzati nelle chiamate a [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="7c4fd-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c4fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c4fd-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="7c4fd-105">Members</span><span class="sxs-lookup"><span data-stu-id="7c4fd-105">Members</span></span>  
  
|<span data-ttu-id="7c4fd-106">Membro</span><span class="sxs-lookup"><span data-stu-id="7c4fd-106">Member</span></span>|<span data-ttu-id="7c4fd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c4fd-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="7c4fd-108">La varianza dei parametri si applica solo ai parametri generici per interfacce e delegati.</span><span class="sxs-lookup"><span data-stu-id="7c4fd-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="7c4fd-109">Indica l'assenza di varianza.</span><span class="sxs-lookup"><span data-stu-id="7c4fd-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="7c4fd-110">Indica la covarianza.</span><span class="sxs-lookup"><span data-stu-id="7c4fd-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="7c4fd-111">Indica la controvarianza.</span><span class="sxs-lookup"><span data-stu-id="7c4fd-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="7c4fd-112">È possibile applicare <xref:System.Type> vincoli speciali a qualsiasi parametro.</span><span class="sxs-lookup"><span data-stu-id="7c4fd-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="7c4fd-113">Indica che nessun vincolo <xref:System.Type> viene applicato al parametro.</span><span class="sxs-lookup"><span data-stu-id="7c4fd-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="7c4fd-114">Indica che <xref:System.Type> il parametro deve essere un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="7c4fd-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="7c4fd-115">Indica che <xref:System.Type> il parametro deve essere un tipo di valore che non può essere un valore null.</span><span class="sxs-lookup"><span data-stu-id="7c4fd-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="7c4fd-116">Indica che <xref:System.Type> il parametro deve avere un costruttore pubblico predefinito che non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="7c4fd-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c4fd-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c4fd-117">Requirements</span></span>  
 <span data-ttu-id="7c4fd-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c4fd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c4fd-119">**Intestazione:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7c4fd-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7c4fd-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c4fd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c4fd-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c4fd-121">See also</span></span>

- [<span data-ttu-id="7c4fd-122">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="7c4fd-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

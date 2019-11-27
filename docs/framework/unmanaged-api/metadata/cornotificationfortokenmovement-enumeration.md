---
title: Enumerazione CorNotificationForTokenMovement
ms.date: 03/30/2017
api_name:
- CorNotificationForTokenMovement
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNotificationForTokenMovement
helpviewer_keywords:
- CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type:
- apiref
ms.openlocfilehash: 411fad0accb59431f776c5bd66e8bd3027ddd907
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450150"
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="3a914-102">Enumerazione CorNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="3a914-102">CorNotificationForTokenMovement Enumeration</span></span>
<span data-ttu-id="3a914-103">Specifica le notifiche che verranno inviate al client dell'API dei metadati quando si verifica un mapping del token.</span><span class="sxs-lookup"><span data-stu-id="3a914-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a914-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a914-104">Syntax</span></span>  
  
```cpp  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a><span data-ttu-id="3a914-105">Members</span><span class="sxs-lookup"><span data-stu-id="3a914-105">Members</span></span>  
  
|<span data-ttu-id="3a914-106">Membro</span><span class="sxs-lookup"><span data-stu-id="3a914-106">Member</span></span>|<span data-ttu-id="3a914-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a914-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="3a914-108">Notifica quando `mdTypeRef`, `mdMethodDef`, `mdMemberRef`o `mdFieldDef` i token vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="3a914-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="3a914-109">Notifica quando un token viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="3a914-110">Non notificare quando i token vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="3a914-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="3a914-111">Notifica quando un token di `mdMethodDef` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="3a914-112">Notifica quando un token di `mdMemberRef` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="3a914-113">Notifica quando un token di `mdFieldDef` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="3a914-114">Notifica quando un token di `mdTypeRef` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="3a914-115">Notifica quando un token di `mdTypeDef` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="3a914-116">Notifica quando un token di `mdParamDef` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="3a914-117">Notifica quando un token di `mdInterfaceImpl` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="3a914-118">Notifica quando un token di `mdProperty` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="3a914-119">Notifica quando un token di `mdEvent` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="3a914-120">Notifica quando un token di `mdSignature` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="3a914-121">Notifica quando un token di `mdTypeSpec` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="3a914-122">Notifica quando un token di `mdCustomAttribute` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="3a914-123">Notifica quando un token di `mdSecurityValue` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="3a914-124">Notifica quando un token di `mdPermission` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="3a914-125">Notifica quando un token di `mdModuleRef` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="3a914-126">Notifica quando un token di `mdNameSpace` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="3a914-127">Notifica quando un token di `mdAssemblyRef` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="3a914-128">Notifica quando un token di `mdFile` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="3a914-129">Notifica quando un token di `mdExportedType` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="3a914-130">Notifica quando un token di `mdManifestResource` viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3a914-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a914-131">Note</span><span class="sxs-lookup"><span data-stu-id="3a914-131">Remarks</span></span>  
 <span data-ttu-id="3a914-132">È possibile che venga nuovamente eseguito il mapping di un token (ovvero lo spostamento) durante un'operazione di merge dei metadati.</span><span class="sxs-lookup"><span data-stu-id="3a914-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a914-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a914-133">Requirements</span></span>  
 <span data-ttu-id="3a914-134">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a914-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a914-135">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="3a914-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3a914-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a914-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a914-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a914-137">See also</span></span>

- [<span data-ttu-id="3a914-138">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="3a914-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15c5e8b34f2748868611bd7dc47ef73c491b1338
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189430"
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="1b7b6-102">Enumerazione CorNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="1b7b6-102">CorNotificationForTokenMovement Enumeration</span></span>
<span data-ttu-id="1b7b6-103">Specifica le notifiche che verranno inviate al client API dei metadati quando si verifica una modifica del mapping dei token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b7b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b7b6-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="1b7b6-105">Membri</span><span class="sxs-lookup"><span data-stu-id="1b7b6-105">Members</span></span>  
  
|<span data-ttu-id="1b7b6-106">Member</span><span class="sxs-lookup"><span data-stu-id="1b7b6-106">Member</span></span>|<span data-ttu-id="1b7b6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b7b6-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="1b7b6-108">Invia una notifica quando `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, o `mdFieldDef` Sposta i token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="1b7b6-109">Inviare una notifica quando si sposta tutti i token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="1b7b6-110">Non notificano quando spostano i token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="1b7b6-111">Invia una notifica quando un `mdMethodDef` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="1b7b6-112">Invia una notifica quando un `mdMemberRef` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="1b7b6-113">Invia una notifica quando un `mdFieldDef` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="1b7b6-114">Invia una notifica quando un `mdTypeRef` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="1b7b6-115">Invia una notifica quando un `mdTypeDef` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="1b7b6-116">Invia una notifica quando un `mdParamDef` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="1b7b6-117">Invia una notifica quando un `mdInterfaceImpl` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="1b7b6-118">Invia una notifica quando un `mdProperty` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="1b7b6-119">Invia una notifica quando un `mdEvent` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="1b7b6-120">Invia una notifica quando un `mdSignature` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="1b7b6-121">Invia una notifica quando un `mdTypeSpec` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="1b7b6-122">Invia una notifica quando un `mdCustomAttribute` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="1b7b6-123">Invia una notifica quando un `mdSecurityValue` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="1b7b6-124">Invia una notifica quando un `mdPermission` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="1b7b6-125">Invia una notifica quando un `mdModuleRef` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="1b7b6-126">Invia una notifica quando un `mdNameSpace` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="1b7b6-127">Invia una notifica quando un `mdAssemblyRef` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="1b7b6-128">Invia una notifica quando un `mdFile` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="1b7b6-129">Invia una notifica quando un `mdExportedType` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="1b7b6-130">Invia una notifica quando un `mdManifestResource` passa il token.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b7b6-131">Note</span><span class="sxs-lookup"><span data-stu-id="1b7b6-131">Remarks</span></span>  
 <span data-ttu-id="1b7b6-132">Un token può essere mappato nuovamente (che è stato spostato) durante un'unione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="1b7b6-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b7b6-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b7b6-133">Requirements</span></span>  
 <span data-ttu-id="1b7b6-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b7b6-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b7b6-135">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="1b7b6-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1b7b6-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b7b6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b7b6-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b7b6-137">See also</span></span>

- [<span data-ttu-id="1b7b6-138">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="1b7b6-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

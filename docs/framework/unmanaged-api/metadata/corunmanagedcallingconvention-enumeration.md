---
title: Enumerazione CorUnmanagedCallingConvention
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorUnmanagedCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorUnmanagedCallingConvention
helpviewer_keywords: CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f66cb036de8450d4c1b3431b92487260956d47f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="4a784-102">Enumerazione CorUnmanagedCallingConvention</span><span class="sxs-lookup"><span data-stu-id="4a784-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="4a784-103">Specifica le convenzioni di chiamata per codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="4a784-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a784-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a784-104">Syntax</span></span>  
  
```  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="4a784-105">Membri</span><span class="sxs-lookup"><span data-stu-id="4a784-105">Members</span></span>  
  
|<span data-ttu-id="4a784-106">Membro</span><span class="sxs-lookup"><span data-stu-id="4a784-106">Member</span></span>|<span data-ttu-id="4a784-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a784-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="4a784-108">La convenzione di chiamata del linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="4a784-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="4a784-109">La convenzione di chiamata standard.</span><span class="sxs-lookup"><span data-stu-id="4a784-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="4a784-110">"This" convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a784-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="4a784-111">La convenzione di chiamata "veloce".</span><span class="sxs-lookup"><span data-stu-id="4a784-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="4a784-112">Non usato.</span><span class="sxs-lookup"><span data-stu-id="4a784-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="4a784-113">Non usato.</span><span class="sxs-lookup"><span data-stu-id="4a784-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="4a784-114">Non usato.</span><span class="sxs-lookup"><span data-stu-id="4a784-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="4a784-115">Non usato.</span><span class="sxs-lookup"><span data-stu-id="4a784-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a784-116">Note</span><span class="sxs-lookup"><span data-stu-id="4a784-116">Remarks</span></span>  
 <span data-ttu-id="4a784-117">Common Language Runtime non supporta la convenzione di chiamata "veloce" in .NET Framework versione 1.0.</span><span class="sxs-lookup"><span data-stu-id="4a784-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a784-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a784-118">Requirements</span></span>  
 <span data-ttu-id="4a784-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a784-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a784-120">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="4a784-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4a784-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a784-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a784-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a784-122">See Also</span></span>  
 [<span data-ttu-id="4a784-123">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="4a784-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

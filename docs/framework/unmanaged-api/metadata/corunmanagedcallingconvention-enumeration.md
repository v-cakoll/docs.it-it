---
title: Enumerazione CorUnmanagedCallingConvention
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
ms.openlocfilehash: 58d30e71929d314ee36adb9f83270858ff8a161b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442446"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="4ac44-102">Enumerazione CorUnmanagedCallingConvention</span><span class="sxs-lookup"><span data-stu-id="4ac44-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="4ac44-103">Specifica le convenzioni di chiamata per il codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="4ac44-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ac44-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ac44-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="4ac44-105">Membri</span><span class="sxs-lookup"><span data-stu-id="4ac44-105">Members</span></span>  
  
|<span data-ttu-id="4ac44-106">Membro</span><span class="sxs-lookup"><span data-stu-id="4ac44-106">Member</span></span>|<span data-ttu-id="4ac44-107">description</span><span class="sxs-lookup"><span data-stu-id="4ac44-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="4ac44-108">Convenzione di chiamata del linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="4ac44-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="4ac44-109">Convenzione di chiamata standard.</span><span class="sxs-lookup"><span data-stu-id="4ac44-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="4ac44-110">Convenzione di chiamata "This".</span><span class="sxs-lookup"><span data-stu-id="4ac44-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="4ac44-111">Convenzione di chiamata "Fast".</span><span class="sxs-lookup"><span data-stu-id="4ac44-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="4ac44-112">Non usato.</span><span class="sxs-lookup"><span data-stu-id="4ac44-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="4ac44-113">Non usato.</span><span class="sxs-lookup"><span data-stu-id="4ac44-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="4ac44-114">Non usato.</span><span class="sxs-lookup"><span data-stu-id="4ac44-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="4ac44-115">Non usato.</span><span class="sxs-lookup"><span data-stu-id="4ac44-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ac44-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4ac44-116">Remarks</span></span>  
 <span data-ttu-id="4ac44-117">CLR non supporta la convenzione di chiamata "Fast" nella versione .NET Framework 1,0.</span><span class="sxs-lookup"><span data-stu-id="4ac44-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ac44-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4ac44-118">Requirements</span></span>  
 <span data-ttu-id="4ac44-119">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ac44-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ac44-120">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="4ac44-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4ac44-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ac44-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ac44-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ac44-122">See also</span></span>

- [<span data-ttu-id="4ac44-123">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="4ac44-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

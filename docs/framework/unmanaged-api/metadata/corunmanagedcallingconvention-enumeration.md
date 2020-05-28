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
ms.openlocfilehash: b4c521489f38360d45c2cf8ff3780e057299f0b4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008950"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="e11ff-102">Enumerazione CorUnmanagedCallingConvention</span><span class="sxs-lookup"><span data-stu-id="e11ff-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="e11ff-103">Specifica le convenzioni di chiamata per il codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="e11ff-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e11ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e11ff-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e11ff-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e11ff-105">Members</span></span>  
  
|<span data-ttu-id="e11ff-106">Membro</span><span class="sxs-lookup"><span data-stu-id="e11ff-106">Member</span></span>|<span data-ttu-id="e11ff-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e11ff-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="e11ff-108">Convenzione di chiamata del linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="e11ff-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="e11ff-109">Convenzione di chiamata standard.</span><span class="sxs-lookup"><span data-stu-id="e11ff-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="e11ff-110">Convenzione di chiamata "This".</span><span class="sxs-lookup"><span data-stu-id="e11ff-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="e11ff-111">Convenzione di chiamata "Fast".</span><span class="sxs-lookup"><span data-stu-id="e11ff-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="e11ff-112">Non usato.</span><span class="sxs-lookup"><span data-stu-id="e11ff-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="e11ff-113">Non usato.</span><span class="sxs-lookup"><span data-stu-id="e11ff-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="e11ff-114">Non usato.</span><span class="sxs-lookup"><span data-stu-id="e11ff-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="e11ff-115">Non usato.</span><span class="sxs-lookup"><span data-stu-id="e11ff-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e11ff-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="e11ff-116">Remarks</span></span>  
 <span data-ttu-id="e11ff-117">CLR non supporta la convenzione di chiamata "Fast" nella versione .NET Framework 1,0.</span><span class="sxs-lookup"><span data-stu-id="e11ff-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e11ff-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e11ff-118">Requirements</span></span>  
 <span data-ttu-id="e11ff-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e11ff-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e11ff-120">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="e11ff-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e11ff-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e11ff-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e11ff-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e11ff-122">See also</span></span>

- [<span data-ttu-id="e11ff-123">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="e11ff-123">Metadata Enumerations</span></span>](metadata-enumerations.md)

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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff308a81282a1cc14c35583daf9cbb057149e556
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178451"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="82779-102">Enumerazione CorUnmanagedCallingConvention</span><span class="sxs-lookup"><span data-stu-id="82779-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="82779-103">Specifica le convenzioni di chiamata per codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="82779-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82779-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82779-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="82779-105">Membri</span><span class="sxs-lookup"><span data-stu-id="82779-105">Members</span></span>  
  
|<span data-ttu-id="82779-106">Member</span><span class="sxs-lookup"><span data-stu-id="82779-106">Member</span></span>|<span data-ttu-id="82779-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82779-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="82779-108">La convenzione di chiamata del linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="82779-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="82779-109">La convenzione di chiamata standard.</span><span class="sxs-lookup"><span data-stu-id="82779-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="82779-110">"This" convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="82779-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="82779-111">La convenzione di chiamata "veloce".</span><span class="sxs-lookup"><span data-stu-id="82779-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="82779-112">Non usato.</span><span class="sxs-lookup"><span data-stu-id="82779-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="82779-113">Non usato.</span><span class="sxs-lookup"><span data-stu-id="82779-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="82779-114">Non usato.</span><span class="sxs-lookup"><span data-stu-id="82779-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="82779-115">Non usato.</span><span class="sxs-lookup"><span data-stu-id="82779-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82779-116">Note</span><span class="sxs-lookup"><span data-stu-id="82779-116">Remarks</span></span>  
 <span data-ttu-id="82779-117">CLR non supporta la convenzione di chiamata "veloce" in .NET Framework versione 1.0.</span><span class="sxs-lookup"><span data-stu-id="82779-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82779-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82779-118">Requirements</span></span>  
 <span data-ttu-id="82779-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82779-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82779-120">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="82779-120">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="82779-121">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="82779-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="82779-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82779-122">See also</span></span>

- [<span data-ttu-id="82779-123">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="82779-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

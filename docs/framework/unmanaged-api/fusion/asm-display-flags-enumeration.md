---
title: Enumerazione ASM_DISPLAY_FLAGS
ms.date: 03/30/2017
api_name:
- ASM_DISPLAY_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_DISPLAY_FLAGS
helpviewer_keywords:
- ASM_DISPLAY_FLAGS enumeration [.NET Framework fusion]
ms.assetid: dbade6c9-9d26-4a79-9fd2-46108edd12d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8befdb454a564ec834532653dd44cf230fa43d79
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795212"
---
# <a name="asm_display_flags-enumeration"></a><span data-ttu-id="58eed-102">Enumerazione ASM_DISPLAY_FLAGS</span><span class="sxs-lookup"><span data-stu-id="58eed-102">ASM_DISPLAY_FLAGS Enumeration</span></span>
<span data-ttu-id="58eed-103">Indica la versione, la compilazione, le impostazioni cultura, la firma e così via dell'assembly il cui nome visualizzato verrà recuperato dal metodo [IAssemblyName:: GetDisplayName](iassemblyname-getdisplayname-method.md) .</span><span class="sxs-lookup"><span data-stu-id="58eed-103">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](iassemblyname-getdisplayname-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58eed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58eed-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    ASM_DISPLAYF_VERSION                 = 0x01,  
    ASM_DISPLAYF_CULTURE                 = 0x02,  
    ASM_DISPLAYF_PUBLIC_KEY_TOKEN        = 0x04,  
    ASM_DISPLAYF_PUBLIC_KEY              = 0x08,  
    ASM_DISPLAYF_CUSTOM                  = 0x10,  
    ASM_DISPLAYF_PROCESSORARCHITECTURE   = 0x20,  
    ASM_DISPLAYF_LANGUAGEID              = 0x40,  
    ASM_DISPLAYF_RETARGET                = 0x80,  
    ASM_DISPLAYF_CONFIG_MASK             = 0x100,  
    ASM_DISPLAYF_MVID                    = 0x200,  
    ASM_DISPLAYF_FULL                    =   
                      ASM_DISPLAYF_VERSION           |   
                      ASM_DISPLAYF_CULTURE           |   
                      ASM_DISPLAYF_PUBLIC_KEY_TOKEN  |   
                      ASM_DISPLAYF_RETARGET          |   
                      ASM_DISPLAYF_PROCESSORARCHITECTURE  
  
} ASM_DISPLAY_FLAGS;  
```  
  
## <a name="remarks"></a><span data-ttu-id="58eed-105">Note</span><span class="sxs-lookup"><span data-stu-id="58eed-105">Remarks</span></span>  
 <span data-ttu-id="58eed-106">`ASM_DISPLAYF_FULL`riflette tutte le modifiche apportate alla versione dell'oggetto [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="58eed-106">`ASM_DISPLAYF_FULL` reflects any changes made to the version of the [IAssemblyName](iassemblyname-interface.md) object.</span></span> <span data-ttu-id="58eed-107">Non presupporre che il valore restituito non sia modificabile.</span><span class="sxs-lookup"><span data-stu-id="58eed-107">Do not assume that the returned value is immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58eed-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58eed-108">Requirements</span></span>  
 <span data-ttu-id="58eed-109">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58eed-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58eed-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="58eed-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="58eed-111">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="58eed-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58eed-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58eed-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58eed-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58eed-113">See also</span></span>

- [<span data-ttu-id="58eed-114">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="58eed-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="58eed-115">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="58eed-115">Fusion Enumerations</span></span>](fusion-enumerations.md)

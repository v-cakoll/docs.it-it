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
ms.openlocfilehash: 70b40095ffcfea37414b7de2a678ad8555423b12
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778552"
---
# <a name="asmdisplayflags-enumeration"></a><span data-ttu-id="eea5a-102">Enumerazione ASM_DISPLAY_FLAGS</span><span class="sxs-lookup"><span data-stu-id="eea5a-102">ASM_DISPLAY_FLAGS Enumeration</span></span>
<span data-ttu-id="eea5a-103">Indica la versione, compilazione, delle impostazioni cultura, firma e così via, dell'assembly verrà recuperato il cui nome visualizzato per il [GetDisplayName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="eea5a-103">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eea5a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eea5a-104">Syntax</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="eea5a-105">Note</span><span class="sxs-lookup"><span data-stu-id="eea5a-105">Remarks</span></span>  
 <span data-ttu-id="eea5a-106">`ASM_DISPLAYF_FULL` rispecchia tutte le modifiche apportate alla versione del [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="eea5a-106">`ASM_DISPLAYF_FULL` reflects any changes made to the version of the [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span> <span data-ttu-id="eea5a-107">Non presupporre che il valore restituito è modificabile.</span><span class="sxs-lookup"><span data-stu-id="eea5a-107">Do not assume that the returned value is immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eea5a-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eea5a-108">Requirements</span></span>  
 <span data-ttu-id="eea5a-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eea5a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eea5a-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="eea5a-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="eea5a-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="eea5a-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eea5a-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eea5a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eea5a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eea5a-113">See also</span></span>

- [<span data-ttu-id="eea5a-114">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="eea5a-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="eea5a-115">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="eea5a-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)

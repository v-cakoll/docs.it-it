---
title: Enumerazione ASM_NAME
ms.date: 03/30/2017
api_name:
- ASM_NAME
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_NAME
helpviewer_keywords:
- ASM_NAME enumeration [.NET Framework fusion]
ms.assetid: c8b65b19-d777-428f-bc0c-0d84c78a37bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b37e9c2874448b5fff82f6a37f6ca850875f2b04
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914602"
---
# <a name="asmname-enumeration"></a><span data-ttu-id="faeac-102">Enumerazione ASM_NAME</span><span class="sxs-lookup"><span data-stu-id="faeac-102">ASM_NAME Enumeration</span></span>
<span data-ttu-id="faeac-103">Indica la versione, compilazione, le impostazioni cultura, firma e così via, dell'assembly le cui proprietà saranno recuperate o impostate [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) metodi.</span><span class="sxs-lookup"><span data-stu-id="faeac-103">Indicates the version, build, culture, signature, and so on, of the assembly whose properties will be retrieved or set by [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faeac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="faeac-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    ASM_NAME_PUBLIC_KEY = 0,  
    ASM_NAME_PUBLIC_KEY_TOKEN,  
    ASM_NAME_HASH_VALUE,  
    ASM_NAME_NAME,  
    ASM_NAME_MAJOR_VERSION,  
    ASM_NAME_MINOR_VERSION,  
    ASM_NAME_BUILD_NUMBER,  
    ASM_NAME_REVISION_NUMBER,  
    ASM_NAME_CULTURE,  
    ASM_NAME_PROCESSOR_ID_ARRAY,  
    ASM_NAME_OSINFO_ARRAY,  
    ASM_NAME_HASH_ALGID,  
    ASM_NAME_ALIAS,  
    ASM_NAME_CODEBASE_URL,  
    ASM_NAME_CODEBASE_LASTMOD,  
    ASM_NAME_NULL_PUBLIC_KEY,  
    ASM_NAME_NULL_PUBLIC_KEY_TOKEN,  
    ASM_NAME_CUSTOM,  
    ASM_NAME_NULL_CUSTOM,   
    ASM_NAME_MVID,  
    ASM_NAME_FILE_MAJOR_VERSION,  
    ASM_NAME_FILE_MINOR_VERSION,  
    ASM_NAME_FILE_BUILD_NUMBER,  
    ASM_NAME_FILE_REVISION_NUMBER,  
    ASM_NAME_RETARGET,  
    ASM_NAME_SIGNATURE_BLOB,  
    ASM_NAME_CONFIG_MASK,  
    ASM_NAME_ARCHITECTURE,  
    ASM_NAME_MAX_PARAMS  
  
} ASM_NAME;  
```  
  
## <a name="requirements"></a><span data-ttu-id="faeac-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="faeac-105">Requirements</span></span>  
 <span data-ttu-id="faeac-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faeac-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faeac-107">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="faeac-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="faeac-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="faeac-108">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="faeac-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faeac-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faeac-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="faeac-110">See also</span></span>

- [<span data-ttu-id="faeac-111">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="faeac-111">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="faeac-112">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="faeac-112">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)

---
title: Struttura COR_PRF_CODE_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_CODE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODE_INFO
helpviewer_keywords:
- COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 852e6cbd666441b92afb583b15b72d50d26eff8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449784"
---
# <a name="corprfcodeinfo-structure"></a><span data-ttu-id="16b2a-102">Struttura COR_PRF_CODE_INFO</span><span class="sxs-lookup"><span data-stu-id="16b2a-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="16b2a-103">Rappresenta un blocco contiguo di codice nativo archiviato in memoria.</span><span class="sxs-lookup"><span data-stu-id="16b2a-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16b2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16b2a-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="16b2a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="16b2a-105">Members</span></span>  
  
|<span data-ttu-id="16b2a-106">Membro</span><span class="sxs-lookup"><span data-stu-id="16b2a-106">Member</span></span>|<span data-ttu-id="16b2a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16b2a-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="16b2a-108">L'indirizzo iniziale del blocco contiguo di codice.</span><span class="sxs-lookup"><span data-stu-id="16b2a-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="16b2a-109">Le dimensioni del blocco.</span><span class="sxs-lookup"><span data-stu-id="16b2a-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="16b2a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16b2a-110">Requirements</span></span>  
 <span data-ttu-id="16b2a-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16b2a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16b2a-112">**Intestazione:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="16b2a-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="16b2a-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="16b2a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16b2a-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16b2a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b2a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16b2a-115">See Also</span></span>  
 [<span data-ttu-id="16b2a-116">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="16b2a-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)

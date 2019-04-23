---
title: Struttura COR_ACTIVE_FUNCTION
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0400da0cd29d642a1be42be7e2b22213ae54b94
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121771"
---
# <a name="coractivefunction-structure"></a><span data-ttu-id="2eb84-102">Struttura COR_ACTIVE_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="2eb84-102">COR_ACTIVE_FUNCTION Structure</span></span>
<span data-ttu-id="2eb84-103">Contiene informazioni sulle funzioni attualmente attive nei frame di un thread.</span><span class="sxs-lookup"><span data-stu-id="2eb84-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="2eb84-104">Questa struttura viene utilizzata per la [ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="2eb84-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eb84-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2eb84-105">Syntax</span></span>  
  
```  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="2eb84-106">Membri</span><span class="sxs-lookup"><span data-stu-id="2eb84-106">Members</span></span>  
  
|<span data-ttu-id="2eb84-107">Member</span><span class="sxs-lookup"><span data-stu-id="2eb84-107">Member</span></span>|<span data-ttu-id="2eb84-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2eb84-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="2eb84-109">Puntatore al proprietario del dominio dell'applicazione dei `ilOffset` campo.</span><span class="sxs-lookup"><span data-stu-id="2eb84-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="2eb84-110">Puntatore al proprietario del modulo di `ilOffset` campo.</span><span class="sxs-lookup"><span data-stu-id="2eb84-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="2eb84-111">Puntatore al proprietario della funzione di `ilOffset` campo.</span><span class="sxs-lookup"><span data-stu-id="2eb84-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="2eb84-112">Offset Microsoft intermediate language (MSIL) del frame.</span><span class="sxs-lookup"><span data-stu-id="2eb84-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="2eb84-113">Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="2eb84-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2eb84-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2eb84-114">Requirements</span></span>  
 <span data-ttu-id="2eb84-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2eb84-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2eb84-116">**Intestazione:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="2eb84-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="2eb84-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2eb84-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2eb84-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2eb84-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eb84-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2eb84-119">See also</span></span>

- [<span data-ttu-id="2eb84-120">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="2eb84-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="2eb84-121">Debug</span><span class="sxs-lookup"><span data-stu-id="2eb84-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

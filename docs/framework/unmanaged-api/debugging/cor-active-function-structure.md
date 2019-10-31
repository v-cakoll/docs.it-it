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
ms.openlocfilehash: cbc272070e9eb6810b34ec1f3fdc9e944c624cd3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132387"
---
# <a name="cor_active_function-structure"></a><span data-ttu-id="b9fae-102">Struttura COR_ACTIVE_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="b9fae-102">COR_ACTIVE_FUNCTION Structure</span></span>
<span data-ttu-id="b9fae-103">Contiene informazioni sulle funzioni attualmente attive nei frame di un thread.</span><span class="sxs-lookup"><span data-stu-id="b9fae-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="b9fae-104">Questa struttura viene utilizzata dal metodo [ICorDebugThread2:: GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b9fae-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9fae-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9fae-105">Syntax</span></span>  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="b9fae-106">Members</span><span class="sxs-lookup"><span data-stu-id="b9fae-106">Members</span></span>  
  
|<span data-ttu-id="b9fae-107">Member</span><span class="sxs-lookup"><span data-stu-id="b9fae-107">Member</span></span>|<span data-ttu-id="b9fae-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9fae-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="b9fae-109">Puntatore al proprietario del dominio dell'applicazione del campo `ilOffset`.</span><span class="sxs-lookup"><span data-stu-id="b9fae-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="b9fae-110">Puntatore al proprietario del modulo del campo `ilOffset`.</span><span class="sxs-lookup"><span data-stu-id="b9fae-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="b9fae-111">Puntatore al proprietario della funzione del campo `ilOffset`.</span><span class="sxs-lookup"><span data-stu-id="b9fae-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="b9fae-112">Offset MSIL (Microsoft Intermediate Language) del frame.</span><span class="sxs-lookup"><span data-stu-id="b9fae-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="b9fae-113">Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="b9fae-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9fae-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9fae-114">Requirements</span></span>  
 <span data-ttu-id="b9fae-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9fae-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9fae-116">**Intestazione:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="b9fae-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="b9fae-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9fae-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9fae-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9fae-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9fae-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9fae-119">See also</span></span>

- [<span data-ttu-id="b9fae-120">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="b9fae-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b9fae-121">Debug</span><span class="sxs-lookup"><span data-stu-id="b9fae-121">Debugging</span></span>](index.md)

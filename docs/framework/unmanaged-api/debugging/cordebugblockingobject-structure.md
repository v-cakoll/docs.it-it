---
title: Struttura CorDebugBlockingObject
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57de11c1c40c05befcf3c99c31c2e07e1ecaec5a
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71273963"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="a3146-102">Struttura CorDebugBlockingObject</span><span class="sxs-lookup"><span data-stu-id="a3146-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="a3146-103">Definisce un oggetto che blocca un thread e il motivo specifico per cui il thread è bloccato.</span><span class="sxs-lookup"><span data-stu-id="a3146-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3146-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3146-104">Syntax</span></span>  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="a3146-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a3146-105">Members</span></span>  
  
|<span data-ttu-id="a3146-106">Member</span><span class="sxs-lookup"><span data-stu-id="a3146-106">Member</span></span>|<span data-ttu-id="a3146-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3146-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="a3146-108">Oggetto su cui è bloccato il thread.</span><span class="sxs-lookup"><span data-stu-id="a3146-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="a3146-109">Questo oggetto è valido solo per la durata dello stato sincronizzato corrente.</span><span class="sxs-lookup"><span data-stu-id="a3146-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="a3146-110">Se due thread sono bloccati sullo stesso oggetto nello stesso stato sincronizzato, è possibile che il metodo [ICorDebugValue:: GetAddress](icordebugvalue-getaddress-method.md) restituisca lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="a3146-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="a3146-111">Tuttavia, le interfacce possono essere o meno equivalenti del puntatore.</span><span class="sxs-lookup"><span data-stu-id="a3146-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="a3146-112">Il numero di millisecondi prima del timeout dell'operazione di blocco oppure il valore infinito, che indica che non verrà timeout. Il valore di timeout specifica l'intervallo di tempo totale per l'operazione di blocco, non il tempo rimanente.</span><span class="sxs-lookup"><span data-stu-id="a3146-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="a3146-113">Motivo per cui il thread è bloccato su questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="a3146-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3146-114">Note</span><span class="sxs-lookup"><span data-stu-id="a3146-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3146-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3146-115">Requirements</span></span>  
 <span data-ttu-id="a3146-116">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3146-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3146-117">**Intestazione:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="a3146-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="a3146-118">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3146-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3146-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3146-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3146-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3146-120">See also</span></span>

- [<span data-ttu-id="a3146-121">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="a3146-121">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="a3146-122">Debug</span><span class="sxs-lookup"><span data-stu-id="a3146-122">Debugging</span></span>](index.md)

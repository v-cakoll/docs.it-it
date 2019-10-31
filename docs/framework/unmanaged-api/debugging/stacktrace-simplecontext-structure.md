---
title: Struttura StackTrace_SimpleContext
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
ms.openlocfilehash: 1cd3c34fc292e4a050fa8a75078283e34425fc8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139125"
---
# <a name="stacktrace_simplecontext-structure"></a><span data-ttu-id="07319-102">Struttura StackTrace_SimpleContext</span><span class="sxs-lookup"><span data-stu-id="07319-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="07319-103">Fornisce un contesto semplice che può essere usato invece di una struttura `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="07319-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07319-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07319-104">Syntax</span></span>  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="07319-105">Members</span><span class="sxs-lookup"><span data-stu-id="07319-105">Members</span></span>  
  
|<span data-ttu-id="07319-106">Member</span><span class="sxs-lookup"><span data-stu-id="07319-106">Member</span></span>|<span data-ttu-id="07319-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07319-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="07319-108">Il puntatore dello stack o il puntatore di stack di immissione (ESP) sulle piattaforme x86.</span><span class="sxs-lookup"><span data-stu-id="07319-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="07319-109">Offset del frame oppure il registro EBP sulle piattaforme x86.</span><span class="sxs-lookup"><span data-stu-id="07319-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="07319-110">Puntatore all'istruzione oppure il puntatore all'istruzione Enter (PEI) sulle piattaforme x86.</span><span class="sxs-lookup"><span data-stu-id="07319-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07319-111">Note</span><span class="sxs-lookup"><span data-stu-id="07319-111">Remarks</span></span>  
 <span data-ttu-id="07319-112">Poiché le funzioni di analisi dello stack in genere devono restituire solo l'indirizzo, l'offset del frame e l'indirizzo dello stack, è possibile usare facoltativamente la struttura di `SimpleContext` anziché una struttura di `CONTEXT` di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="07319-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07319-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="07319-113">Requirements</span></span>  
 <span data-ttu-id="07319-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07319-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07319-115">**Intestazione:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="07319-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="07319-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07319-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07319-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07319-117">See also</span></span>

- [<span data-ttu-id="07319-118">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="07319-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="07319-119">Debug</span><span class="sxs-lookup"><span data-stu-id="07319-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0625dc72d44485dbb69b42cba5387085d1862bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210425"
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="0f298-102">Struttura StackTrace_SimpleContext</span><span class="sxs-lookup"><span data-stu-id="0f298-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="0f298-103">Fornisce un contesto semplice che può essere usato invece di una struttura `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="0f298-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f298-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f298-104">Syntax</span></span>  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="0f298-105">Membri</span><span class="sxs-lookup"><span data-stu-id="0f298-105">Members</span></span>  
  
|<span data-ttu-id="0f298-106">Member</span><span class="sxs-lookup"><span data-stu-id="0f298-106">Member</span></span>|<span data-ttu-id="0f298-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f298-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="0f298-108">Il puntatore dello stack, o il puntatore dello stack invio (ESP) x86 piattaforme.</span><span class="sxs-lookup"><span data-stu-id="0f298-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="0f298-109">L'offset di frame, o il registro EBP x86 piattaforme.</span><span class="sxs-lookup"><span data-stu-id="0f298-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="0f298-110">Il puntatore all'istruzione o il puntatore all'istruzione invio (EIP) x86 piattaforme.</span><span class="sxs-lookup"><span data-stu-id="0f298-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f298-111">Note</span><span class="sxs-lookup"><span data-stu-id="0f298-111">Remarks</span></span>  
 <span data-ttu-id="0f298-112">Poiché le funzioni di traccia dello stack in genere necessario restituire solo l'indirizzo di offset di frame e indirizzo dello stack, è possibile usare la `SimpleContext` struttura invece di un grande `CONTEXT` struttura.</span><span class="sxs-lookup"><span data-stu-id="0f298-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f298-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f298-113">Requirements</span></span>  
 <span data-ttu-id="0f298-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f298-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f298-115">**Intestazione:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="0f298-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="0f298-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f298-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f298-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f298-117">See also</span></span>

- [<span data-ttu-id="0f298-118">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="0f298-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="0f298-119">Debug</span><span class="sxs-lookup"><span data-stu-id="0f298-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

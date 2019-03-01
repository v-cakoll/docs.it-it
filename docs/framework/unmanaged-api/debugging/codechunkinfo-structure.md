---
title: Struttura CodeChunkInfo
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9d5ed028045f14012567ecfa86ff6a5c3d419a1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977916"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="0118b-102">Struttura CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="0118b-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="0118b-103">Rappresenta un singolo blocco di codice in memoria.</span><span class="sxs-lookup"><span data-stu-id="0118b-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0118b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0118b-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="0118b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="0118b-105">Members</span></span>  
  
|<span data-ttu-id="0118b-106">Membro</span><span class="sxs-lookup"><span data-stu-id="0118b-106">Member</span></span>|<span data-ttu-id="0118b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0118b-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="0118b-108">Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo iniziale del blocco.</span><span class="sxs-lookup"><span data-stu-id="0118b-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="0118b-109">Le dimensioni, in byte, del blocco.</span><span class="sxs-lookup"><span data-stu-id="0118b-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0118b-110">Note</span><span class="sxs-lookup"><span data-stu-id="0118b-110">Remarks</span></span>  
 <span data-ttu-id="0118b-111">L'unico blocco di codice è un'area di codice nativo che fa parte di un oggetto di codice, ad esempio una funzione.</span><span class="sxs-lookup"><span data-stu-id="0118b-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0118b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0118b-112">Requirements</span></span>  
 <span data-ttu-id="0118b-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0118b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0118b-114">**Intestazione:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="0118b-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="0118b-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0118b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0118b-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0118b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0118b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0118b-117">See also</span></span>
- [<span data-ttu-id="0118b-118">Metodo GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="0118b-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="0118b-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="0118b-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="0118b-120">Debug</span><span class="sxs-lookup"><span data-stu-id="0118b-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

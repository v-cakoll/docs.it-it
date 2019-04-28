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
ms.openlocfilehash: 58c9d4c66af0bb9f4e66d17b18ac78ef8271bc31
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609607"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="84bed-102">Struttura CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="84bed-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="84bed-103">Rappresenta un singolo blocco di codice in memoria.</span><span class="sxs-lookup"><span data-stu-id="84bed-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84bed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84bed-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="84bed-105">Membri</span><span class="sxs-lookup"><span data-stu-id="84bed-105">Members</span></span>  
  
|<span data-ttu-id="84bed-106">Member</span><span class="sxs-lookup"><span data-stu-id="84bed-106">Member</span></span>|<span data-ttu-id="84bed-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84bed-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="84bed-108">Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo iniziale del blocco.</span><span class="sxs-lookup"><span data-stu-id="84bed-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="84bed-109">Le dimensioni, in byte, del blocco.</span><span class="sxs-lookup"><span data-stu-id="84bed-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84bed-110">Note</span><span class="sxs-lookup"><span data-stu-id="84bed-110">Remarks</span></span>  
 <span data-ttu-id="84bed-111">L'unico blocco di codice è un'area di codice nativo che fa parte di un oggetto di codice, ad esempio una funzione.</span><span class="sxs-lookup"><span data-stu-id="84bed-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84bed-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84bed-112">Requirements</span></span>  
 <span data-ttu-id="84bed-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84bed-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84bed-114">**Intestazione:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="84bed-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="84bed-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84bed-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84bed-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84bed-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84bed-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84bed-117">See also</span></span>

- [<span data-ttu-id="84bed-118">Metodo GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="84bed-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="84bed-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="84bed-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="84bed-120">Debug</span><span class="sxs-lookup"><span data-stu-id="84bed-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

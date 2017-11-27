---
title: CodeChunkInfo Structure1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CodeChunkInfo
api_location: mscordbi.dll
api_type: COM
f1_keywords: CodeChunkInfo
helpviewer_keywords: CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 17727c8927f9db3de3ab26d2504dfae5215a1495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="codechunkinfo-structure1"></a><span data-ttu-id="52c57-102">CodeChunkInfo Structure1</span><span class="sxs-lookup"><span data-stu-id="52c57-102">CodeChunkInfo Structure1</span></span>
<span data-ttu-id="52c57-103">Rappresenta un singolo blocco di codice in memoria.</span><span class="sxs-lookup"><span data-stu-id="52c57-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52c57-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52c57-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="52c57-105">Membri</span><span class="sxs-lookup"><span data-stu-id="52c57-105">Members</span></span>  
  
|<span data-ttu-id="52c57-106">Membro</span><span class="sxs-lookup"><span data-stu-id="52c57-106">Member</span></span>|<span data-ttu-id="52c57-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52c57-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="52c57-108">Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo iniziale del blocco.</span><span class="sxs-lookup"><span data-stu-id="52c57-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="52c57-109">Le dimensioni in byte, del blocco.</span><span class="sxs-lookup"><span data-stu-id="52c57-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52c57-110">Note</span><span class="sxs-lookup"><span data-stu-id="52c57-110">Remarks</span></span>  
 <span data-ttu-id="52c57-111">Il singolo blocco di codice è un'area di codice nativo che fa parte di un oggetto di codice, ad esempio una funzione.</span><span class="sxs-lookup"><span data-stu-id="52c57-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52c57-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52c57-112">Requirements</span></span>  
 <span data-ttu-id="52c57-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52c57-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52c57-114">**Intestazione:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="52c57-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="52c57-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52c57-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52c57-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52c57-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52c57-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52c57-117">See Also</span></span>  
 [<span data-ttu-id="52c57-118">GetCodeChunks (metodo)</span><span class="sxs-lookup"><span data-stu-id="52c57-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 [<span data-ttu-id="52c57-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="52c57-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="52c57-120">Debug</span><span class="sxs-lookup"><span data-stu-id="52c57-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

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
ms.openlocfilehash: 36afee8af3de046683c55215a677a529b0837c77
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274251"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="dfb84-102">Struttura CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="dfb84-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="dfb84-103">Rappresenta un singolo blocco di codice in memoria.</span><span class="sxs-lookup"><span data-stu-id="dfb84-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfb84-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dfb84-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="dfb84-105">Membri</span><span class="sxs-lookup"><span data-stu-id="dfb84-105">Members</span></span>  
  
|<span data-ttu-id="dfb84-106">Member</span><span class="sxs-lookup"><span data-stu-id="dfb84-106">Member</span></span>|<span data-ttu-id="dfb84-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfb84-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="dfb84-108">`CORDB_ADDRESS` Valore che specifica l'indirizzo iniziale del blocco.</span><span class="sxs-lookup"><span data-stu-id="dfb84-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="dfb84-109">Dimensione, in byte, del blocco.</span><span class="sxs-lookup"><span data-stu-id="dfb84-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfb84-110">Note</span><span class="sxs-lookup"><span data-stu-id="dfb84-110">Remarks</span></span>  
 <span data-ttu-id="dfb84-111">Il singolo blocco di codice è un'area di codice nativo che fa parte di un oggetto di codice, ad esempio una funzione.</span><span class="sxs-lookup"><span data-stu-id="dfb84-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfb84-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dfb84-112">Requirements</span></span>  
 <span data-ttu-id="dfb84-113">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfb84-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfb84-114">**Intestazione:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="dfb84-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="dfb84-115">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfb84-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfb84-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfb84-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb84-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfb84-117">See also</span></span>

- [<span data-ttu-id="dfb84-118">Metodo GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="dfb84-118">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="dfb84-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="dfb84-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="dfb84-120">Debug</span><span class="sxs-lookup"><span data-stu-id="dfb84-120">Debugging</span></span>](index.md)

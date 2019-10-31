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
ms.openlocfilehash: d33c8b31473e389e07fb24076dc32272e9dde387
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132396"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="f0f42-102">Struttura CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="f0f42-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="f0f42-103">Rappresenta un singolo blocco di codice in memoria.</span><span class="sxs-lookup"><span data-stu-id="f0f42-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0f42-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0f42-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="f0f42-105">Members</span><span class="sxs-lookup"><span data-stu-id="f0f42-105">Members</span></span>  
  
|<span data-ttu-id="f0f42-106">Member</span><span class="sxs-lookup"><span data-stu-id="f0f42-106">Member</span></span>|<span data-ttu-id="f0f42-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0f42-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="f0f42-108">Valore `CORDB_ADDRESS` che specifica l'indirizzo iniziale del blocco.</span><span class="sxs-lookup"><span data-stu-id="f0f42-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="f0f42-109">Dimensione, in byte, del blocco.</span><span class="sxs-lookup"><span data-stu-id="f0f42-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0f42-110">Note</span><span class="sxs-lookup"><span data-stu-id="f0f42-110">Remarks</span></span>  
 <span data-ttu-id="f0f42-111">Il singolo blocco di codice è un'area di codice nativo che fa parte di un oggetto di codice, ad esempio una funzione.</span><span class="sxs-lookup"><span data-stu-id="f0f42-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0f42-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0f42-112">Requirements</span></span>  
 <span data-ttu-id="f0f42-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0f42-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0f42-114">**Intestazione:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="f0f42-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="f0f42-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0f42-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0f42-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0f42-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f42-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0f42-117">See also</span></span>

- [<span data-ttu-id="f0f42-118">Metodo GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="f0f42-118">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="f0f42-119">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="f0f42-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="f0f42-120">Debug</span><span class="sxs-lookup"><span data-stu-id="f0f42-120">Debugging</span></span>](index.md)

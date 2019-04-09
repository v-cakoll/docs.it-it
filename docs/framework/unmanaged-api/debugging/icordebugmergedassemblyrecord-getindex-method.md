---
title: Metodo ICorDebugMergedAssemblyRecord::GetIndex
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8ba470325098125aee8ef7de01fa6aa70596d42
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202599"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="bdb3a-102">Metodo ICorDebugMergedAssemblyRecord::GetIndex</span><span class="sxs-lookup"><span data-stu-id="bdb3a-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="bdb3a-103">Ottiene l'indice del prefisso dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bdb3a-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdb3a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bdb3a-104">Syntax</span></span>  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdb3a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bdb3a-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="bdb3a-106">[out] Puntatore all'indice del prefisso.</span><span class="sxs-lookup"><span data-stu-id="bdb3a-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdb3a-107">Note</span><span class="sxs-lookup"><span data-stu-id="bdb3a-107">Remarks</span></span>  
 <span data-ttu-id="bdb3a-108">L'indice del prefisso viene usato per evitare conflitti di nome nei nomi dei tipi di metadati uniti.</span><span class="sxs-lookup"><span data-stu-id="bdb3a-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdb3a-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bdb3a-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdb3a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bdb3a-110">Requirements</span></span>  
 <span data-ttu-id="bdb3a-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdb3a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdb3a-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdb3a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdb3a-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdb3a-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bdb3a-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bdb3a-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bdb3a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdb3a-115">See also</span></span>

- [<span data-ttu-id="bdb3a-116">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="bdb3a-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="bdb3a-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="bdb3a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

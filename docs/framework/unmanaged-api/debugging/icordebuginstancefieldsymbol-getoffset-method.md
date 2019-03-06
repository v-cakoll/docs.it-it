---
title: Metodo ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a88de396d946c37b30688ab614d2bcc549c86873
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468130"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="06996-102">Metodo ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="06996-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="06996-103">Ottiene l'offset, in byte, di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="06996-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06996-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06996-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06996-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="06996-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="06996-106">Puntatore al numero di byte di offset di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="06996-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06996-107">Note</span><span class="sxs-lookup"><span data-stu-id="06996-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06996-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="06996-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06996-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06996-109">Requirements</span></span>  
 <span data-ttu-id="06996-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06996-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06996-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06996-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06996-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06996-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06996-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06996-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06996-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06996-114">See also</span></span>
- [<span data-ttu-id="06996-115">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="06996-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="06996-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="06996-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

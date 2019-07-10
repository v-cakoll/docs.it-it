---
title: 'Metodo icordebugvariablesymbol:: GetSize'
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e963e655c933c9191953bb32ba0b73adf0ae86d7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774876"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="009f4-102">Metodo icordebugvariablesymbol:: GetSize</span><span class="sxs-lookup"><span data-stu-id="009f4-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="009f4-103">Ottiene le dimensioni di una variabile in byte.</span><span class="sxs-lookup"><span data-stu-id="009f4-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="009f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="009f4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="009f4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="009f4-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="009f4-106">Puntatore a un intero senza segno a 32 bit che contiene le dimensioni della variabile.</span><span class="sxs-lookup"><span data-stu-id="009f4-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="009f4-107">Note</span><span class="sxs-lookup"><span data-stu-id="009f4-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="009f4-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="009f4-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="009f4-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="009f4-109">Requirements</span></span>  
 <span data-ttu-id="009f4-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="009f4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="009f4-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="009f4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="009f4-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="009f4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="009f4-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="009f4-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="009f4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="009f4-114">See also</span></span>

- [<span data-ttu-id="009f4-115">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="009f4-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="009f4-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="009f4-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

---
title: Metodo ICorDebugVariableSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01349b6418008db51c432d5c49f8491a44ab60d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419410"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="9f8fd-102">Metodo ICorDebugVariableSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="9f8fd-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="9f8fd-103">Ottiene le dimensioni di una variabile in byte.</span><span class="sxs-lookup"><span data-stu-id="9f8fd-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f8fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f8fd-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f8fd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9f8fd-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="9f8fd-106">Puntatore a un intero senza segno a 32 bit che contiene le dimensioni della variabile.</span><span class="sxs-lookup"><span data-stu-id="9f8fd-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f8fd-107">Note</span><span class="sxs-lookup"><span data-stu-id="9f8fd-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f8fd-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9f8fd-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f8fd-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f8fd-109">Requirements</span></span>  
 <span data-ttu-id="9f8fd-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f8fd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f8fd-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9f8fd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f8fd-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9f8fd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f8fd-113">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f8fd-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f8fd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f8fd-114">See Also</span></span>  
 [<span data-ttu-id="9f8fd-115">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="9f8fd-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="9f8fd-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9f8fd-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

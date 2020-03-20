---
title: Metodo ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 500d36b414be686071990a6e1b40dd8759d02ae9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178923"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="a1b8c-102">Metodo ICorDebugDataTarget2::GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="a1b8c-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="a1b8c-103">Restituisce il provider di simboli per un modulo dall'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="a1b8c-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1b8c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1b8c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1b8c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1b8c-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="a1b8c-106">[in] Oggetto [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valore che rappresenta l'indirizzo di base di un modulo.</span><span class="sxs-lookup"><span data-stu-id="a1b8c-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="a1b8c-107">[fuori] Puntatore all'indirizzo di un [oggetto ICorDebugSymbolProvider.](icordebugsymbolprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="a1b8c-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1b8c-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a1b8c-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1b8c-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a1b8c-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1b8c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1b8c-110">Requirements</span></span>  
 <span data-ttu-id="a1b8c-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1b8c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1b8c-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1b8c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1b8c-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1b8c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1b8c-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1b8c-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1b8c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1b8c-115">See also</span></span>

- [<span data-ttu-id="a1b8c-116">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="a1b8c-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="a1b8c-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a1b8c-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

---
title: Metodo ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: bada60295c3a9b3a702aa674e06f8f5cf6ac0a24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788831"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="9f047-102">Metodo ICorDebugDataTarget2::GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="9f047-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="9f047-103">Restituisce il provider di simboli per un modulo dall'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="9f047-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f047-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f047-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,   
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f047-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9f047-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="9f047-106">in Valore [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) che rappresenta l'indirizzo di base di un modulo.</span><span class="sxs-lookup"><span data-stu-id="9f047-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="9f047-107">out Puntatore all'indirizzo di un oggetto [Metodo icordebugsymbolprovider](icordebugsymbolprovider-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9f047-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f047-108">Note</span><span class="sxs-lookup"><span data-stu-id="9f047-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9f047-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9f047-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f047-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9f047-110">Requirements</span></span>  
 <span data-ttu-id="9f047-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f047-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f047-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f047-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f047-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f047-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f047-114">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f047-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f047-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f047-115">See also</span></span>

- [<span data-ttu-id="9f047-116">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="9f047-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="9f047-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9f047-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

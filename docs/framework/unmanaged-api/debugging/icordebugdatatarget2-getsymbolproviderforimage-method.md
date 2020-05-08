---
title: Metodo ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 7800630be0ed9afb321d607046be308088781388
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976447"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="4187e-102">Metodo ICorDebugDataTarget2::GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="4187e-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="4187e-103">Restituisce il provider di simboli per un modulo dall'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="4187e-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4187e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4187e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4187e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4187e-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="4187e-106">in Valore [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) che rappresenta l'indirizzo di base di un modulo.</span><span class="sxs-lookup"><span data-stu-id="4187e-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="4187e-107">out Puntatore all'indirizzo di un oggetto [Metodo icordebugsymbolprovider](icordebugsymbolprovider-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4187e-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4187e-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4187e-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4187e-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4187e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4187e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4187e-110">Requirements</span></span>  
 <span data-ttu-id="4187e-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4187e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4187e-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4187e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4187e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4187e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4187e-114">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4187e-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4187e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4187e-115">See also</span></span>

- [<span data-ttu-id="4187e-116">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="4187e-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="4187e-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4187e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

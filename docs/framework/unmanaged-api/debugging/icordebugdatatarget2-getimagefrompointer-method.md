---
title: Metodo ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5dab9183075f563f52a4fc982eda5cb172556554
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154375"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="fe55c-102">Metodo ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="fe55c-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="fe55c-103">Restituisce l'indirizzo di base e le dimensioni del modulo da un indirizzo contenuto nel modulo.</span><span class="sxs-lookup"><span data-stu-id="fe55c-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe55c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe55c-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe55c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe55c-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="fe55c-106">Oggetto [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valore che rappresenta un indirizzo di un modulo.</span><span class="sxs-lookup"><span data-stu-id="fe55c-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="fe55c-107">[out] Oggetto [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valore che rappresenta l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="fe55c-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="fe55c-108">Un puntatore alle dimensioni del modulo.</span><span class="sxs-lookup"><span data-stu-id="fe55c-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe55c-109">Note</span><span class="sxs-lookup"><span data-stu-id="fe55c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe55c-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fe55c-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe55c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe55c-111">Requirements</span></span>  
 <span data-ttu-id="fe55c-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe55c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe55c-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe55c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe55c-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe55c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe55c-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe55c-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe55c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe55c-116">See also</span></span>

- [<span data-ttu-id="fe55c-117">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="fe55c-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="fe55c-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fe55c-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

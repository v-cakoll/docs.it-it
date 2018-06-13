---
title: Metodo ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ddb891091988a21013ee71272d489e7fd1f1283
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411005"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="d153d-102">Metodo ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="d153d-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="d153d-103">Restituisce l'indirizzo di base e le dimensioni del modulo da un indirizzo contenuto nel modulo.</span><span class="sxs-lookup"><span data-stu-id="d153d-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d153d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d153d-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d153d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d153d-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="d153d-106">Oggetto [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valore che rappresenta un indirizzo in un modulo.</span><span class="sxs-lookup"><span data-stu-id="d153d-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="d153d-107">[out] Oggetto [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valore che rappresenta l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="d153d-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="d153d-108">Un puntatore alle dimensioni del modulo.</span><span class="sxs-lookup"><span data-stu-id="d153d-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d153d-109">Note</span><span class="sxs-lookup"><span data-stu-id="d153d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d153d-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d153d-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d153d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d153d-111">Requirements</span></span>  
 <span data-ttu-id="d153d-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d153d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d153d-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="d153d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d153d-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d153d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d153d-115">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d153d-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d153d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d153d-116">See Also</span></span>  
 [<span data-ttu-id="d153d-117">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="d153d-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="d153d-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d153d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

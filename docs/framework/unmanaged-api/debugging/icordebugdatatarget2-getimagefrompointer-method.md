---
title: Metodo ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 3ac1f8ab98583357a3aa622b5032d9ae121ebdf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178924"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="6346a-102">Metodo ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="6346a-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="6346a-103">Restituisce l'indirizzo di base e le dimensioni del modulo da un indirizzo contenuto nel modulo.</span><span class="sxs-lookup"><span data-stu-id="6346a-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6346a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6346a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6346a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6346a-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="6346a-106">Oggetto [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valore che rappresenta un indirizzo in un modulo.</span><span class="sxs-lookup"><span data-stu-id="6346a-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="6346a-107">[fuori] Valore [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) che rappresenta l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="6346a-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="6346a-108">Un puntatore alle dimensioni del modulo.</span><span class="sxs-lookup"><span data-stu-id="6346a-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6346a-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6346a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6346a-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6346a-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6346a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6346a-111">Requirements</span></span>  
 <span data-ttu-id="6346a-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6346a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6346a-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6346a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6346a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6346a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6346a-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6346a-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6346a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6346a-116">See also</span></span>

- [<span data-ttu-id="6346a-117">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="6346a-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="6346a-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6346a-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

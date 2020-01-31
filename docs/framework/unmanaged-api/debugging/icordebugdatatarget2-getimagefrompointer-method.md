---
title: Metodo ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 55c87731399cf1e7a6747720b8bb33de7e01906c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788836"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="c420b-102">Metodo ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="c420b-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="c420b-103">Restituisce l'indirizzo di base e le dimensioni del modulo da un indirizzo contenuto nel modulo.</span><span class="sxs-lookup"><span data-stu-id="c420b-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c420b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c420b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c420b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c420b-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="c420b-106">Valore [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) che rappresenta un indirizzo in un modulo.</span><span class="sxs-lookup"><span data-stu-id="c420b-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="c420b-107">out Valore [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) che rappresenta l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="c420b-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="c420b-108">Un puntatore alle dimensioni del modulo.</span><span class="sxs-lookup"><span data-stu-id="c420b-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c420b-109">Note</span><span class="sxs-lookup"><span data-stu-id="c420b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c420b-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c420b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c420b-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="c420b-111">Requirements</span></span>  
 <span data-ttu-id="c420b-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c420b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c420b-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c420b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c420b-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c420b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c420b-115">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c420b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c420b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c420b-116">See also</span></span>

- [<span data-ttu-id="c420b-117">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="c420b-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="c420b-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c420b-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

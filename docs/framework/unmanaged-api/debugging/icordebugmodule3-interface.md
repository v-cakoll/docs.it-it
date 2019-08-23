---
title: Interfaccia ICorDebugModule3
ms.date: 03/30/2017
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e51ff64115ce3417087eee6845aa802ad64f2a72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961002"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="ef794-102">Interfaccia ICorDebugModule3</span><span class="sxs-lookup"><span data-stu-id="ef794-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="ef794-103">Crea un lettore di simboli per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="ef794-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef794-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef794-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ef794-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ef794-105">Methods</span></span>  
  
|<span data-ttu-id="ef794-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="ef794-106">Method</span></span>|<span data-ttu-id="ef794-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef794-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ef794-108">Metodo ICorDebugModule3::CreateReaderForInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="ef794-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="ef794-109">Crea un lettore di simboli (in genere [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="ef794-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef794-110">Note</span><span class="sxs-lookup"><span data-stu-id="ef794-110">Remarks</span></span>  
 <span data-ttu-id="ef794-111">Questa interfaccia estende logicamente le interfacce "ICorDebugModule" e "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="ef794-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef794-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="ef794-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef794-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef794-113">Requirements</span></span>  
 <span data-ttu-id="ef794-114">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef794-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef794-115">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ef794-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef794-116">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef794-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef794-117">**Versioni .NET Framework:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="ef794-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ef794-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef794-118">See also</span></span>

- [<span data-ttu-id="ef794-119">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="ef794-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="ef794-120">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="ef794-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="ef794-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ef794-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

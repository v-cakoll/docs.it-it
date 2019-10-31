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
ms.openlocfilehash: 07919398b658d735fe4c9818ab24d27d586b6629
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122555"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="0bbb4-102">Interfaccia ICorDebugModule3</span><span class="sxs-lookup"><span data-stu-id="0bbb4-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="0bbb4-103">Crea un lettore di simboli per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="0bbb4-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bbb4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0bbb4-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="0bbb4-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="0bbb4-105">Methods</span></span>  
  
|<span data-ttu-id="0bbb4-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="0bbb4-106">Method</span></span>|<span data-ttu-id="0bbb4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0bbb4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0bbb4-108">Metodo ICorDebugModule3::CreateReaderForInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="0bbb4-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="0bbb4-109">Crea un lettore di simboli (in genere [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="0bbb4-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bbb4-110">Note</span><span class="sxs-lookup"><span data-stu-id="0bbb4-110">Remarks</span></span>  
 <span data-ttu-id="0bbb4-111">Questa interfaccia estende logicamente le interfacce "ICorDebugModule" e "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="0bbb4-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0bbb4-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="0bbb4-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bbb4-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0bbb4-113">Requirements</span></span>  
 <span data-ttu-id="0bbb4-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bbb4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bbb4-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bbb4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bbb4-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bbb4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bbb4-117">**Versioni .NET Framework:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="0bbb4-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0bbb4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bbb4-118">See also</span></span>

- [<span data-ttu-id="0bbb4-119">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="0bbb4-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="0bbb4-120">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="0bbb4-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="0bbb4-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0bbb4-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

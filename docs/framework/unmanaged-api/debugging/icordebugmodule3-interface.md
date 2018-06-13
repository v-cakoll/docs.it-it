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
ms.openlocfilehash: 5fc4c0560c2aa0d66c1b40d78458a2d44284e232
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417915"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="717f8-102">Interfaccia ICorDebugModule3</span><span class="sxs-lookup"><span data-stu-id="717f8-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="717f8-103">Crea un lettore di simboli per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="717f8-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="717f8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="717f8-104">Syntax</span></span>  
  
```  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="717f8-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="717f8-105">Methods</span></span>  
  
|<span data-ttu-id="717f8-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="717f8-106">Method</span></span>|<span data-ttu-id="717f8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="717f8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="717f8-108">Metodo ICorDebugModule3::CreateReaderForInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="717f8-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="717f8-109">Crea un lettore di simboli (in genere [interfaccia ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="717f8-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="717f8-110">Note</span><span class="sxs-lookup"><span data-stu-id="717f8-110">Remarks</span></span>  
 <span data-ttu-id="717f8-111">Questa interfaccia estende logicamente le interfacce "ICorDebugModule" e "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="717f8-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="717f8-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="717f8-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="717f8-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="717f8-113">Requirements</span></span>  
 <span data-ttu-id="717f8-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="717f8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="717f8-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="717f8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="717f8-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="717f8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="717f8-117">**Versioni di .NET framework:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="717f8-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="717f8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="717f8-118">See Also</span></span>  
 [<span data-ttu-id="717f8-119">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="717f8-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="717f8-120">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="717f8-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="717f8-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="717f8-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

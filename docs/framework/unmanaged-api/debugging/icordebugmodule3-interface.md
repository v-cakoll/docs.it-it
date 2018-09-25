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
ms.openlocfilehash: 58bad617eb91b7e529ff3d95edd06a5c73feee64
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47111750"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="695f6-102">Interfaccia ICorDebugModule3</span><span class="sxs-lookup"><span data-stu-id="695f6-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="695f6-103">Crea un lettore di simboli per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="695f6-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="695f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="695f6-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="695f6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="695f6-105">Methods</span></span>  
  
|<span data-ttu-id="695f6-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="695f6-106">Method</span></span>|<span data-ttu-id="695f6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="695f6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="695f6-108">Metodo ICorDebugModule3::CreateReaderForInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="695f6-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="695f6-109">Crea un lettore di simboli (in genere [interfaccia di ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="695f6-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="695f6-110">Note</span><span class="sxs-lookup"><span data-stu-id="695f6-110">Remarks</span></span>  
 <span data-ttu-id="695f6-111">Questa interfaccia estende logicamente le interfacce "ICorDebugModule" e "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="695f6-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="695f6-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="695f6-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="695f6-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="695f6-113">Requirements</span></span>  
 <span data-ttu-id="695f6-114">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="695f6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="695f6-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="695f6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="695f6-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="695f6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="695f6-117">**Versioni di .NET framework:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="695f6-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="695f6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="695f6-118">See Also</span></span>  
 [<span data-ttu-id="695f6-119">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="695f6-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="695f6-120">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="695f6-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="695f6-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="695f6-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

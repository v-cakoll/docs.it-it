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
ms.openlocfilehash: 69fd3e2df4a4eafe91cc025f28e1387cc443ea04
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212308"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="fce5f-102">Interfaccia ICorDebugModule3</span><span class="sxs-lookup"><span data-stu-id="fce5f-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="fce5f-103">Crea un lettore di simboli per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="fce5f-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fce5f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fce5f-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="fce5f-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="fce5f-105">Methods</span></span>  
  
|<span data-ttu-id="fce5f-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="fce5f-106">Method</span></span>|<span data-ttu-id="fce5f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fce5f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fce5f-108">Metodo ICorDebugModule3::CreateReaderForInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="fce5f-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="fce5f-109">Crea un lettore di simboli (in genere [ISymUnmanagedReader Interface](../diagnostics/isymunmanagedreader-interface.md)) per un modulo dinamico.</span><span class="sxs-lookup"><span data-stu-id="fce5f-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fce5f-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fce5f-110">Remarks</span></span>  
 <span data-ttu-id="fce5f-111">Questa interfaccia estende logicamente le interfacce "ICorDebugModule" e "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="fce5f-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fce5f-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="fce5f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fce5f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fce5f-113">Requirements</span></span>  
 <span data-ttu-id="fce5f-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fce5f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fce5f-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fce5f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fce5f-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fce5f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fce5f-117">**Versioni .NET Framework:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="fce5f-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fce5f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fce5f-118">See also</span></span>

- [<span data-ttu-id="fce5f-119">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="fce5f-119">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="fce5f-120">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="fce5f-120">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="fce5f-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fce5f-121">Debugging Interfaces</span></span>](debugging-interfaces.md)

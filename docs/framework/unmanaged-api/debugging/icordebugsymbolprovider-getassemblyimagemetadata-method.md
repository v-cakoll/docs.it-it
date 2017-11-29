---
title: Metodo ICorDebugSymbolProvider::GetAssemblyImageMetadata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 48e5e9daf191cb2f4112dd2a957f29c0a7521398
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="0be55-102">Metodo ICorDebugSymbolProvider::GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="0be55-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="0be55-103">Restituisce i metadati da un assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="0be55-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0be55-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0be55-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0be55-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0be55-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="0be55-106">[out] Un puntatore all'indirizzo di un [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) oggetto che contiene informazioni sulle dimensioni e l'indirizzo dei metadati dell'assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="0be55-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0be55-107">Note</span><span class="sxs-lookup"><span data-stu-id="0be55-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0be55-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0be55-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0be55-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0be55-109">Requirements</span></span>  
 <span data-ttu-id="0be55-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0be55-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0be55-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0be55-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0be55-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0be55-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0be55-113">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0be55-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be55-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0be55-114">See Also</span></span>  
 [<span data-ttu-id="0be55-115">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="0be55-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="0be55-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0be55-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

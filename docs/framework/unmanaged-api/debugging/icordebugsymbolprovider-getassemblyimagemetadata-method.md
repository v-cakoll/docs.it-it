---
title: Metodo ICorDebugSymbolProvider::GetAssemblyImageMetadata
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: 3ee80c18d3091406bf0bbd5b22c5f6021888906d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791663"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="597be-102">Metodo ICorDebugSymbolProvider::GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="597be-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="597be-103">Restituisce i metadati da un assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="597be-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="597be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="597be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="597be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="597be-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="597be-106">out Puntatore all'indirizzo di un oggetto [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) che contiene informazioni sulle dimensioni e sull'indirizzo dei metadati dell'assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="597be-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="597be-107">Note</span><span class="sxs-lookup"><span data-stu-id="597be-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="597be-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="597be-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="597be-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="597be-109">Requirements</span></span>  
 <span data-ttu-id="597be-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="597be-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="597be-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="597be-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="597be-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="597be-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="597be-113">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="597be-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="597be-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="597be-114">See also</span></span>

- [<span data-ttu-id="597be-115">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="597be-115">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="597be-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="597be-116">Debugging Interfaces</span></span>](debugging-interfaces.md)

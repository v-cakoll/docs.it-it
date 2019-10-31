---
title: 'Metodo metodo icordebugsymbolprovider:: GetAssemblyImageBytes'
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: 3184ba116704df8945b53766e62435a4252eaa11
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138930"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="9c5dc-102">Metodo metodo icordebugsymbolprovider:: GetAssemblyImageBytes</span><span class="sxs-lookup"><span data-stu-id="9c5dc-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="9c5dc-103">Legge i dati da un assembly sottoposto a merge tramite un indirizzo RVA (Relative Virtual Address) specificato nell'assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="9c5dc-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c5dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c5dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c5dc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9c5dc-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="9c5dc-106">[in] Indirizzo RVA (Relative Virtual Address) in un assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="9c5dc-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="9c5dc-107">Numero di byte da leggere dall'assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="9c5dc-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="9c5dc-108">Puntatore all'indirizzo di un oggetto [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) che contiene informazioni sul buffer di memoria con i metadati dell'assembly Uniti.</span><span class="sxs-lookup"><span data-stu-id="9c5dc-108">A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c5dc-109">Note</span><span class="sxs-lookup"><span data-stu-id="9c5dc-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c5dc-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9c5dc-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c5dc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9c5dc-111">Requirements</span></span>  
 <span data-ttu-id="9c5dc-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c5dc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c5dc-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c5dc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c5dc-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c5dc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c5dc-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c5dc-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c5dc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c5dc-116">See also</span></span>

- [<span data-ttu-id="9c5dc-117">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="9c5dc-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="9c5dc-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9c5dc-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

---
title: Metodo ICorDebugSymbolProvider::GetAssemblyImageBytes
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: 6361b12802876ef480acbe1cc13f32b77ba0be49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178485"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="69c4f-102">Metodo ICorDebugSymbolProvider::GetAssemblyImageBytes</span><span class="sxs-lookup"><span data-stu-id="69c4f-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="69c4f-103">Legge i dati da un assembly sottoposto a merge tramite un indirizzo RVA (Relative Virtual Address) specificato nell'assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="69c4f-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69c4f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="69c4f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,
   [in] ULONG32 length,
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69c4f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="69c4f-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="69c4f-106">[in] Indirizzo RVA (Relative Virtual Address) in un assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="69c4f-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="69c4f-107">Numero di byte da leggere dall'assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="69c4f-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="69c4f-108">Puntatore all'indirizzo di un oggetto [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) che contiene informazioni sul buffer di memoria con i metadati dell'assembly uniti.</span><span class="sxs-lookup"><span data-stu-id="69c4f-108">A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69c4f-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="69c4f-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69c4f-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="69c4f-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69c4f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="69c4f-111">Requirements</span></span>  
 <span data-ttu-id="69c4f-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69c4f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69c4f-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69c4f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69c4f-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69c4f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69c4f-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69c4f-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c4f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69c4f-116">See also</span></span>

- [<span data-ttu-id="69c4f-117">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="69c4f-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="69c4f-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="69c4f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

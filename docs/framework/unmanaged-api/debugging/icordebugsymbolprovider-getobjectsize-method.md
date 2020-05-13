---
title: Metodo ICorDebugSymbolProvider::GetObjectSize
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: 64324df49ad0b5dfa3c25455950bddc3d687b178
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379551"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="15ada-102">Metodo ICorDebugSymbolProvider::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="15ada-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="15ada-103">Restituisce le dimensioni dell'oggetto per un oggetto in base alla relativa firma typespec.</span><span class="sxs-lookup"><span data-stu-id="15ada-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15ada-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15ada-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15ada-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="15ada-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="15ada-106">[in] Numero di byte nella firma typespec.</span><span class="sxs-lookup"><span data-stu-id="15ada-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="15ada-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="15ada-107">typeSig</span></span>  
 <span data-ttu-id="15ada-108">[in] Firma typespec.</span><span class="sxs-lookup"><span data-stu-id="15ada-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="15ada-109">[out] Puntatore alla dimensione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="15ada-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15ada-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="15ada-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15ada-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="15ada-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15ada-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15ada-112">Requirements</span></span>  
 <span data-ttu-id="15ada-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15ada-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15ada-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15ada-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15ada-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15ada-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15ada-116">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15ada-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ada-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15ada-117">See also</span></span>

- [<span data-ttu-id="15ada-118">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="15ada-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="15ada-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="15ada-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

---
title: Metodo ICorDebugSymbolProvider::GetObjectSize
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: fce7410b5ae9571af0c8a5963596e2af41737798
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791575"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="8341d-102">Metodo ICorDebugSymbolProvider::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="8341d-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="8341d-103">Restituisce le dimensioni dell'oggetto per un oggetto in base alla relativa firma typespec.</span><span class="sxs-lookup"><span data-stu-id="8341d-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8341d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8341d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8341d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8341d-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="8341d-106">[in] Numero di byte nella firma typespec.</span><span class="sxs-lookup"><span data-stu-id="8341d-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="8341d-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="8341d-107">typeSig</span></span>  
 <span data-ttu-id="8341d-108">[in] Firma typespec.</span><span class="sxs-lookup"><span data-stu-id="8341d-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="8341d-109">[out] Puntatore alla dimensione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="8341d-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8341d-110">Note</span><span class="sxs-lookup"><span data-stu-id="8341d-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8341d-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8341d-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8341d-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="8341d-112">Requirements</span></span>  
 <span data-ttu-id="8341d-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8341d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8341d-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8341d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8341d-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8341d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8341d-116">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8341d-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8341d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8341d-117">See also</span></span>

- [<span data-ttu-id="8341d-118">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="8341d-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="8341d-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8341d-119">Debugging Interfaces</span></span>](debugging-interfaces.md)

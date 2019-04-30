---
title: 'Metodo icordebugsymbolprovider:: Gettypeprops'
ms.date: 03/30/2017
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5f9867dbdc244ed22948dbe9a07a7ea06292d6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994097"
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a><span data-ttu-id="d6f3a-102">Metodo icordebugsymbolprovider:: Gettypeprops</span><span class="sxs-lookup"><span data-stu-id="d6f3a-102">ICorDebugSymbolProvider::GetTypeProps Method</span></span>
<span data-ttu-id="d6f3a-103">Restituisce informazioni sulle proprietà di un tipo, ad esempio il numero di firma dei parametri generici, dato un indirizzo RVA (Relative Virtual Address) in un oggetto vtable.</span><span class="sxs-lookup"><span data-stu-id="d6f3a-103">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6f3a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6f3a-104">Syntax</span></span>  
  
```  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6f3a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6f3a-105">Parameters</span></span>  
 `tableRva`  
 <span data-ttu-id="d6f3a-106">[in] Indirizzo RVA (Relative Virtual Address) in un oggetto vtable</span><span class="sxs-lookup"><span data-stu-id="d6f3a-106">[in] A relative virtual address (RVA) in a vtable.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="d6f3a-107">[in] Dimensione della matrice `signature`.</span><span class="sxs-lookup"><span data-stu-id="d6f3a-107">[in] The size of the `signature` array.</span></span> <span data-ttu-id="d6f3a-108">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="d6f3a-108">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="d6f3a-109">[out] [out] Puntatore alla dimensione della matrice `signature` restituita.</span><span class="sxs-lookup"><span data-stu-id="d6f3a-109">[out] [out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="d6f3a-110">[out] Buffer contenente le firme typespec di tutti i parametri generici.</span><span class="sxs-lookup"><span data-stu-id="d6f3a-110">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6f3a-111">Note</span><span class="sxs-lookup"><span data-stu-id="d6f3a-111">Remarks</span></span>  
 <span data-ttu-id="d6f3a-112">Per ottenere la dimensione necessaria del tipo `signature` matrice, impostare il `cbSignature` argomento su 0 e `signature` al **null**.</span><span class="sxs-lookup"><span data-stu-id="d6f3a-112">To get the required size of the type's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="d6f3a-113">Quando il metodo viene restituito, `pcbSignature` conterrà il numero di byte necessari per la matrice `signature`.</span><span class="sxs-lookup"><span data-stu-id="d6f3a-113">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6f3a-114">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d6f3a-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6f3a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6f3a-115">Requirements</span></span>  
 <span data-ttu-id="d6f3a-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6f3a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6f3a-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6f3a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6f3a-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6f3a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6f3a-119">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6f3a-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f3a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6f3a-120">See also</span></span>

- [<span data-ttu-id="d6f3a-121">Metodo GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="d6f3a-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)
- [<span data-ttu-id="d6f3a-122">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="d6f3a-122">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="d6f3a-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d6f3a-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

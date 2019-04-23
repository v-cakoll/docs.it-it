---
title: Metodo ICorDebugSymbolProvider::GetMethodProps
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 784fcb10e9c0c3c6ff50c25d47bb4fb3fd5762ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59161109"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a><span data-ttu-id="87c46-102">Metodo ICorDebugSymbolProvider::GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="87c46-102">ICorDebugSymbolProvider::GetMethodProps Method</span></span>
<span data-ttu-id="87c46-103">Restituisce informazioni sulle proprietà del metodo, ad esempio il token di metadati del metodo e informazioni sui relativi parametri generici, da un indirizzo RVA (Relative Virtual Address) fornito in tale metodo.</span><span class="sxs-lookup"><span data-stu-id="87c46-103">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87c46-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87c46-104">Syntax</span></span>  
  
```  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87c46-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="87c46-105">Parameters</span></span>  
 `codeRVA`  
 <span data-ttu-id="87c46-106">[in] Indirizzo virtuale relativo del metodo sul quale recuperare informazioni.</span><span class="sxs-lookup"><span data-stu-id="87c46-106">[in] A relative virtual address in the method about which information is to be retrieved.</span></span>  
  
 `pMethodToken`  
 <span data-ttu-id="87c46-107">[out] Puntatore al token di metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="87c46-107">[out] A pointer to the method's metadata token.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="87c46-108">[out] Puntatore al numero di parametri generici associati al metodo.</span><span class="sxs-lookup"><span data-stu-id="87c46-108">[out] A pointer to the number of generic parameters associated with this method.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="87c46-109">[in] Dimensione della matrice `signature`.</span><span class="sxs-lookup"><span data-stu-id="87c46-109">[in] The size of the `signature` array.</span></span> <span data-ttu-id="87c46-110">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="87c46-110">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="87c46-111">[out] Puntatore alla dimensione della matrice `signature` restituita.</span><span class="sxs-lookup"><span data-stu-id="87c46-111">[out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="87c46-112">[out] Buffer contenente le firme typespec di tutti i parametri generici.</span><span class="sxs-lookup"><span data-stu-id="87c46-112">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87c46-113">Note</span><span class="sxs-lookup"><span data-stu-id="87c46-113">Remarks</span></span>  
 <span data-ttu-id="87c46-114">Per ottenere la dimensione necessaria del metodo `signature` matrice, impostare il `cbSignature` argomento su 0 e `signature` al **null**.</span><span class="sxs-lookup"><span data-stu-id="87c46-114">To get the required size of the method's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="87c46-115">Quando il metodo viene restituito, `pcbSignature` conterrà il numero di byte necessari per la matrice `signature`.</span><span class="sxs-lookup"><span data-stu-id="87c46-115">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87c46-116">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="87c46-116">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87c46-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87c46-117">Requirements</span></span>  
 <span data-ttu-id="87c46-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87c46-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87c46-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87c46-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87c46-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87c46-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87c46-121">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87c46-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c46-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87c46-122">See also</span></span>

- [<span data-ttu-id="87c46-123">Metodo GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="87c46-123">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)
- [<span data-ttu-id="87c46-124">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="87c46-124">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="87c46-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="87c46-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

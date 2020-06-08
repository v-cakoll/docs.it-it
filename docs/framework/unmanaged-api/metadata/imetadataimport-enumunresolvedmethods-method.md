---
title: Metodo IMetaDataImport::EnumUnresolvedMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
ms.openlocfilehash: c991c0af845bc6825db6b3bf258fe0809d5db804
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503696"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="d0fdd-102">Metodo IMetaDataImport::EnumUnresolvedMethods</span><span class="sxs-lookup"><span data-stu-id="d0fdd-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="d0fdd-103">Enumera i token MemberDef che rappresentano i metodi non risolti nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="d0fdd-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0fdd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0fdd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0fdd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d0fdd-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d0fdd-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="d0fdd-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d0fdd-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="d0fdd-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="d0fdd-108">out Matrice utilizzata per archiviare i token MemberDef.</span><span class="sxs-lookup"><span data-stu-id="d0fdd-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d0fdd-109">[in] Dimensione massima della matrice `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="d0fdd-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d0fdd-110">out Numero di token MemberDef restituiti in `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="d0fdd-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0fdd-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d0fdd-111">Return Value</span></span>  
  
|<span data-ttu-id="d0fdd-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0fdd-112">HRESULT</span></span>|<span data-ttu-id="d0fdd-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0fdd-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d0fdd-114">`EnumUnresolvedMethods`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="d0fdd-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d0fdd-115">Nessun token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="d0fdd-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="d0fdd-116">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="d0fdd-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0fdd-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d0fdd-117">Remarks</span></span>  
 <span data-ttu-id="d0fdd-118">Un metodo non risolto è uno che è stato dichiarato ma non implementato.</span><span class="sxs-lookup"><span data-stu-id="d0fdd-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="d0fdd-119">Un metodo è incluso nell'enumerazione se il metodo è contrassegnato `miForwardRef` e `mdPinvokeImpl` o `miRuntime` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="d0fdd-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="d0fdd-120">In altre parole, un metodo non risolto è un metodo della classe contrassegnato `miForwardRef` ma non implementato nel codice non gestito (raggiunto tramite PInvoke), né internamente dal runtime stesso</span><span class="sxs-lookup"><span data-stu-id="d0fdd-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="d0fdd-121">L'enumerazione esclude tutti i metodi definiti nell'ambito del modulo (Globals) o in interfacce o classi astratte.</span><span class="sxs-lookup"><span data-stu-id="d0fdd-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0fdd-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d0fdd-122">Requirements</span></span>  
 <span data-ttu-id="d0fdd-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0fdd-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0fdd-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d0fdd-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0fdd-125">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d0fdd-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d0fdd-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0fdd-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0fdd-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0fdd-127">See also</span></span>

- [<span data-ttu-id="d0fdd-128">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d0fdd-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d0fdd-129">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d0fdd-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

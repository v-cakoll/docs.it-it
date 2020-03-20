---
title: Metodo IMetaDataImport::EnumInterfaceImpls
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: b535fdd5027a26cc4dd0eafec9883f0186773dd1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175499"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="9c426-102">Metodo IMetaDataImport::EnumInterfaceImpls</span><span class="sxs-lookup"><span data-stu-id="9c426-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="9c426-103">Enumera tutte le interfacce `TypeDef`implementate dall'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="9c426-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="9c426-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c426-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c426-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9c426-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9c426-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="9c426-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="9c426-107">[in] Token del TypeDef i cui token MethodDef rappresentano le implementazioni dell'interfaccia devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="9c426-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="9c426-108">[fuori] Matrice utilizzata per archiviare i token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="9c426-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9c426-109">[in] Lunghezza massima della `rImpls` matrice.</span><span class="sxs-lookup"><span data-stu-id="9c426-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="9c426-110">[fuori] Numero effettivo di token restituiti in `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="9c426-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c426-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9c426-111">Return Value</span></span>  
  
|<span data-ttu-id="9c426-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9c426-112">HRESULT</span></span>|<span data-ttu-id="9c426-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c426-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9c426-114">`EnumInterfaceImpls`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="9c426-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9c426-115">Non sono presenti token MethodDef da enumerare.</span><span class="sxs-lookup"><span data-stu-id="9c426-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="9c426-116">In tal `pcImpls` caso, è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="9c426-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="9c426-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9c426-117">Remarks</span></span>

<span data-ttu-id="9c426-118">L'enumerazione restituisce una raccolta di `mdInterfaceImpl` token `TypeDef`per ogni interfaccia implementata dall'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="9c426-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="9c426-119">I token di interfaccia vengono restituiti nell'ordine `DefineTypeDef` `SetTypeDefProps`in cui sono state specificate le interfacce (tramite o ).</span><span class="sxs-lookup"><span data-stu-id="9c426-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="9c426-120">È possibile eseguire `mdInterfaceImpl` una query sulle proprietà dei token restituiti utilizzando [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="9c426-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="9c426-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9c426-121">Requirements</span></span>  
 <span data-ttu-id="9c426-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c426-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c426-123">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9c426-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9c426-124">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9c426-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9c426-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c426-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c426-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c426-126">See also</span></span>

- [<span data-ttu-id="9c426-127">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9c426-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9c426-128">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9c426-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

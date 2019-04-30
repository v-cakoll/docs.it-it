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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f6e4be2e05c573ec93cc23c8dd6eccc834b8b848
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992342"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="bf078-102">Metodo IMetaDataImport::EnumInterfaceImpls</span><span class="sxs-lookup"><span data-stu-id="bf078-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="bf078-103">Enumera tutte le interfacce implementate dall'oggetto specificato `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="bf078-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="bf078-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf078-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf078-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bf078-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="bf078-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="bf078-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="bf078-107">[in] Il token di TypeDef il cui token MethodDef che rappresentano le implementazioni di interfaccia devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="bf078-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="bf078-108">[out] Matrice utilizzata per archiviare i token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="bf078-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bf078-109">[in] Dimensione massima della matrice `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="bf078-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="bf078-110">[out] Il numero effettivo di token restituito nel `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="bf078-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf078-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bf078-111">Return Value</span></span>  
  
|<span data-ttu-id="bf078-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bf078-112">HRESULT</span></span>|<span data-ttu-id="bf078-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf078-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bf078-114">`EnumInterfaceImpls` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="bf078-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bf078-115">Non sono presenti token MethodDef per enumerare.</span><span class="sxs-lookup"><span data-stu-id="bf078-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="bf078-116">In tal caso, `pcImpls` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="bf078-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="bf078-117">Note</span><span class="sxs-lookup"><span data-stu-id="bf078-117">Remarks</span></span>

<span data-ttu-id="bf078-118">L'enumerazione restituisce una raccolta di `mdInterfaceImpl` i token per ogni interfaccia implementata dalla classe specificata `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="bf078-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="bf078-119">I token di interfaccia vengono restituiti nell'ordine le interfacce sono state specificate (tramite `DefineTypeDef` o `SetTypeDefProps`).</span><span class="sxs-lookup"><span data-stu-id="bf078-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="bf078-120">Proprietà del valore restituito `mdInterfaceImpl` token è possibile eseguire query usando [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="bf078-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="bf078-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf078-121">Requirements</span></span>  
 <span data-ttu-id="bf078-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf078-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf078-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bf078-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf078-124">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="bf078-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf078-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf078-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf078-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf078-126">See also</span></span>

- [<span data-ttu-id="bf078-127">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bf078-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bf078-128">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="bf078-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

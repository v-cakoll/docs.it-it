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
ms.openlocfilehash: 21d70b2702a754b554f06de5dad776ae98ae918d
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836266"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="c1890-102">Metodo IMetaDataImport::EnumInterfaceImpls</span><span class="sxs-lookup"><span data-stu-id="c1890-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="c1890-103">Enumera tutte le interfacce implementate dall'oggetto specificato `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="c1890-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="c1890-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1890-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1890-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c1890-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c1890-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="c1890-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="c1890-107">[in] Il token di TypeDef il cui token MethodDef che rappresentano le implementazioni di interfaccia devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="c1890-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="c1890-108">[out] Matrice utilizzata per archiviare i token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="c1890-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c1890-109">[in] Dimensione massima della matrice `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="c1890-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="c1890-110">[out] Il numero effettivo di token restituito nel `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="c1890-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1890-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c1890-111">Return Value</span></span>  
  
|<span data-ttu-id="c1890-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c1890-112">HRESULT</span></span>|<span data-ttu-id="c1890-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1890-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c1890-114">`EnumInterfaceImpls` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c1890-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c1890-115">Non sono presenti token MethodDef per enumerare.</span><span class="sxs-lookup"><span data-stu-id="c1890-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="c1890-116">In tal caso, `pcImpls` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="c1890-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="c1890-117">Note</span><span class="sxs-lookup"><span data-stu-id="c1890-117">Remarks</span></span>

<span data-ttu-id="c1890-118">L'enumerazione restituisce una raccolta di `mdInterfaceImpl` i token per ogni interfaccia implementata dalla classe specificata `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="c1890-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="c1890-119">I token di interfaccia vengono restituiti nell'ordine le interfacce sono state specificate (tramite `DefineTypeDef` o `SetTypeDefProps`).</span><span class="sxs-lookup"><span data-stu-id="c1890-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="c1890-120">Proprietà del valore restituito `mdInterfaceImpl` token è possibile eseguire query usando [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="c1890-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="c1890-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c1890-121">Requirements</span></span>  
 <span data-ttu-id="c1890-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1890-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1890-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c1890-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1890-124">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c1890-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1890-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1890-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1890-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1890-126">See also</span></span>
- [<span data-ttu-id="c1890-127">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c1890-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c1890-128">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c1890-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

---
title: Metodo IMetaDataImport::EnumTypeDefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53ed486a885514d02bf2be9c473e102c2c5f0e15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446843"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="5cc95-102">Metodo IMetaDataImport::EnumTypeDefs</span><span class="sxs-lookup"><span data-stu-id="5cc95-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="5cc95-103">Enumera i token TypeDef che rappresentano tutti i tipi all'interno dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="5cc95-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cc95-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5cc95-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5cc95-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5cc95-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5cc95-106">[out] Un puntatore per il nuovo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="5cc95-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="5cc95-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="5cc95-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="5cc95-108">[in] Matrice utilizzata per archiviare i token TypeDef.</span><span class="sxs-lookup"><span data-stu-id="5cc95-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5cc95-109">[in] Dimensione massima della matrice `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="5cc95-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="5cc95-110">[out] Il numero di token TypeDef restituiti in `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="5cc95-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5cc95-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5cc95-111">Return Value</span></span>  
  
|<span data-ttu-id="5cc95-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5cc95-112">HRESULT</span></span>|<span data-ttu-id="5cc95-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5cc95-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5cc95-114">`EnumTypeDefs` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5cc95-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5cc95-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="5cc95-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="5cc95-116">In tal caso, `pcTypeDefs` è zero.</span><span class="sxs-lookup"><span data-stu-id="5cc95-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cc95-117">Note</span><span class="sxs-lookup"><span data-stu-id="5cc95-117">Remarks</span></span>  
 <span data-ttu-id="5cc95-118">Il token TypeDef rappresenta un tipo, ad esempio una classe o un'interfaccia, come qualsiasi tipo aggiunto tramite un meccanismo di extensibility.</span><span class="sxs-lookup"><span data-stu-id="5cc95-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cc95-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5cc95-119">Requirements</span></span>  
 <span data-ttu-id="5cc95-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cc95-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cc95-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5cc95-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5cc95-122">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5cc95-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5cc95-123">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cc95-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cc95-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cc95-124">See Also</span></span>  
 [<span data-ttu-id="5cc95-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5cc95-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="5cc95-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5cc95-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

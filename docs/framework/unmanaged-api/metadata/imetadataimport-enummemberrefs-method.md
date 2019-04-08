---
title: Metodo IMetaDataImport::EnumMemberRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08577f15a6fab0e630d40032a23c273ee935faa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072993"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="f87ea-102">Metodo IMetaDataImport::EnumMemberRefs</span><span class="sxs-lookup"><span data-stu-id="f87ea-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="f87ea-103">Enumera i token MemberRef che rappresentano i membri del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="f87ea-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f87ea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f87ea-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f87ea-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f87ea-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f87ea-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="f87ea-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="f87ea-107">[in] Un token ModuleRef, TypeRef, MethodDef o TypeDef per il tipo i cui membri sono da enumerare.</span><span class="sxs-lookup"><span data-stu-id="f87ea-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="f87ea-108">[out] Matrice utilizzata per archiviare i token MemberRef.</span><span class="sxs-lookup"><span data-stu-id="f87ea-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f87ea-109">[in] Dimensione massima della matrice `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="f87ea-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f87ea-110">[out] Il numero effettivo di token MemberRef restituiti in `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="f87ea-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f87ea-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f87ea-111">Return Value</span></span>  
  
|<span data-ttu-id="f87ea-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f87ea-112">HRESULT</span></span>|<span data-ttu-id="f87ea-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f87ea-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumMemberRefs` <span data-ttu-id="f87ea-114">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f87ea-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f87ea-115">Non sono presenti token MemberRef per enumerare.</span><span class="sxs-lookup"><span data-stu-id="f87ea-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="f87ea-116">In tal caso, `pcTokens` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="f87ea-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f87ea-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f87ea-117">Requirements</span></span>  
 <span data-ttu-id="f87ea-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f87ea-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f87ea-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f87ea-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f87ea-120">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f87ea-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f87ea-121">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f87ea-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f87ea-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f87ea-122">See also</span></span>

- [<span data-ttu-id="f87ea-123">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f87ea-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f87ea-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f87ea-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

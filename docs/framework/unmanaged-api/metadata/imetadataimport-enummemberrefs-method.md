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
ms.openlocfilehash: 444c892026f9b6de12255ebdcda829db82c9bfdb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780450"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="4773a-102">Metodo IMetaDataImport::EnumMemberRefs</span><span class="sxs-lookup"><span data-stu-id="4773a-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="4773a-103">Enumera i token MemberRef che rappresentano i membri del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="4773a-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4773a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4773a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4773a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4773a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4773a-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="4773a-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="4773a-107">[in] Un token ModuleRef, TypeRef, MethodDef o TypeDef per il tipo i cui membri sono da enumerare.</span><span class="sxs-lookup"><span data-stu-id="4773a-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="4773a-108">[out] Matrice utilizzata per archiviare i token MemberRef.</span><span class="sxs-lookup"><span data-stu-id="4773a-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4773a-109">[in] Dimensione massima della matrice `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="4773a-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="4773a-110">[out] Il numero effettivo di token MemberRef restituiti in `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="4773a-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4773a-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4773a-111">Return Value</span></span>  
  
|<span data-ttu-id="4773a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4773a-112">HRESULT</span></span>|<span data-ttu-id="4773a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4773a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4773a-114">`EnumMemberRefs` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="4773a-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4773a-115">Non sono presenti token MemberRef per enumerare.</span><span class="sxs-lookup"><span data-stu-id="4773a-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="4773a-116">In tal caso, `pcTokens` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="4773a-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4773a-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4773a-117">Requirements</span></span>  
 <span data-ttu-id="4773a-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4773a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4773a-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4773a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4773a-120">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4773a-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4773a-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4773a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4773a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4773a-122">See also</span></span>

- [<span data-ttu-id="4773a-123">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4773a-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4773a-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4773a-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

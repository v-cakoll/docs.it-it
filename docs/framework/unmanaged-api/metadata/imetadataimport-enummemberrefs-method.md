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
ms.openlocfilehash: 68cdefe7ab362b26bbf060fa46766068eb0d7094
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503757"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="6c1dc-102">Metodo IMetaDataImport::EnumMemberRefs</span><span class="sxs-lookup"><span data-stu-id="6c1dc-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="6c1dc-103">Enumera i token MemberRef che rappresentano i membri del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="6c1dc-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c1dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c1dc-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c1dc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6c1dc-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6c1dc-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="6c1dc-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="6c1dc-107">in Un token TypeDef, TypeRef, MethodDef o ModuleRef per il tipo di cui è necessario enumerare i membri.</span><span class="sxs-lookup"><span data-stu-id="6c1dc-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="6c1dc-108">out Matrice utilizzata per archiviare i token MemberRef.</span><span class="sxs-lookup"><span data-stu-id="6c1dc-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6c1dc-109">[in] Dimensione massima della matrice `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="6c1dc-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6c1dc-110">out Numero effettivo di token MemberRef restituiti in `rMemberRefs` .</span><span class="sxs-lookup"><span data-stu-id="6c1dc-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c1dc-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6c1dc-111">Return Value</span></span>  
  
|<span data-ttu-id="6c1dc-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c1dc-112">HRESULT</span></span>|<span data-ttu-id="6c1dc-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c1dc-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6c1dc-114">`EnumMemberRefs`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="6c1dc-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6c1dc-115">Nessun token MemberRef da enumerare.</span><span class="sxs-lookup"><span data-stu-id="6c1dc-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="6c1dc-116">In tal caso, `pcTokens` è pari a zero.</span><span class="sxs-lookup"><span data-stu-id="6c1dc-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c1dc-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c1dc-117">Requirements</span></span>  
 <span data-ttu-id="6c1dc-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c1dc-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c1dc-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6c1dc-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c1dc-120">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6c1dc-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6c1dc-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c1dc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c1dc-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c1dc-122">See also</span></span>

- [<span data-ttu-id="6c1dc-123">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6c1dc-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6c1dc-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6c1dc-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

---
title: Metodo IMetaDataImport::FindTypeRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: acc006894f05536ed76bac60b0fde9277a460813
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199024"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="0ba06-102">Metodo IMetaDataImport::FindTypeRef</span><span class="sxs-lookup"><span data-stu-id="0ba06-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="0ba06-103">Ottiene un puntatore a TypeRef token per il <xref:System.Type> informazioni di riferimento che si trova nell'ambito specificato e con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="0ba06-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ba06-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ba06-104">Syntax</span></span>  
  
```  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ba06-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ba06-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="0ba06-106">[in] Un token ModuleRef, AssemblyRef o TypeRef che specifica il modulo, un assembly o un tipo, rispettivamente, in cui il tipo di riferimento è definito.</span><span class="sxs-lookup"><span data-stu-id="0ba06-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="0ba06-107">[in] Il nome del riferimento al tipo da cercare.</span><span class="sxs-lookup"><span data-stu-id="0ba06-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="0ba06-108">[out] Puntatore al token TypeRef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="0ba06-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ba06-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ba06-109">Requirements</span></span>  
 <span data-ttu-id="0ba06-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ba06-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ba06-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0ba06-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ba06-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0ba06-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="0ba06-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0ba06-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ba06-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ba06-114">See also</span></span>

- [<span data-ttu-id="0ba06-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0ba06-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0ba06-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0ba06-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

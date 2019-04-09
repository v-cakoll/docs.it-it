---
title: Metodo IMetaDataImport::GetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a482c7a06efe888408206f2de569e0a8739b85b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121511"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="48bd8-102">Metodo IMetaDataImport::GetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="48bd8-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="48bd8-103">Restituisce informazioni sui metadati per il <xref:System.Type> rappresentato dal token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="48bd8-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48bd8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48bd8-104">Syntax</span></span>  
  
```  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48bd8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="48bd8-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="48bd8-106">[in] Il token TypeDef che rappresenta il tipo da restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="48bd8-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="48bd8-107">[out] Un buffer contenente il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="48bd8-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="48bd8-108">[in] La dimensione in caratteri "wide" di `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="48bd8-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="48bd8-109">[out] Il numero di caratteri "wide", restituito nel `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="48bd8-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="48bd8-110">[out] Puntatore a un flag che modificano la definizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="48bd8-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="48bd8-111">Questo valore è una maschera di bit di [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="48bd8-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="48bd8-112">[out] Token di metadati TypeRef o (typedef) che rappresenta il tipo di base del tipo richiesto.</span><span class="sxs-lookup"><span data-stu-id="48bd8-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48bd8-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48bd8-113">Requirements</span></span>  
 <span data-ttu-id="48bd8-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48bd8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48bd8-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="48bd8-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48bd8-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="48bd8-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="48bd8-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="48bd8-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="48bd8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48bd8-118">See also</span></span>

- [<span data-ttu-id="48bd8-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="48bd8-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="48bd8-120">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="48bd8-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

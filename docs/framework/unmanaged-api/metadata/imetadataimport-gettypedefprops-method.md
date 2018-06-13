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
ms.openlocfilehash: aa69eda974187748d7046c792fa16b7729e3deff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446882"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="ef011-102">Metodo IMetaDataImport::GetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="ef011-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="ef011-103">Restituisce informazioni sui metadati per il <xref:System.Type> rappresentato dal token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="ef011-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef011-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef011-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="ef011-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef011-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ef011-106">[in] Il token TypeDef che rappresenta il tipo da restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="ef011-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="ef011-107">[out] Un buffer contenente il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="ef011-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="ef011-108">[in] La dimensione in caratteri "wide" di `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="ef011-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="ef011-109">[out] Il numero di caratteri "wide" restituiti in `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="ef011-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="ef011-110">[out] Puntatore a qualsiasi flag che modificano la definizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="ef011-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="ef011-111">Questo valore è una maschera di bit di [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ef011-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="ef011-112">[out] Token di metadati TypeDef o TypeRef che rappresenta il tipo di base del tipo richiesto.</span><span class="sxs-lookup"><span data-stu-id="ef011-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef011-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef011-113">Requirements</span></span>  
 <span data-ttu-id="ef011-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef011-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef011-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ef011-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef011-116">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ef011-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef011-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef011-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef011-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef011-118">See Also</span></span>  
 [<span data-ttu-id="ef011-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ef011-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ef011-120">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ef011-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

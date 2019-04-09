---
title: Metodo IMetaDataImport::FindTypeDefByName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5cd6b74ce2871cfafc0dc2260be3f758f6a28704
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168688"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="7adc8-102">Metodo IMetaDataImport::FindTypeDefByName</span><span class="sxs-lookup"><span data-stu-id="7adc8-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="7adc8-103">Ottiene un puntatore ai metadati TypeDef token per il <xref:System.Type> con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="7adc8-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7adc8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7adc8-104">Syntax</span></span>  
  
```  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7adc8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7adc8-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="7adc8-106">[in] Il nome del tipo per cui ottenere il token TypeDef.</span><span class="sxs-lookup"><span data-stu-id="7adc8-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="7adc8-107">[in] Token TypeRef o (typedef) che rappresenta la classe che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="7adc8-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="7adc8-108">Se il tipo da trovare non è una classe annidata, impostare questo valore su NULL.</span><span class="sxs-lookup"><span data-stu-id="7adc8-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="7adc8-109">[out] Puntatore al token TypeDef corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="7adc8-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7adc8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7adc8-110">Requirements</span></span>  
 <span data-ttu-id="7adc8-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7adc8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7adc8-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7adc8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7adc8-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7adc8-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="7adc8-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7adc8-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7adc8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7adc8-115">See also</span></span>

- [<span data-ttu-id="7adc8-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="7adc8-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7adc8-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="7adc8-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

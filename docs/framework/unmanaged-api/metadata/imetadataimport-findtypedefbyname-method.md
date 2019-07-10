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
ms.openlocfilehash: 7f182dad17e28cc5d19393bb4e13d747e34249fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782473"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="9e123-102">Metodo IMetaDataImport::FindTypeDefByName</span><span class="sxs-lookup"><span data-stu-id="9e123-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="9e123-103">Ottiene un puntatore ai metadati TypeDef token per il <xref:System.Type> con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="9e123-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e123-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e123-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e123-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9e123-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="9e123-106">[in] Il nome del tipo per cui ottenere il token TypeDef.</span><span class="sxs-lookup"><span data-stu-id="9e123-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="9e123-107">[in] Token TypeRef o (typedef) che rappresenta la classe che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="9e123-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="9e123-108">Se il tipo da trovare non è una classe annidata, impostare questo valore su NULL.</span><span class="sxs-lookup"><span data-stu-id="9e123-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="9e123-109">[out] Puntatore al token TypeDef corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="9e123-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e123-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e123-110">Requirements</span></span>  
 <span data-ttu-id="9e123-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e123-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e123-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9e123-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9e123-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9e123-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9e123-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e123-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e123-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e123-115">See also</span></span>

- [<span data-ttu-id="9e123-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9e123-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9e123-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9e123-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

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
ms.openlocfilehash: 2b4aad1cf1d3eb2dec249686f2897e6f393ab7e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445478"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="4bf77-102">Metodo IMetaDataImport::FindTypeDefByName</span><span class="sxs-lookup"><span data-stu-id="4bf77-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="4bf77-103">Ottiene un puntatore ai metadati TypeDef token per il <xref:System.Type> con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="4bf77-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bf77-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4bf77-104">Syntax</span></span>  
  
```  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4bf77-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4bf77-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="4bf77-106">[in] Il nome del tipo per il quale ottenere il token TypeDef.</span><span class="sxs-lookup"><span data-stu-id="4bf77-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="4bf77-107">[in] Token TypeDef o TypeRef che rappresenta la classe che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="4bf77-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="4bf77-108">Se il tipo da cercare non è una classe annidata, impostare questo valore su NULL.</span><span class="sxs-lookup"><span data-stu-id="4bf77-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="4bf77-109">[out] Puntatore al token TypeDef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="4bf77-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bf77-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4bf77-110">Requirements</span></span>  
 <span data-ttu-id="4bf77-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bf77-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bf77-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4bf77-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4bf77-113">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4bf77-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4bf77-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bf77-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf77-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bf77-115">See Also</span></span>  
 [<span data-ttu-id="4bf77-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4bf77-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="4bf77-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4bf77-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

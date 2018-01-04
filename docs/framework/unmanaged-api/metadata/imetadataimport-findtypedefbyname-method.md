---
title: Metodo IMetaDataImport::FindTypeDefByName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindTypeDefByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 036a177e807a2ab77a6afa74c7b811eeaaebfd29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="793b7-102">Metodo IMetaDataImport::FindTypeDefByName</span><span class="sxs-lookup"><span data-stu-id="793b7-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="793b7-103">Ottiene un puntatore ai metadati TypeDef token per il <xref:System.Type> con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="793b7-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="793b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="793b7-104">Syntax</span></span>  
  
```  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="793b7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="793b7-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="793b7-106">[in] Il nome del tipo per il quale ottenere il token TypeDef.</span><span class="sxs-lookup"><span data-stu-id="793b7-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="793b7-107">[in] Token TypeDef o TypeRef che rappresenta la classe che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="793b7-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="793b7-108">Se il tipo da cercare non è una classe annidata, impostare questo valore su NULL.</span><span class="sxs-lookup"><span data-stu-id="793b7-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="793b7-109">[out] Puntatore al token TypeDef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="793b7-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="793b7-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="793b7-110">Requirements</span></span>  
 <span data-ttu-id="793b7-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="793b7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="793b7-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="793b7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="793b7-113">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="793b7-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="793b7-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="793b7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="793b7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="793b7-115">See Also</span></span>  
 [<span data-ttu-id="793b7-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="793b7-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="793b7-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="793b7-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

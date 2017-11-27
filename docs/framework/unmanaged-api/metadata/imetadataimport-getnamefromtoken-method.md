---
title: Metodo IMetaDataImport::GetNameFromToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetNameFromToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e77954d5730417a005c6c1ac07fa171bd0f1b13a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="5c566-102">Metodo IMetaDataImport::GetNameFromToken</span><span class="sxs-lookup"><span data-stu-id="5c566-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="5c566-103">Ottiene il nome in formato UTF-8 dell'oggetto a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="5c566-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="5c566-104">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="5c566-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c566-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c566-105">Syntax</span></span>  
  
```  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c566-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c566-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="5c566-107">[in] Che rappresenta l'oggetto per restituire il nome per il token.</span><span class="sxs-lookup"><span data-stu-id="5c566-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="5c566-108">[out] Un puntatore per il nome dell'oggetto nell'heap UTF-8.</span><span class="sxs-lookup"><span data-stu-id="5c566-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c566-109">Note</span><span class="sxs-lookup"><span data-stu-id="5c566-109">Remarks</span></span>  
 <span data-ttu-id="5c566-110">`GetNameFromToken` è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="5c566-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="5c566-111">In alternativa, chiamare un metodo per ottenere le proprietà di quel determinato tipo di token richiesto, ad esempio `GetFieldProps` per un campo o `GetMethodProps` per un metodo.</span><span class="sxs-lookup"><span data-stu-id="5c566-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c566-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c566-112">Requirements</span></span>  
 <span data-ttu-id="5c566-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c566-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c566-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5c566-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c566-115">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c566-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c566-116">**Versioni di .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="5c566-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c566-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c566-117">See Also</span></span>  
 [<span data-ttu-id="5c566-118">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5c566-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="5c566-119">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5c566-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

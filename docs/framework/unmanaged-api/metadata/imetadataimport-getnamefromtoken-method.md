---
title: Metodo IMetaDataImport::GetNameFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d77891478c9136a18dc4c9c44beed805244dd1a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225937"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="5f41f-102">Metodo IMetaDataImport::GetNameFromToken</span><span class="sxs-lookup"><span data-stu-id="5f41f-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="5f41f-103">Ottiene il nome in formato UTF-8 dell'oggetto a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="5f41f-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="5f41f-104">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="5f41f-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f41f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f41f-105">Syntax</span></span>  
  
```  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f41f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f41f-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="5f41f-107">[in] Che rappresenta l'oggetto per restituire il nome per il token.</span><span class="sxs-lookup"><span data-stu-id="5f41f-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="5f41f-108">[out] Puntatore al nome dell'oggetto UTF-8 nell'heap.</span><span class="sxs-lookup"><span data-stu-id="5f41f-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f41f-109">Note</span><span class="sxs-lookup"><span data-stu-id="5f41f-109">Remarks</span></span>  
 `GetNameFromToken` <span data-ttu-id="5f41f-110">è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="5f41f-110">is obsolete.</span></span> <span data-ttu-id="5f41f-111">In alternativa, chiamare un metodo per ottenere le proprietà del tipo di token richiesto, come determinato `GetFieldProps` per un campo o `GetMethodProps` per un metodo.</span><span class="sxs-lookup"><span data-stu-id="5f41f-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f41f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f41f-112">Requirements</span></span>  
 <span data-ttu-id="5f41f-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f41f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f41f-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5f41f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f41f-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5f41f-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f41f-116">**Versioni di .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="5f41f-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f41f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f41f-117">See also</span></span>

- [<span data-ttu-id="5f41f-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5f41f-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5f41f-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5f41f-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

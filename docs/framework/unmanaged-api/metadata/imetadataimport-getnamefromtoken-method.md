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
ms.openlocfilehash: 6d62739148280c7333cf7cdb6002b59a145496e3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503562"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="0c5b3-102">Metodo IMetaDataImport::GetNameFromToken</span><span class="sxs-lookup"><span data-stu-id="0c5b3-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="0c5b3-103">Ottiene il nome in formato UTF-8 dell'oggetto a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="0c5b3-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="0c5b3-104">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="0c5b3-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c5b3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c5b3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c5b3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c5b3-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="0c5b3-107">in Token che rappresenta l'oggetto per il quale restituire il nome.</span><span class="sxs-lookup"><span data-stu-id="0c5b3-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="0c5b3-108">out Puntatore al nome dell'oggetto UTF-8 nell'heap.</span><span class="sxs-lookup"><span data-stu-id="0c5b3-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c5b3-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0c5b3-109">Remarks</span></span>  
 <span data-ttu-id="0c5b3-110">`GetNameFromToken` è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="0c5b3-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="0c5b3-111">In alternativa, chiamare un metodo per ottenere le proprietà del tipo specifico di token necessario, ad esempio `GetFieldProps` per un campo o `GetMethodProps` per un metodo.</span><span class="sxs-lookup"><span data-stu-id="0c5b3-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c5b3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c5b3-112">Requirements</span></span>  
 <span data-ttu-id="0c5b3-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c5b3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c5b3-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0c5b3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c5b3-115">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0c5b3-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c5b3-116">**Versioni .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="0c5b3-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c5b3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c5b3-117">See also</span></span>

- [<span data-ttu-id="0c5b3-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0c5b3-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="0c5b3-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0c5b3-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

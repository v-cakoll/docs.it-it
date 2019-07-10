---
title: Metodo IMetaDataImport::GetRVA
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d305aa59c1b9e9e1225b30f12e36fc689d584db1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778894"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="5f65d-102">Metodo IMetaDataImport::GetRVA</span><span class="sxs-lookup"><span data-stu-id="5f65d-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="5f65d-103">Ottiene l'indirizzo virtuale relativo (RVA) e i flag di implementazione del metodo o del campo rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="5f65d-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f65d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f65d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f65d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f65d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="5f65d-106">[in] Un token MethodDef o FieldDef metadati che rappresenta l'oggetto di codice per restituire il RVA per.</span><span class="sxs-lookup"><span data-stu-id="5f65d-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="5f65d-107">Se il token FieldDef, il campo deve essere una variabile globale.</span><span class="sxs-lookup"><span data-stu-id="5f65d-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="5f65d-108">[out] Un puntatore all'indirizzo virtuale relativo dell'oggetto codice rappresentato dal token.</span><span class="sxs-lookup"><span data-stu-id="5f65d-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="5f65d-109">[out] Puntatore ai flag di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="5f65d-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="5f65d-110">Questo valore è una maschera di bit di [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5f65d-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="5f65d-111">Il valore di `pdwImplFlags` è valido solo se `tk` è un token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="5f65d-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f65d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f65d-112">Requirements</span></span>  
 <span data-ttu-id="5f65d-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f65d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f65d-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5f65d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f65d-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5f65d-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f65d-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f65d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f65d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f65d-117">See also</span></span>

- [<span data-ttu-id="5f65d-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5f65d-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5f65d-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5f65d-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

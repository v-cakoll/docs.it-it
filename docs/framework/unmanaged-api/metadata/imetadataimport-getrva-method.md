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
ms.openlocfilehash: 190bcacc84646cfd9294cf2b6b53b0474f38758f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177212"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="c7da6-102">Metodo IMetaDataImport::GetRVA</span><span class="sxs-lookup"><span data-stu-id="c7da6-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="c7da6-103">Ottiene l'indirizzo virtuale relativo (RVA) e i flag di implementazione del metodo o del campo rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="c7da6-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7da6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7da6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7da6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c7da6-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c7da6-106">[in] Token di metadati MethodDef o FieldDef che rappresenta l'oggetto codice per cui restituire l'RVA.</span><span class="sxs-lookup"><span data-stu-id="c7da6-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="c7da6-107">Se il token è un FieldDef, il campo deve essere una variabile globale.</span><span class="sxs-lookup"><span data-stu-id="c7da6-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="c7da6-108">[fuori] Puntatore all'indirizzo virtuale relativo dell'oggetto codice rappresentato dal token.</span><span class="sxs-lookup"><span data-stu-id="c7da6-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="c7da6-109">[fuori] Puntatore ai flag di implementazione per il metodo.</span><span class="sxs-lookup"><span data-stu-id="c7da6-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="c7da6-110">Questo valore è una maschera di bit dall'enumerazione [CorMethodImpl.](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="c7da6-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="c7da6-111">Il valore `pdwImplFlags` di è `tk` valido solo se è un token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="c7da6-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7da6-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7da6-112">Requirements</span></span>  
 <span data-ttu-id="c7da6-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7da6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7da6-114">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c7da6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c7da6-115">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c7da6-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c7da6-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7da6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7da6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7da6-117">See also</span></span>

- [<span data-ttu-id="c7da6-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c7da6-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c7da6-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c7da6-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

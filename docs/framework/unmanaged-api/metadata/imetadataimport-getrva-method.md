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
ms.openlocfilehash: a3a5cadc1b5a9df7967aae271ff10296843121dd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436951"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="98557-102">Metodo IMetaDataImport::GetRVA</span><span class="sxs-lookup"><span data-stu-id="98557-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="98557-103">Ottiene l'indirizzo RVA (relative Virtual Address) e i flag di implementazione del metodo o del campo rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="98557-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98557-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98557-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98557-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="98557-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="98557-106">in Token di metadati MethodDef o FieldDef che rappresenta l'oggetto di codice per il quale restituire l'RVA.</span><span class="sxs-lookup"><span data-stu-id="98557-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="98557-107">Se il token è un FieldDef, il campo deve essere una variabile globale.</span><span class="sxs-lookup"><span data-stu-id="98557-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="98557-108">out Puntatore all'indirizzo virtuale relativo dell'oggetto di codice rappresentato dal token.</span><span class="sxs-lookup"><span data-stu-id="98557-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="98557-109">out Puntatore ai flag di implementazione per il metodo.</span><span class="sxs-lookup"><span data-stu-id="98557-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="98557-110">Questo valore è una maschera di maschera dall'enumerazione [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="98557-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="98557-111">Il valore di `pdwImplFlags` è valido solo se `tk` è un token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="98557-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98557-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="98557-112">Requirements</span></span>  
 <span data-ttu-id="98557-113">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98557-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98557-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="98557-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="98557-115">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="98557-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="98557-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98557-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98557-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98557-117">See also</span></span>

- [<span data-ttu-id="98557-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="98557-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="98557-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="98557-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

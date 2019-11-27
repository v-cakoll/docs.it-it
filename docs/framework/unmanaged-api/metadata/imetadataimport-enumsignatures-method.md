---
title: Metodo IMetaDataImport::EnumSignatures
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
ms.openlocfilehash: 9dbbdcc9d0fb9f0a8d2a64edfa4a0ad92570933c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450011"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="ffab9-102">Metodo IMetaDataImport::EnumSignatures</span><span class="sxs-lookup"><span data-stu-id="ffab9-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="ffab9-103">Enumera i token Signature che rappresentano le firme autonome nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="ffab9-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffab9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ffab9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffab9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ffab9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ffab9-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="ffab9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ffab9-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="ffab9-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="ffab9-108">out Matrice utilizzata per archiviare i token della firma.</span><span class="sxs-lookup"><span data-stu-id="ffab9-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ffab9-109">[in] Dimensione massima della matrice `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="ffab9-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="ffab9-110">out Numero di token di firma restituiti in `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="ffab9-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ffab9-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ffab9-111">Return Value</span></span>  
  
|<span data-ttu-id="ffab9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ffab9-112">HRESULT</span></span>|<span data-ttu-id="ffab9-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ffab9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ffab9-114">`EnumSignatures` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ffab9-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ffab9-115">Nessun token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="ffab9-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="ffab9-116">In tal caso, `pcSignatures` è zero.</span><span class="sxs-lookup"><span data-stu-id="ffab9-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffab9-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ffab9-117">Remarks</span></span>  
 <span data-ttu-id="ffab9-118">I token di firma vengono creati dal metodo [IMetaDataEmit:: GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ffab9-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffab9-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ffab9-119">Requirements</span></span>  
 <span data-ttu-id="ffab9-120">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffab9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffab9-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ffab9-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ffab9-122">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ffab9-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ffab9-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffab9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffab9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffab9-124">See also</span></span>

- [<span data-ttu-id="ffab9-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ffab9-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ffab9-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ffab9-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

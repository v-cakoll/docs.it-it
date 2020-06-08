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
ms.openlocfilehash: 652ebf1be6a58e08da27aaed5b2e84a8f2aee98a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503770"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="ba612-102">Metodo IMetaDataImport::EnumSignatures</span><span class="sxs-lookup"><span data-stu-id="ba612-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="ba612-103">Enumera i token Signature che rappresentano le firme autonome nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="ba612-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba612-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba612-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba612-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba612-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ba612-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="ba612-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ba612-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="ba612-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="ba612-108">out Matrice utilizzata per archiviare i token della firma.</span><span class="sxs-lookup"><span data-stu-id="ba612-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ba612-109">[in] Dimensione massima della matrice `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="ba612-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="ba612-110">out Numero di token di firma restituiti in `rSignatures` .</span><span class="sxs-lookup"><span data-stu-id="ba612-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba612-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ba612-111">Return Value</span></span>  
  
|<span data-ttu-id="ba612-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba612-112">HRESULT</span></span>|<span data-ttu-id="ba612-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba612-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ba612-114">`EnumSignatures`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ba612-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ba612-115">Nessun token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="ba612-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="ba612-116">In tal caso, `pcSignatures` è zero.</span><span class="sxs-lookup"><span data-stu-id="ba612-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba612-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ba612-117">Remarks</span></span>  
 <span data-ttu-id="ba612-118">I token di firma vengono creati dal metodo [IMetaDataEmit:: GetTokenFromSig](imetadataemit-gettokenfromsig-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ba612-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba612-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba612-119">Requirements</span></span>  
 <span data-ttu-id="ba612-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba612-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba612-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ba612-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba612-122">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ba612-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba612-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba612-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba612-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba612-124">See also</span></span>

- [<span data-ttu-id="ba612-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ba612-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ba612-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ba612-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

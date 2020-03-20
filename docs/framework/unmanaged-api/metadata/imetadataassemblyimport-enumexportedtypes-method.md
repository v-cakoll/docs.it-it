---
title: Metodo IMetaDataAssemblyImport::EnumExportedTypes
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: f00fe5bce2f808265add228406dfaa2ccc267545
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176006"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="ef1aa-102">Metodo IMetaDataAssemblyImport::EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="ef1aa-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="ef1aa-103">Enumera i tipi esportati a cui viene fatto riferimento nel manifesto dell'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="ef1aa-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef1aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef1aa-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef1aa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef1aa-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ef1aa-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="ef1aa-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ef1aa-107">Deve essere un valore `EnumExportedTypes` null quando il metodo viene chiamato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="ef1aa-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="ef1aa-108">[fuori] Enumerazione `mdExportedType` dei token di metadati.</span><span class="sxs-lookup"><span data-stu-id="ef1aa-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ef1aa-109">[in] Numero massimo `mdExportedType` di token che possono `rExportedTypes` essere inseriti nella matrice.</span><span class="sxs-lookup"><span data-stu-id="ef1aa-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ef1aa-110">[fuori] Il numero `mdExportedType` di token `rExportedTypes`effettivamente inseriti in .</span><span class="sxs-lookup"><span data-stu-id="ef1aa-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef1aa-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ef1aa-111">Return Value</span></span>  
  
|<span data-ttu-id="ef1aa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef1aa-112">HRESULT</span></span>|<span data-ttu-id="ef1aa-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef1aa-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ef1aa-114">`EnumExportedTypes`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="ef1aa-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ef1aa-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="ef1aa-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="ef1aa-116">In questo `pcTokens` caso, è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="ef1aa-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ef1aa-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef1aa-117">Requirements</span></span>  
 <span data-ttu-id="ef1aa-118">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef1aa-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef1aa-119">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ef1aa-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef1aa-120">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef1aa-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef1aa-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef1aa-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef1aa-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef1aa-122">See also</span></span>

- [<span data-ttu-id="ef1aa-123">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="ef1aa-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

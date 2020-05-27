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
ms.openlocfilehash: 514488c6e0d2e89de0d8ee483def485ec9f3ef25
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009106"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="3a74b-102">Metodo IMetaDataAssemblyImport::EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="3a74b-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="3a74b-103">Enumera i tipi esportati a cui si fa riferimento nel manifesto dell'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="3a74b-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a74b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a74b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a74b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3a74b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3a74b-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="3a74b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3a74b-107">Deve essere un valore null quando il `EnumExportedTypes` metodo viene chiamato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="3a74b-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="3a74b-108">out Enumerazione dei `mdExportedType` token di metadati.</span><span class="sxs-lookup"><span data-stu-id="3a74b-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3a74b-109">in Numero massimo di `mdExportedType` token che è possibile inserire nella `rExportedTypes` matrice.</span><span class="sxs-lookup"><span data-stu-id="3a74b-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3a74b-110">out Numero di `mdExportedType` token effettivamente inseriti in `rExportedTypes` .</span><span class="sxs-lookup"><span data-stu-id="3a74b-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a74b-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3a74b-111">Return Value</span></span>  
  
|<span data-ttu-id="3a74b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a74b-112">HRESULT</span></span>|<span data-ttu-id="3a74b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a74b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3a74b-114">`EnumExportedTypes`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="3a74b-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3a74b-115">Nessun token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="3a74b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="3a74b-116">In questo caso, `pcTokens` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="3a74b-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3a74b-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a74b-117">Requirements</span></span>  
 <span data-ttu-id="3a74b-118">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a74b-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a74b-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3a74b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a74b-120">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3a74b-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a74b-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a74b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a74b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a74b-122">See also</span></span>

- [<span data-ttu-id="3a74b-123">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="3a74b-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)

---
title: Metodo IMetaDataAssemblyImport::EnumFiles
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
ms.openlocfilehash: 70f76318f51047cb81262f744a6fbed5fe401692
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177807"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="88b23-102">Metodo IMetaDataAssemblyImport::EnumFiles</span><span class="sxs-lookup"><span data-stu-id="88b23-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="88b23-103">Enumera i file a cui viene fatto riferimento nel manifesto dell'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="88b23-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88b23-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="88b23-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,
    [out] mdFile          rFiles[],
    [in]  ULONG           cMax,
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88b23-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="88b23-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="88b23-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="88b23-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="88b23-107">Deve essere un valore null per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="88b23-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="88b23-108">[fuori] Matrice utilizzata per `mdFile` archiviare i token di metadati.</span><span class="sxs-lookup"><span data-stu-id="88b23-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="88b23-109">[in] Numero massimo `mdFile` di token che possono `rFiles`essere inseriti in .</span><span class="sxs-lookup"><span data-stu-id="88b23-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="88b23-110">[fuori] Il numero `mdFile` di token `rFiles`effettivamente inseriti in .</span><span class="sxs-lookup"><span data-stu-id="88b23-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88b23-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="88b23-111">Return Value</span></span>  
  
|<span data-ttu-id="88b23-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="88b23-112">HRESULT</span></span>|<span data-ttu-id="88b23-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88b23-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="88b23-114">`EnumFiles`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="88b23-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="88b23-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="88b23-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="88b23-116">In questo `pcTokens` caso, è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="88b23-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88b23-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="88b23-117">Requirements</span></span>  
 <span data-ttu-id="88b23-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88b23-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88b23-119">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="88b23-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="88b23-120">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="88b23-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="88b23-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88b23-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88b23-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88b23-122">See also</span></span>

- [<span data-ttu-id="88b23-123">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="88b23-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

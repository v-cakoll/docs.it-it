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
ms.openlocfilehash: e4549789ea1af584c0850a535d9f6bb54f844ce0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443554"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="d29be-102">Metodo IMetaDataAssemblyImport::EnumFiles</span><span class="sxs-lookup"><span data-stu-id="d29be-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="d29be-103">Enumera i file a cui si fa riferimento nel manifesto dell'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="d29be-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d29be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d29be-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d29be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d29be-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d29be-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="d29be-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d29be-107">Deve essere un valore null per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="d29be-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="d29be-108">out Matrice utilizzata per archiviare i token di metadati del `mdFile`.</span><span class="sxs-lookup"><span data-stu-id="d29be-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d29be-109">in Numero massimo di token di `mdFile` che possono essere inseriti nel `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="d29be-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d29be-110">out Il numero di token `mdFile` effettivamente inseriti in `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="d29be-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d29be-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d29be-111">Return Value</span></span>  
  
|<span data-ttu-id="d29be-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d29be-112">HRESULT</span></span>|<span data-ttu-id="d29be-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d29be-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d29be-114">`EnumFiles` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d29be-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d29be-115">Nessun token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="d29be-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="d29be-116">In questo caso, `pcTokens` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="d29be-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d29be-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d29be-117">Requirements</span></span>  
 <span data-ttu-id="d29be-118">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d29be-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d29be-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d29be-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d29be-120">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d29be-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d29be-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d29be-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d29be-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d29be-122">See also</span></span>

- [<span data-ttu-id="d29be-123">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="d29be-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

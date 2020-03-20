---
title: Metodo IMetaDataAssemblyEmit::DefineFile
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
ms.openlocfilehash: cabd6a47e5d6fc2a4cea87b16d349d9c778b3507
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176058"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="5f4df-102">Metodo IMetaDataAssemblyEmit::DefineFile</span><span class="sxs-lookup"><span data-stu-id="5f4df-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="5f4df-103">Crea una struttura dei metadati `File` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="5f4df-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f4df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f4df-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f4df-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f4df-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="5f4df-106">[in] Nome del file da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5f4df-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="5f4df-107">[in] Puntatore ai dati hash associati all'assembly.</span><span class="sxs-lookup"><span data-stu-id="5f4df-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="5f4df-108">[in] Dimensione in byte `pbHashValue`di .</span><span class="sxs-lookup"><span data-stu-id="5f4df-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="5f4df-109">[in] Combinazione bit per `FileFlags` bit di valori che specificano le impostazioni delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="5f4df-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="5f4df-110">[fuori] Puntatore al token `File` restituito.</span><span class="sxs-lookup"><span data-stu-id="5f4df-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f4df-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5f4df-111">Remarks</span></span>  
 <span data-ttu-id="5f4df-112">È `File` necessario definire una struttura di metadati per ogni file che faceva parte di questo assembly al momento della compilazione dell'assembly, escluso il file che contiene i metadati.</span><span class="sxs-lookup"><span data-stu-id="5f4df-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f4df-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f4df-113">Requirements</span></span>  
 <span data-ttu-id="5f4df-114">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f4df-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f4df-115">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5f4df-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f4df-116">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f4df-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f4df-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f4df-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f4df-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f4df-118">See also</span></span>

- [<span data-ttu-id="5f4df-119">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="5f4df-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5693da3b5e6d883efd9ad8a5a409a5dba8dd8b6e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203431"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="44286-102">Metodo IMetaDataAssemblyEmit::DefineFile</span><span class="sxs-lookup"><span data-stu-id="44286-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="44286-103">Crea una struttura dei metadati `File` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="44286-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44286-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44286-104">Syntax</span></span>  
  
```  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44286-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="44286-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="44286-106">[in] Il nome del file devono essere usati.</span><span class="sxs-lookup"><span data-stu-id="44286-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="44286-107">[in] Un puntatore per il valore hash dei dati associati all'assembly.</span><span class="sxs-lookup"><span data-stu-id="44286-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="44286-108">[in] La dimensione in byte di `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="44286-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="44286-109">[in] Una combinazione bit per bit di `FileFlags` valori che specificano le impostazioni delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="44286-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="44286-110">[out] Un puntatore all'oggetto restituito `File` token.</span><span class="sxs-lookup"><span data-stu-id="44286-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44286-111">Note</span><span class="sxs-lookup"><span data-stu-id="44286-111">Remarks</span></span>  
 <span data-ttu-id="44286-112">Uno `File` struttura dei metadati deve essere definito per ogni file che faceva parte di questo assembly nel momento in cui questo assembly è stato compilato, escluso il file che contiene i metadati.</span><span class="sxs-lookup"><span data-stu-id="44286-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44286-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="44286-113">Requirements</span></span>  
 <span data-ttu-id="44286-114">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44286-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44286-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="44286-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44286-116">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="44286-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="44286-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="44286-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="44286-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44286-118">See also</span></span>

- [<span data-ttu-id="44286-119">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="44286-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

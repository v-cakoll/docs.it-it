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
ms.openlocfilehash: 61d81c94e3a9c092b5d45791962635c761e8da8a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008144"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="d1acc-102">Metodo IMetaDataAssemblyEmit::DefineFile</span><span class="sxs-lookup"><span data-stu-id="d1acc-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="d1acc-103">Crea una struttura dei metadati `File` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="d1acc-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1acc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1acc-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1acc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d1acc-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="d1acc-106">in Nome del file da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="d1acc-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="d1acc-107">in Puntatore ai dati hash associati all'assembly.</span><span class="sxs-lookup"><span data-stu-id="d1acc-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="d1acc-108">in Dimensioni in byte di `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="d1acc-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="d1acc-109">in Combinazione bit per bit di `FileFlags` valori che specificano le impostazioni delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="d1acc-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="d1acc-110">out Puntatore al `File` token restituito.</span><span class="sxs-lookup"><span data-stu-id="d1acc-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1acc-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="d1acc-111">Remarks</span></span>  
 <span data-ttu-id="d1acc-112">È `File` necessario definire una struttura di metadati per ogni file che faceva parte di questo assembly nel momento in cui l'assembly è stato compilato, escluso il file contenente i metadati.</span><span class="sxs-lookup"><span data-stu-id="d1acc-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1acc-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d1acc-113">Requirements</span></span>  
 <span data-ttu-id="d1acc-114">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1acc-114">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1acc-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d1acc-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d1acc-116">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d1acc-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d1acc-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1acc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1acc-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1acc-118">See also</span></span>

- [<span data-ttu-id="d1acc-119">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="d1acc-119">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)

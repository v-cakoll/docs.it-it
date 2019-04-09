---
title: Metodo IMetaDataAssemblyEmit::SetFileProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd0c2da234fa89bbf92c2117d6428d64502da0c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208176"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="af767-102">Metodo IMetaDataAssemblyEmit::SetFileProps</span><span class="sxs-lookup"><span data-stu-id="af767-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="af767-103">Modifica la struttura dei metadati `File` specificata.</span><span class="sxs-lookup"><span data-stu-id="af767-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af767-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af767-104">Syntax</span></span>  
  
```  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af767-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="af767-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="af767-106">[in] Il token di metadati che specifica il `File` modifica della struttura dei metadati.</span><span class="sxs-lookup"><span data-stu-id="af767-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="af767-107">[in] Un puntatore per il valore hash dei dati associato al file.</span><span class="sxs-lookup"><span data-stu-id="af767-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="af767-108">[in] La dimensione in byte di `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="af767-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="af767-109">[in] Una combinazione bit per bit di [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) valori che specificano vari attributi del file.</span><span class="sxs-lookup"><span data-stu-id="af767-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af767-110">Note</span><span class="sxs-lookup"><span data-stu-id="af767-110">Remarks</span></span>  
 <span data-ttu-id="af767-111">Per creare un `File` struttura dei metadati, usare il [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="af767-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af767-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af767-112">Requirements</span></span>  
 <span data-ttu-id="af767-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af767-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af767-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="af767-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af767-115">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="af767-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="af767-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="af767-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="af767-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af767-117">See also</span></span>

- [<span data-ttu-id="af767-118">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="af767-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

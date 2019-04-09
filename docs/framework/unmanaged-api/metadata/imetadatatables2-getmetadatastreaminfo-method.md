---
title: Metodo IMetaDataTables2::GetMetaDataStreamInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f70187ba9bd71225162e6e10184e4992b5600f5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228848"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="ea29b-102">Metodo IMetaDataTables2::GetMetaDataStreamInfo</span><span class="sxs-lookup"><span data-stu-id="ea29b-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="ea29b-103">Ottiene il nome, dimensioni e contenuto del flusso di metadati in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="ea29b-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea29b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea29b-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea29b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea29b-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="ea29b-106">[in] L'indice del flusso di richiesta dei metadati.</span><span class="sxs-lookup"><span data-stu-id="ea29b-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="ea29b-107">[out] Un puntatore al nome del flusso.</span><span class="sxs-lookup"><span data-stu-id="ea29b-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="ea29b-108">[out] Un puntatore al flusso di metadati.</span><span class="sxs-lookup"><span data-stu-id="ea29b-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="ea29b-109">[out] Le dimensioni, in byte, di `ppv`.</span><span class="sxs-lookup"><span data-stu-id="ea29b-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea29b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea29b-110">Requirements</span></span>  
 <span data-ttu-id="ea29b-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea29b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea29b-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ea29b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea29b-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ea29b-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="ea29b-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ea29b-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ea29b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea29b-115">See also</span></span>

- [<span data-ttu-id="ea29b-116">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="ea29b-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="ea29b-117">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="ea29b-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)

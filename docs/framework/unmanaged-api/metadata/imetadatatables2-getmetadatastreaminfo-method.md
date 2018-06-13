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
ms.openlocfilehash: 756b0ff726c31bf096a1c1b70004c3ff82fe9979
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450037"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="227e1-102">Metodo IMetaDataTables2::GetMetaDataStreamInfo</span><span class="sxs-lookup"><span data-stu-id="227e1-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="227e1-103">Ottiene il nome, dimensioni e contenuto del flusso di metadati in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="227e1-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="227e1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="227e1-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="227e1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="227e1-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="227e1-106">[in] L'indice del flusso di richiesta dei metadati.</span><span class="sxs-lookup"><span data-stu-id="227e1-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="227e1-107">[out] Un puntatore al nome del flusso.</span><span class="sxs-lookup"><span data-stu-id="227e1-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="227e1-108">[out] Puntatore al flusso di metadati.</span><span class="sxs-lookup"><span data-stu-id="227e1-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="227e1-109">[out] Le dimensioni, in byte, di `ppv`.</span><span class="sxs-lookup"><span data-stu-id="227e1-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="227e1-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="227e1-110">Requirements</span></span>  
 <span data-ttu-id="227e1-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="227e1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="227e1-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="227e1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="227e1-113">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="227e1-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="227e1-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="227e1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="227e1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="227e1-115">See Also</span></span>  
 [<span data-ttu-id="227e1-116">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="227e1-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 [<span data-ttu-id="227e1-117">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="227e1-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)

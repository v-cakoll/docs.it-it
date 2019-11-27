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
ms.openlocfilehash: 279e34689169d31ad89772e90155e7f50bdbac08
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426225"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="438d3-102">Metodo IMetaDataTables2::GetMetaDataStreamInfo</span><span class="sxs-lookup"><span data-stu-id="438d3-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="438d3-103">Ottiene il nome, le dimensioni e il contenuto del flusso di metadati in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="438d3-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="438d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="438d3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="438d3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="438d3-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="438d3-106">in Indice del flusso di metadati richiesto.</span><span class="sxs-lookup"><span data-stu-id="438d3-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="438d3-107">out Puntatore al nome del flusso.</span><span class="sxs-lookup"><span data-stu-id="438d3-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="438d3-108">out Puntatore al flusso di metadati.</span><span class="sxs-lookup"><span data-stu-id="438d3-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="438d3-109">out Dimensione, in byte, del `ppv`.</span><span class="sxs-lookup"><span data-stu-id="438d3-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="438d3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="438d3-110">Requirements</span></span>  
 <span data-ttu-id="438d3-111">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="438d3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="438d3-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="438d3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="438d3-113">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="438d3-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="438d3-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="438d3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="438d3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="438d3-115">See also</span></span>

- [<span data-ttu-id="438d3-116">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="438d3-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="438d3-117">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="438d3-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)

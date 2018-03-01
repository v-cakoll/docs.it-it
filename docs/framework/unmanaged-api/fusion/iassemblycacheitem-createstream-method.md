---
title: Metodo IAssemblyCacheItem::CreateStream
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAsssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a24d9732a8e413b3cde0ac1c622743153ff6fd01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="ba20d-102">Metodo IAssemblyCacheItem::CreateStream</span><span class="sxs-lookup"><span data-stu-id="ba20d-102">IAssemblyCacheItem::CreateStream Method</span></span>
<span data-ttu-id="ba20d-103">Crea un flusso con il nome specificato e il formato.</span><span class="sxs-lookup"><span data-stu-id="ba20d-103">Creates a stream with the specified name and format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba20d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba20d-104">Syntax</span></span>  
  
```  
HRESULT CreateStream (  
    [in]  DWORD dwFlags,  
    [in]  LPCWSTR pszStreamName,  
    [in]  DWORD dwFormat,  
    [in]  DWORD dwFormatFlags,  
    [out] IStream **ppIStream,  
    [in, optional] ULARGE_INTEGER *puliMaxSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ba20d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba20d-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="ba20d-106">[in] Flag definiti in Fusion.</span><span class="sxs-lookup"><span data-stu-id="ba20d-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszStreamName`  
 <span data-ttu-id="ba20d-107">[in] Il nome del flusso da creare.</span><span class="sxs-lookup"><span data-stu-id="ba20d-107">[in] The name of the stream to be created.</span></span>  
  
 `dwFormat`  
 <span data-ttu-id="ba20d-108">[in] Il formato del file da trasmettere.</span><span class="sxs-lookup"><span data-stu-id="ba20d-108">[in] The format of the file to be streamed.</span></span>  
  
 `dwFormatFlags`  
 <span data-ttu-id="ba20d-109">[in] Flag specifici del formato definito in Fusion.</span><span class="sxs-lookup"><span data-stu-id="ba20d-109">[in] Format-specific flags defined in Fusion.idl.</span></span>  
  
 `ppIStream`  
 <span data-ttu-id="ba20d-110">[out] Un puntatore all'indirizzo dell'oggetto restituito <xref:IStream> istanza.</span><span class="sxs-lookup"><span data-stu-id="ba20d-110">[out] A pointer to the address of the returned <xref:IStream> instance.</span></span>  
  
 `puliMaxSize`  
 <span data-ttu-id="ba20d-111">[in, facoltativo] La dimensione massima del flusso a cui fa riferimento `ppIStream`.</span><span class="sxs-lookup"><span data-stu-id="ba20d-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba20d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba20d-112">Requirements</span></span>  
 <span data-ttu-id="ba20d-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba20d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba20d-114">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ba20d-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ba20d-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba20d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba20d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba20d-116">See Also</span></span>  
 [<span data-ttu-id="ba20d-117">Interfaccia IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="ba20d-117">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)

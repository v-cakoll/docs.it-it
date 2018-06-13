---
title: Metodo IAssemblyCacheItem::CreateStream
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8057406552525be19f8e6457de9faf841edc6e68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429501"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="cb55a-102">Metodo IAssemblyCacheItem::CreateStream</span><span class="sxs-lookup"><span data-stu-id="cb55a-102">IAssemblyCacheItem::CreateStream Method</span></span>
<span data-ttu-id="cb55a-103">Crea un flusso con il nome specificato e il formato.</span><span class="sxs-lookup"><span data-stu-id="cb55a-103">Creates a stream with the specified name and format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb55a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb55a-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="cb55a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cb55a-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="cb55a-106">[in] Flag definiti in Fusion.</span><span class="sxs-lookup"><span data-stu-id="cb55a-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszStreamName`  
 <span data-ttu-id="cb55a-107">[in] Il nome del flusso da creare.</span><span class="sxs-lookup"><span data-stu-id="cb55a-107">[in] The name of the stream to be created.</span></span>  
  
 `dwFormat`  
 <span data-ttu-id="cb55a-108">[in] Il formato del file da trasmettere.</span><span class="sxs-lookup"><span data-stu-id="cb55a-108">[in] The format of the file to be streamed.</span></span>  
  
 `dwFormatFlags`  
 <span data-ttu-id="cb55a-109">[in] Flag specifici del formato definito in Fusion.</span><span class="sxs-lookup"><span data-stu-id="cb55a-109">[in] Format-specific flags defined in Fusion.idl.</span></span>  
  
 `ppIStream`  
 <span data-ttu-id="cb55a-110">[out] Un puntatore all'indirizzo dell'oggetto restituito [IStream](https://msdn.microsoft.com/library/aa380034.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="cb55a-110">[out] A pointer to the address of the returned [IStream](https://msdn.microsoft.com/library/aa380034.aspx) instance.</span></span>  
  
 `puliMaxSize`  
 <span data-ttu-id="cb55a-111">[in, facoltativo] La dimensione massima del flusso a cui fa riferimento `ppIStream`.</span><span class="sxs-lookup"><span data-stu-id="cb55a-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb55a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb55a-112">Requirements</span></span>  
 <span data-ttu-id="cb55a-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb55a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb55a-114">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="cb55a-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cb55a-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb55a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb55a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb55a-116">See Also</span></span>  
 [<span data-ttu-id="cb55a-117">Interfaccia IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="cb55a-117">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)

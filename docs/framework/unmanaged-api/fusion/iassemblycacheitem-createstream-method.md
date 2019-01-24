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
ms.openlocfilehash: 58fb8e3ae0f9485399aebe81b5f77ee61ee8f3ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641096"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="33cd4-102">Metodo IAssemblyCacheItem::CreateStream</span><span class="sxs-lookup"><span data-stu-id="33cd4-102">IAssemblyCacheItem::CreateStream Method</span></span>
<span data-ttu-id="33cd4-103">Crea un flusso con il nome specificato e il formato.</span><span class="sxs-lookup"><span data-stu-id="33cd4-103">Creates a stream with the specified name and format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33cd4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33cd4-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="33cd4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="33cd4-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="33cd4-106">[in] Flag definiti in Fusion.</span><span class="sxs-lookup"><span data-stu-id="33cd4-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszStreamName`  
 <span data-ttu-id="33cd4-107">[in] Il nome del flusso da creare.</span><span class="sxs-lookup"><span data-stu-id="33cd4-107">[in] The name of the stream to be created.</span></span>  
  
 `dwFormat`  
 <span data-ttu-id="33cd4-108">[in] Il formato del file deve essere trasmessa.</span><span class="sxs-lookup"><span data-stu-id="33cd4-108">[in] The format of the file to be streamed.</span></span>  
  
 `dwFormatFlags`  
 <span data-ttu-id="33cd4-109">[in] Flag specifici del formato definito in Fusion.</span><span class="sxs-lookup"><span data-stu-id="33cd4-109">[in] Format-specific flags defined in Fusion.idl.</span></span>  
  
 `ppIStream`  
 <span data-ttu-id="33cd4-110">[out] Un puntatore all'indirizzo del valore restituito [IStream](/windows/desktop/api/objidl/nn-objidl-istream) istanza.</span><span class="sxs-lookup"><span data-stu-id="33cd4-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>  
  
 `puliMaxSize`  
 <span data-ttu-id="33cd4-111">[in, optional] La dimensione massima del flusso fa `ppIStream`.</span><span class="sxs-lookup"><span data-stu-id="33cd4-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33cd4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33cd4-112">Requirements</span></span>  
 <span data-ttu-id="33cd4-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33cd4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33cd4-114">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="33cd4-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="33cd4-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33cd4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33cd4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33cd4-116">See also</span></span>
- [<span data-ttu-id="33cd4-117">Interfaccia IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="33cd4-117">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)

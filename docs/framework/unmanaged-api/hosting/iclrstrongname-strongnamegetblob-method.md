---
title: Metodo ICLRStrongName::StrongNameGetBlob
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4621a7d143d401d4cb620ac17c31e4ee5f13837
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46577652"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="ff9c0-102">Metodo ICLRStrongName::StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="ff9c0-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="ff9c0-103">Completa il buffer specificato con la rappresentazione binaria del file eseguibile presente all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="ff9c0-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff9c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff9c0-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff9c0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff9c0-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="ff9c0-106">[in] Un percorso valido per il file eseguibile da caricare.</span><span class="sxs-lookup"><span data-stu-id="ff9c0-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="ff9c0-107">[in] Buffer in cui caricare il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="ff9c0-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="ff9c0-108">[in, out] La massima dimensione, espressa in byte, richiesta del `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="ff9c0-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="ff9c0-109">Al momento della restituzione, le dimensioni effettive, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="ff9c0-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff9c0-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ff9c0-110">Return Value</span></span>  
 <span data-ttu-id="ff9c0-111">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="ff9c0-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff9c0-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff9c0-112">Requirements</span></span>  
 <span data-ttu-id="ff9c0-113">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff9c0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff9c0-114">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="ff9c0-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ff9c0-115">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ff9c0-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff9c0-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff9c0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff9c0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff9c0-117">See Also</span></span>  
 [<span data-ttu-id="ff9c0-118">Metodo StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="ff9c0-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="ff9c0-119">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ff9c0-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

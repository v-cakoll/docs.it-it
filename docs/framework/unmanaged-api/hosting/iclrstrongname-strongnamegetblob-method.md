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
ms.openlocfilehash: 38b6785afae75888398f1c0d3d69be2ce21d67bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160784"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="90ca8-102">Metodo ICLRStrongName::StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="90ca8-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="90ca8-103">Completa il buffer specificato con la rappresentazione binaria del file eseguibile presente all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="90ca8-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90ca8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90ca8-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90ca8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="90ca8-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="90ca8-106">[in] Un percorso valido per il file eseguibile da caricare.</span><span class="sxs-lookup"><span data-stu-id="90ca8-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="90ca8-107">[in] Buffer in cui caricare il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="90ca8-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="90ca8-108">[in, out] La massima dimensione, espressa in byte, richiesta del `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="90ca8-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="90ca8-109">Al momento della restituzione, le dimensioni effettive, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="90ca8-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90ca8-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="90ca8-110">Return Value</span></span>  
 `S_OK` <span data-ttu-id="90ca8-111">Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="90ca8-111">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90ca8-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="90ca8-112">Requirements</span></span>  
 <span data-ttu-id="90ca8-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90ca8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90ca8-114">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="90ca8-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="90ca8-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="90ca8-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="90ca8-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="90ca8-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="90ca8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90ca8-117">See also</span></span>

- [<span data-ttu-id="90ca8-118">Metodo StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="90ca8-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="90ca8-119">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="90ca8-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

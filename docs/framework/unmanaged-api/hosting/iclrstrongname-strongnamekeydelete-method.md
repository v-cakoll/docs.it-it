---
title: Metodo ICLRStrongName::StrongNameKeyDelete
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyDelete
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b3a1d742ac2ad74d327afe4dce097d0f11e5cfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="1bcba-102">Metodo ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="1bcba-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="1bcba-103">Elimina il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="1bcba-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bcba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1bcba-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1bcba-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1bcba-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="1bcba-106">[in] Il nome del contenitore di chiavi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="1bcba-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1bcba-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1bcba-107">Return Value</span></span>  
 <span data-ttu-id="1bcba-108">`S_OK`Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="1bcba-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bcba-109">Note</span><span class="sxs-lookup"><span data-stu-id="1bcba-109">Remarks</span></span>  
 <span data-ttu-id="1bcba-110">Utilizzare il [ICLRStrongName:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) metodo per importare una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="1bcba-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bcba-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1bcba-111">Requirements</span></span>  
 <span data-ttu-id="1bcba-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bcba-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bcba-113">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="1bcba-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1bcba-114">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1bcba-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1bcba-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bcba-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bcba-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bcba-116">See Also</span></span>  
 [<span data-ttu-id="1bcba-117">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="1bcba-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="1bcba-118">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="1bcba-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

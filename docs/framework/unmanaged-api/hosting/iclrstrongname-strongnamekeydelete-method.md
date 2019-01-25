---
title: Metodo ICLRStrongName::StrongNameKeyDelete
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e55a94cc5a877efa0ddc8e2a5e554f5d5791e53f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676120"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="c0775-102">Metodo ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="c0775-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="c0775-103">Elimina il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="c0775-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0775-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0775-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0775-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c0775-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="c0775-106">[in] Il nome del contenitore di chiavi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="c0775-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0775-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c0775-107">Return Value</span></span>  
 <span data-ttu-id="c0775-108">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="c0775-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0775-109">Note</span><span class="sxs-lookup"><span data-stu-id="c0775-109">Remarks</span></span>  
 <span data-ttu-id="c0775-110">Usare la [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) metodo per importare una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="c0775-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0775-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0775-111">Requirements</span></span>  
 <span data-ttu-id="c0775-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0775-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0775-113">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c0775-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c0775-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c0775-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0775-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0775-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0775-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0775-116">See also</span></span>
- [<span data-ttu-id="c0775-117">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="c0775-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="c0775-118">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c0775-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

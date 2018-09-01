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
ms.openlocfilehash: 2515eb0e33a033e78843d68754d3175e91165dff
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388787"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="330b0-102">Metodo ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="330b0-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="330b0-103">Elimina il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="330b0-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="330b0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="330b0-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="330b0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="330b0-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="330b0-106">[in] Il nome del contenitore di chiavi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="330b0-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="330b0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="330b0-107">Return Value</span></span>  
 <span data-ttu-id="330b0-108">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="330b0-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="330b0-109">Note</span><span class="sxs-lookup"><span data-stu-id="330b0-109">Remarks</span></span>  
 <span data-ttu-id="330b0-110">Usare la [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) metodo per importare una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="330b0-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="330b0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="330b0-111">Requirements</span></span>  
 <span data-ttu-id="330b0-112">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="330b0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="330b0-113">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="330b0-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="330b0-114">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="330b0-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="330b0-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="330b0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="330b0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="330b0-116">See Also</span></span>  
 [<span data-ttu-id="330b0-117">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="330b0-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="330b0-118">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="330b0-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

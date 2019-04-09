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
ms.openlocfilehash: 412aa8fd30294ac9681a5edd02bb4bdfe25b3fab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143988"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="48b3a-102">Metodo ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="48b3a-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="48b3a-103">Elimina il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="48b3a-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48b3a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48b3a-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48b3a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="48b3a-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="48b3a-106">[in] Il nome del contenitore di chiavi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="48b3a-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48b3a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="48b3a-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="48b3a-108">Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="48b3a-108">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48b3a-109">Note</span><span class="sxs-lookup"><span data-stu-id="48b3a-109">Remarks</span></span>  
 <span data-ttu-id="48b3a-110">Usare la [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) metodo per importare una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="48b3a-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48b3a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48b3a-111">Requirements</span></span>  
 <span data-ttu-id="48b3a-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48b3a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48b3a-113">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="48b3a-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="48b3a-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="48b3a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="48b3a-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="48b3a-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="48b3a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48b3a-116">See also</span></span>

- [<span data-ttu-id="48b3a-117">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="48b3a-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="48b3a-118">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="48b3a-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

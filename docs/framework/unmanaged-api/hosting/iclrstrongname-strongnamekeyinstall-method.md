---
title: Metodo ICLRStrongName::StrongNameKeyInstall
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a2badf8f164abd1bbb8892ec5db28f7cf39f5c5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775659"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="585f6-102">Metodo ICLRStrongName::StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="585f6-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="585f6-103">Importa una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="585f6-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="585f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="585f6-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="585f6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="585f6-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="585f6-106">[in] Il nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="585f6-106">[in] The name of the key container.</span></span> <span data-ttu-id="585f6-107">`wszKeyContainer` deve essere una stringa non vuota.</span><span class="sxs-lookup"><span data-stu-id="585f6-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="585f6-108">[in] La coppia di chiavi binaria.</span><span class="sxs-lookup"><span data-stu-id="585f6-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="585f6-109">[in] Le dimensioni, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="585f6-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="585f6-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="585f6-110">Return Value</span></span>  
 <span data-ttu-id="585f6-111">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="585f6-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="585f6-112">Note</span><span class="sxs-lookup"><span data-stu-id="585f6-112">Remarks</span></span>  
 <span data-ttu-id="585f6-113">Usare la [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) metodo per eliminare il contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="585f6-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="585f6-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="585f6-114">Requirements</span></span>  
 <span data-ttu-id="585f6-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="585f6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="585f6-116">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="585f6-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="585f6-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="585f6-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="585f6-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="585f6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="585f6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="585f6-119">See also</span></span>

- [<span data-ttu-id="585f6-120">Metodo StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="585f6-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="585f6-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="585f6-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

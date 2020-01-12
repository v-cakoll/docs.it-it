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
ms.openlocfilehash: 95098cbb060c06d2d5a5a4c04b6fa9017bca66a1
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899587"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="77be2-102">Metodo ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="77be2-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="77be2-103">Elimina il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="77be2-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77be2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77be2-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77be2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="77be2-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="77be2-106">in Nome del contenitore di chiavi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="77be2-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77be2-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="77be2-107">Return Value</span></span>  
 <span data-ttu-id="77be2-108">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="77be2-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77be2-109">Note</span><span class="sxs-lookup"><span data-stu-id="77be2-109">Remarks</span></span>  
 <span data-ttu-id="77be2-110">Usare il metodo [ICLRStrongName:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) per importare una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="77be2-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77be2-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="77be2-111">Requirements</span></span>  
 <span data-ttu-id="77be2-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77be2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77be2-113">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="77be2-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="77be2-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="77be2-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77be2-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77be2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77be2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77be2-116">See also</span></span>

- [<span data-ttu-id="77be2-117">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="77be2-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="77be2-118">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="77be2-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

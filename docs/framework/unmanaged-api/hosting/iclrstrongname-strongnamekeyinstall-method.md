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
ms.openlocfilehash: 2a76377857c3cf1e40a328b9a13fb4834321707e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899561"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="3b31e-102">Metodo ICLRStrongName::StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="3b31e-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="3b31e-103">Importa una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="3b31e-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b31e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b31e-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b31e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3b31e-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="3b31e-106">in Nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="3b31e-106">[in] The name of the key container.</span></span> <span data-ttu-id="3b31e-107">`wszKeyContainer` deve essere una stringa non vuota.</span><span class="sxs-lookup"><span data-stu-id="3b31e-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="3b31e-108">in Coppia di chiavi binarie.</span><span class="sxs-lookup"><span data-stu-id="3b31e-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="3b31e-109">in Dimensione, in byte, del `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="3b31e-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b31e-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3b31e-110">Return Value</span></span>  
 <span data-ttu-id="3b31e-111">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="3b31e-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b31e-112">Note</span><span class="sxs-lookup"><span data-stu-id="3b31e-112">Remarks</span></span>  
 <span data-ttu-id="3b31e-113">Usare il metodo [ICLRStrongName:: StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) per eliminare il contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="3b31e-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b31e-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3b31e-114">Requirements</span></span>  
 <span data-ttu-id="3b31e-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b31e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b31e-116">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="3b31e-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3b31e-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3b31e-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b31e-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b31e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b31e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b31e-119">See also</span></span>

- [<span data-ttu-id="3b31e-120">Metodo StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="3b31e-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="3b31e-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="3b31e-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

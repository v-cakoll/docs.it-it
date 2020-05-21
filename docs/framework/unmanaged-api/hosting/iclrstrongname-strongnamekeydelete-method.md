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
ms.openlocfilehash: 8f6f2445d88d608d51be4e6fe1e064efbb58325d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763098"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="0929c-102">Metodo ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="0929c-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="0929c-103">Elimina il contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="0929c-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0929c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0929c-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0929c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0929c-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="0929c-106">in Nome del contenitore di chiavi da eliminare.</span><span class="sxs-lookup"><span data-stu-id="0929c-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0929c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0929c-107">Return Value</span></span>  
 <span data-ttu-id="0929c-108">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="0929c-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0929c-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0929c-109">Remarks</span></span>  
 <span data-ttu-id="0929c-110">Usare il metodo [ICLRStrongName:: StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) per importare una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="0929c-110">Use the [ICLRStrongName::StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0929c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0929c-111">Requirements</span></span>  
 <span data-ttu-id="0929c-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0929c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0929c-113">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="0929c-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0929c-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0929c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0929c-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0929c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0929c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0929c-116">See also</span></span>

- [<span data-ttu-id="0929c-117">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="0929c-117">StrongNameKeyInstall Method</span></span>](iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="0929c-118">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="0929c-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

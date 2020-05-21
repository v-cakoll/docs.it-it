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
ms.openlocfilehash: e0c60d6e74c48531a223f6dbb35125b5a2017cbb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763041"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="43700-102">Metodo ICLRStrongName::StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="43700-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="43700-103">Importa una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="43700-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43700-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43700-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43700-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="43700-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="43700-106">in Nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="43700-106">[in] The name of the key container.</span></span> <span data-ttu-id="43700-107">`wszKeyContainer`deve essere una stringa non vuota.</span><span class="sxs-lookup"><span data-stu-id="43700-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="43700-108">in Coppia di chiavi binarie.</span><span class="sxs-lookup"><span data-stu-id="43700-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="43700-109">in Dimensione, in byte, di `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="43700-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43700-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="43700-110">Return Value</span></span>  
 <span data-ttu-id="43700-111">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="43700-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43700-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="43700-112">Remarks</span></span>  
 <span data-ttu-id="43700-113">Usare il metodo [ICLRStrongName:: StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md) per eliminare il contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="43700-113">Use the [ICLRStrongName::StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43700-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43700-114">Requirements</span></span>  
 <span data-ttu-id="43700-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43700-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43700-116">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="43700-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="43700-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="43700-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43700-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43700-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43700-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43700-119">See also</span></span>

- [<span data-ttu-id="43700-120">Metodo StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="43700-120">StrongNameKeyDelete Method</span></span>](iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="43700-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="43700-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

---
title: Metodo ICLRStrongName::StrongNameKeyGen
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
ms.openlocfilehash: db5c0dbe57607c7a3bf8b97cee734415aa934336
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763085"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="cf2bd-102">Metodo ICLRStrongName::StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="cf2bd-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="cf2bd-103">Crea una nuova coppia di chiavi pubblica/privata per l'uso come nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="cf2bd-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf2bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf2bd-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf2bd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cf2bd-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="cf2bd-106">in Nome del contenitore di chiavi richiesto.</span><span class="sxs-lookup"><span data-stu-id="cf2bd-106">[in] The requested key container name.</span></span> <span data-ttu-id="cf2bd-107">`wszKeyContainer`deve essere una stringa non vuota o null per generare un nome temporaneo.</span><span class="sxs-lookup"><span data-stu-id="cf2bd-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cf2bd-108">in Valore che specifica se lasciare la chiave registrata.</span><span class="sxs-lookup"><span data-stu-id="cf2bd-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="cf2bd-109">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf2bd-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="cf2bd-110">0x00000000: viene usato quando `wszKeyContainer` è null per generare un nome del contenitore di chiavi temporaneo.</span><span class="sxs-lookup"><span data-stu-id="cf2bd-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="cf2bd-111">0x00000001 ( `SN_LEAVE_KEY` ): specifica che la chiave deve essere lasciata registrata.</span><span class="sxs-lookup"><span data-stu-id="cf2bd-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="cf2bd-112">out Coppia di chiavi pubblica/privata restituita.</span><span class="sxs-lookup"><span data-stu-id="cf2bd-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="cf2bd-113">out Dimensione, in byte, di `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="cf2bd-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf2bd-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cf2bd-114">Return Value</span></span>  
 <span data-ttu-id="cf2bd-115">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="cf2bd-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf2bd-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cf2bd-116">Remarks</span></span>  
 <span data-ttu-id="cf2bd-117">Il metodo [ICLRStrongName:: StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) crea una chiave a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="cf2bd-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="cf2bd-118">Dopo che la chiave è stata recuperata, è necessario chiamare il metodo [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="cf2bd-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf2bd-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf2bd-119">Requirements</span></span>  
 <span data-ttu-id="cf2bd-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf2bd-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf2bd-121">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="cf2bd-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cf2bd-122">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cf2bd-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf2bd-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf2bd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf2bd-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf2bd-124">See also</span></span>

- [<span data-ttu-id="cf2bd-125">Metodo StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="cf2bd-125">StrongNameKeyGenEx Method</span></span>](iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="cf2bd-126">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="cf2bd-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

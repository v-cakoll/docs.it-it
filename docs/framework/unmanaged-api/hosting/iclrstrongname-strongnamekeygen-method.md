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
ms.openlocfilehash: e437ee2ab04d3b1126ec2911553e87586e74e54e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899622"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="54b20-102">Metodo ICLRStrongName::StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="54b20-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="54b20-103">Crea una nuova coppia di chiavi pubblica/privata per l'uso come nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="54b20-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54b20-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54b20-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54b20-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="54b20-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="54b20-106">in Nome del contenitore di chiavi richiesto.</span><span class="sxs-lookup"><span data-stu-id="54b20-106">[in] The requested key container name.</span></span> <span data-ttu-id="54b20-107">`wszKeyContainer` deve essere una stringa non vuota o null per generare un nome temporaneo.</span><span class="sxs-lookup"><span data-stu-id="54b20-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="54b20-108">in Valore che specifica se lasciare la chiave registrata.</span><span class="sxs-lookup"><span data-stu-id="54b20-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="54b20-109">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="54b20-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="54b20-110">0x00000000: viene usato quando `wszKeyContainer` è null per generare un nome del contenitore di chiavi temporaneo.</span><span class="sxs-lookup"><span data-stu-id="54b20-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="54b20-111">0x00000001 (`SN_LEAVE_KEY`): specifica che la chiave deve essere lasciata registrata.</span><span class="sxs-lookup"><span data-stu-id="54b20-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="54b20-112">out Coppia di chiavi pubblica/privata restituita.</span><span class="sxs-lookup"><span data-stu-id="54b20-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="54b20-113">out Dimensione, in byte, del `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="54b20-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54b20-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="54b20-114">Return Value</span></span>  
 <span data-ttu-id="54b20-115">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="54b20-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54b20-116">Note</span><span class="sxs-lookup"><span data-stu-id="54b20-116">Remarks</span></span>  
 <span data-ttu-id="54b20-117">Il metodo [ICLRStrongName:: StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) crea una chiave a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="54b20-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="54b20-118">Dopo che la chiave è stata recuperata, è necessario chiamare il metodo [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="54b20-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54b20-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="54b20-119">Requirements</span></span>  
 <span data-ttu-id="54b20-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54b20-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54b20-121">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="54b20-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="54b20-122">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="54b20-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54b20-123">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54b20-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b20-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54b20-124">See also</span></span>

- [<span data-ttu-id="54b20-125">Metodo StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="54b20-125">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="54b20-126">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="54b20-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

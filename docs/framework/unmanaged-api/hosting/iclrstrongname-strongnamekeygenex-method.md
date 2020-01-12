---
title: Metodo ICLRStrongName::StrongNameKeyGenEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
ms.openlocfilehash: b09677a45c5d515aacb2cac709599140039a9dd8
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899548"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="a5960-102">Metodo ICLRStrongName::StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="a5960-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="a5960-103">Genera una nuova coppia di chiavi pubblica/privata con la dimensione della chiave specificata, per l'uso del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="a5960-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5960-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5960-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5960-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a5960-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="a5960-106">in Nome del contenitore di chiavi richiesto.</span><span class="sxs-lookup"><span data-stu-id="a5960-106">[in] The requested key container name.</span></span> <span data-ttu-id="a5960-107">`wszKeyContainer` deve essere una stringa non vuota o null per generare un nome temporaneo.</span><span class="sxs-lookup"><span data-stu-id="a5960-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a5960-108">in Valore che specifica se lasciare la chiave registrata.</span><span class="sxs-lookup"><span data-stu-id="a5960-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="a5960-109">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5960-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="a5960-110">0x00000000: viene usato quando `wszKeyContainer` è null per generare un nome del contenitore di chiavi temporaneo.</span><span class="sxs-lookup"><span data-stu-id="a5960-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="a5960-111">0x00000001 (`SN_LEAVE_KEY`): specifica che la chiave deve essere lasciata registrata.</span><span class="sxs-lookup"><span data-stu-id="a5960-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="a5960-112">in Dimensioni richieste della chiave, in bit.</span><span class="sxs-lookup"><span data-stu-id="a5960-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="a5960-113">out Coppia di chiavi pubblica/privata restituita.</span><span class="sxs-lookup"><span data-stu-id="a5960-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="a5960-114">out Dimensione, in byte, del `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="a5960-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5960-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a5960-115">Return Value</span></span>  
 <span data-ttu-id="a5960-116">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="a5960-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5960-117">Note</span><span class="sxs-lookup"><span data-stu-id="a5960-117">Remarks</span></span>  
 <span data-ttu-id="a5960-118">Per la firma di un assembly con un nome sicuro, le versioni di .NET Framework 1,0 e 1,1 richiedono un `dwKeySize` di 1024 bit; la versione 2,0 aggiunge i supporti per le chiavi a 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="a5960-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="a5960-119">Dopo che la chiave è stata recuperata, è necessario chiamare il metodo [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="a5960-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5960-120">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a5960-120">Requirements</span></span>  
 <span data-ttu-id="a5960-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5960-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5960-122">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="a5960-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a5960-123">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a5960-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5960-124">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5960-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5960-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5960-125">See also</span></span>

- [<span data-ttu-id="a5960-126">Metodo StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="a5960-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="a5960-127">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a5960-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

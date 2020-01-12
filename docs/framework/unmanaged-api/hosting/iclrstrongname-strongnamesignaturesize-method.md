---
title: Metodo ICLRStrongName::StrongNameSignatureSize
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
ms.openlocfilehash: 049324baec02fbb03c2db80391ade8a24920a15c
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901086"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="4a1f5-102">Metodo ICLRStrongName::StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="4a1f5-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="4a1f5-103">Restituisce le dimensioni della firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="4a1f5-104">Questo metodo viene in genere usato dai compilatori per determinare la quantità di spazio da riservare nel file quando si crea un assembly con firma ritardata.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a1f5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a1f5-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="4a1f5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a1f5-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="4a1f5-107">in Struttura di tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi utilizzata per generare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="4a1f5-108">in Dimensione, in byte, del `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="4a1f5-109">in Numero di byte necessari per archiviare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a1f5-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4a1f5-110">Return Value</span></span>  
 <span data-ttu-id="4a1f5-111">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="4a1f5-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a1f5-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="4a1f5-112">Requirements</span></span>  
 <span data-ttu-id="4a1f5-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a1f5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a1f5-114">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="4a1f5-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4a1f5-115">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4a1f5-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a1f5-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a1f5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a1f5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a1f5-117">See also</span></span>

- [<span data-ttu-id="4a1f5-118">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="4a1f5-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

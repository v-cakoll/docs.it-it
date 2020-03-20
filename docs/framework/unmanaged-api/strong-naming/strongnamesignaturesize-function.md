---
title: Funzione StrongNameSignatureSize
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
ms.openlocfilehash: a19d875b8fb81f2af3821e69452f0f0ed591cd22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176890"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="5dda3-102">Funzione StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="5dda3-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="5dda3-103">Restituisce le dimensioni della firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="5dda3-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="5dda3-104">`StrongNameSignatureSize`viene in genere utilizzato dai compilatori per determinare la quantità di spazio da riservare nel file durante la creazione di un assembly con firma ritardata.</span><span class="sxs-lookup"><span data-stu-id="5dda3-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="5dda3-105">Questa funzione è deprecata.</span><span class="sxs-lookup"><span data-stu-id="5dda3-105">This function has been deprecated.</span></span> <span data-ttu-id="5dda3-106">Utilizzare invece il metodo [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5dda3-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dda3-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5dda3-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="5dda3-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="5dda3-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="5dda3-109">[in] Struttura di tipo [PublicKeyBlob](publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi utilizzata per generare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="5dda3-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="5dda3-110">[in] Dimensione, in byte, `pbPublicKeyBlob`di .</span><span class="sxs-lookup"><span data-stu-id="5dda3-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="5dda3-111">[in] Numero di byte necessari per archiviare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="5dda3-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5dda3-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5dda3-112">Return Value</span></span>  
 <span data-ttu-id="5dda3-113">`true`al termine del successo; in `false`caso contrario, .</span><span class="sxs-lookup"><span data-stu-id="5dda3-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5dda3-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5dda3-114">Remarks</span></span>  
 <span data-ttu-id="5dda3-115">Se `StrongNameSignatureSize` la funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="5dda3-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dda3-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5dda3-116">Requirements</span></span>  
 <span data-ttu-id="5dda3-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dda3-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dda3-118">**Intestazione:** NomeForte.h</span><span class="sxs-lookup"><span data-stu-id="5dda3-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5dda3-119">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5dda3-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5dda3-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dda3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dda3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dda3-121">See also</span></span>

- [<span data-ttu-id="5dda3-122">Metodo StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="5dda3-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="5dda3-123">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5dda3-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f98b971e430a2c35a4c484f4f9c4bf387c640c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798964"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="fe6b9-102">Funzione StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="fe6b9-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="fe6b9-103">Restituisce le dimensioni della firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="fe6b9-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="fe6b9-104">`StrongNameSignatureSize`viene in genere usato dai compilatori per determinare la quantità di spazio da riservare nel file quando si crea un assembly con firma ritardata.</span><span class="sxs-lookup"><span data-stu-id="fe6b9-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="fe6b9-105">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="fe6b9-105">This function has been deprecated.</span></span> <span data-ttu-id="fe6b9-106">Usare invece il metodo [ICLRStrongName:: StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fe6b9-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe6b9-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe6b9-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="fe6b9-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe6b9-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="fe6b9-109">in Struttura di tipo [PublicKeyBlob](publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi utilizzata per generare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="fe6b9-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="fe6b9-110">in Dimensione, in byte, di `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="fe6b9-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="fe6b9-111">in Numero di byte necessari per archiviare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="fe6b9-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe6b9-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fe6b9-112">Return Value</span></span>  
 <span data-ttu-id="fe6b9-113">`true`al completamento; in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="fe6b9-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe6b9-114">Note</span><span class="sxs-lookup"><span data-stu-id="fe6b9-114">Remarks</span></span>  
 <span data-ttu-id="fe6b9-115">Se la `StrongNameSignatureSize` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="fe6b9-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe6b9-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe6b9-116">Requirements</span></span>  
 <span data-ttu-id="fe6b9-117">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe6b9-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe6b9-118">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="fe6b9-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="fe6b9-119">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fe6b9-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe6b9-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe6b9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe6b9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe6b9-121">See also</span></span>

- [<span data-ttu-id="fe6b9-122">Metodo StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="fe6b9-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="fe6b9-123">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="fe6b9-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

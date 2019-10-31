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
ms.openlocfilehash: a8856790b655f071df704879a247169f456ae2f5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130879"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="da6ec-102">Funzione StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="da6ec-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="da6ec-103">Restituisce le dimensioni della firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="da6ec-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="da6ec-104">`StrongNameSignatureSize` viene in genere usato dai compilatori per determinare la quantità di spazio da riservare nel file quando si crea un assembly con firma ritardata.</span><span class="sxs-lookup"><span data-stu-id="da6ec-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="da6ec-105">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="da6ec-105">This function has been deprecated.</span></span> <span data-ttu-id="da6ec-106">Usare invece il metodo [ICLRStrongName:: StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="da6ec-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da6ec-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da6ec-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="da6ec-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="da6ec-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="da6ec-109">in Struttura di tipo [PublicKeyBlob](publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi utilizzata per generare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="da6ec-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="da6ec-110">in Dimensione, in byte, del `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="da6ec-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="da6ec-111">in Numero di byte necessari per archiviare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="da6ec-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da6ec-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="da6ec-112">Return Value</span></span>  
 <span data-ttu-id="da6ec-113">`true` al completamento; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="da6ec-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da6ec-114">Note</span><span class="sxs-lookup"><span data-stu-id="da6ec-114">Remarks</span></span>  
 <span data-ttu-id="da6ec-115">Se la funzione `StrongNameSignatureSize` non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="da6ec-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da6ec-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da6ec-116">Requirements</span></span>  
 <span data-ttu-id="da6ec-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da6ec-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da6ec-118">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="da6ec-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="da6ec-119">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="da6ec-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="da6ec-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da6ec-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da6ec-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da6ec-121">See also</span></span>

- [<span data-ttu-id="da6ec-122">Metodo StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="da6ec-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="da6ec-123">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="da6ec-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

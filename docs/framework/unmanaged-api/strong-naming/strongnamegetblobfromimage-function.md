---
title: Funzione StrongNameGetBlobFromImage
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
ms.openlocfilehash: 41226cd909900bd2da7bdcf9b9a49567d3042b01
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73094883"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="e2f77-102">Funzione StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="e2f77-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="e2f77-103">Ottiene una rappresentazione binaria dell'immagine dell'assembly in corrispondenza dell'indirizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="e2f77-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="e2f77-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="e2f77-104">This function has been deprecated.</span></span> <span data-ttu-id="e2f77-105">Usare invece il metodo [ICLRStrongName:: StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e2f77-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2f77-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2f77-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2f77-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2f77-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="e2f77-108">in Indirizzo di memoria del manifesto dell'assembly mappato.</span><span class="sxs-lookup"><span data-stu-id="e2f77-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="e2f77-109">in Dimensione, in byte, dell'immagine in `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="e2f77-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="e2f77-110">in Buffer che contiene la rappresentazione binaria dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="e2f77-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="e2f77-111">[in, out] Dimensione massima richiesta, in byte, del `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="e2f77-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="e2f77-112">Al ritorno, le dimensioni effettive, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="e2f77-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2f77-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e2f77-113">Return Value</span></span>  
 <span data-ttu-id="e2f77-114">`true` al completamento; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e2f77-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2f77-115">Note</span><span class="sxs-lookup"><span data-stu-id="e2f77-115">Remarks</span></span>  
 <span data-ttu-id="e2f77-116">Se la funzione `StrongNameGetBlobFromImage` non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="e2f77-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2f77-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2f77-117">Requirements</span></span>  
 <span data-ttu-id="e2f77-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2f77-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2f77-119">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="e2f77-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e2f77-120">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e2f77-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e2f77-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2f77-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2f77-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2f77-122">See also</span></span>

- [<span data-ttu-id="e2f77-123">Metodo StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="e2f77-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="e2f77-124">Metodo StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="e2f77-124">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="e2f77-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e2f77-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

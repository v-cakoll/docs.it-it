---
title: Funzione StrongNameFreeBuffer
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
ms.openlocfilehash: 50e3cc6e677de45be9256a2a818ebd6ed7d8b843
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176916"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="7b0eb-102">Funzione StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="7b0eb-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="7b0eb-103">Libera la memoria allocata con una precedente chiamata a una funzione con nome sicuro, ad esempio [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="7b0eb-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="7b0eb-104">Questa funzione è deprecata.</span><span class="sxs-lookup"><span data-stu-id="7b0eb-104">This function has been deprecated.</span></span> <span data-ttu-id="7b0eb-105">Utilizzare invece il metodo [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7b0eb-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b0eb-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b0eb-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b0eb-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b0eb-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="7b0eb-108">[in] Un puntatore alla memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="7b0eb-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b0eb-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b0eb-109">Requirements</span></span>  
 <span data-ttu-id="7b0eb-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b0eb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b0eb-111">**Intestazione:** NomeForte.h</span><span class="sxs-lookup"><span data-stu-id="7b0eb-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7b0eb-112">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7b0eb-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7b0eb-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b0eb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b0eb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b0eb-114">See also</span></span>

- [<span data-ttu-id="7b0eb-115">Metodo StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="7b0eb-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="7b0eb-116">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="7b0eb-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

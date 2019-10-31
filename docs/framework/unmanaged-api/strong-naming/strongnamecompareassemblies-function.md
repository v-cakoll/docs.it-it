---
title: Funzione StrongNameCompareAssemblies
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
ms.openlocfilehash: adde52dddb63b83dcd7ff10703a43928d9601c92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140629"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="11b03-102">Funzione StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="11b03-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="11b03-103">Determina se due assembly differiscono solo per le firme con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="11b03-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="11b03-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="11b03-104">This function has been deprecated.</span></span> <span data-ttu-id="11b03-105">Usare invece il metodo [ICLRStrongName:: StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) .</span><span class="sxs-lookup"><span data-stu-id="11b03-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11b03-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11b03-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11b03-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="11b03-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="11b03-108">in Percorso del primo assembly.</span><span class="sxs-lookup"><span data-stu-id="11b03-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="11b03-109">in Percorso del secondo assembly.</span><span class="sxs-lookup"><span data-stu-id="11b03-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="11b03-110">out Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="11b03-110">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="11b03-111">`SN_CMP_DIFFERENT` (0): specifica che gli assembly contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="11b03-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="11b03-112">`SN_CMP_IDENTICAL` (1): specifica che gli assembly sono esattamente uguali, incluse le relative firme e checksum.</span><span class="sxs-lookup"><span data-stu-id="11b03-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="11b03-113">`SN_CMP_SIGONLY` (2): specifica che gli assembly differiscono solo per la firma e il checksum.</span><span class="sxs-lookup"><span data-stu-id="11b03-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11b03-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="11b03-114">Return Value</span></span>  
 <span data-ttu-id="11b03-115">`true` al completamento; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="11b03-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11b03-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11b03-116">Requirements</span></span>  
 <span data-ttu-id="11b03-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11b03-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11b03-118">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="11b03-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="11b03-119">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="11b03-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11b03-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11b03-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11b03-121">Note</span><span class="sxs-lookup"><span data-stu-id="11b03-121">Remarks</span></span>  
 <span data-ttu-id="11b03-122">La firma con nome sicuro di un assembly è costituita dal nome del testo, dalla versione, dalle impostazioni cultura e dal token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="11b03-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="11b03-123">Se la funzione `StrongNameCompareAssemblies` non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="11b03-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11b03-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11b03-124">See also</span></span>

- [<span data-ttu-id="11b03-125">Metodo StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="11b03-125">StrongNameCompareAssemblies Method</span></span>](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="11b03-126">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="11b03-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

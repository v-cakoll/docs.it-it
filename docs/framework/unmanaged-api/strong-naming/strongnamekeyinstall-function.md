---
title: Funzione StrongNameKeyInstall
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 353898b72f41acd0c49a43ff05e54f61b99444c4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799002"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="44c5f-102">Funzione StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="44c5f-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="44c5f-103">Importa una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="44c5f-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="44c5f-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="44c5f-104">This function has been deprecated.</span></span> <span data-ttu-id="44c5f-105">Usare invece il metodo [ICLRStrongName:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) .</span><span class="sxs-lookup"><span data-stu-id="44c5f-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="44c5f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44c5f-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="44c5f-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="44c5f-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="44c5f-108">in Nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="44c5f-108">[in] The name of the key container.</span></span> <span data-ttu-id="44c5f-109">`wszKeyContainer`deve essere una stringa non vuota.</span><span class="sxs-lookup"><span data-stu-id="44c5f-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="44c5f-110">in Coppia di chiavi binarie.</span><span class="sxs-lookup"><span data-stu-id="44c5f-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="44c5f-111">in Dimensione, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="44c5f-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="44c5f-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="44c5f-112">Return Value</span></span>

<span data-ttu-id="44c5f-113">`true`al completamento; in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="44c5f-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="44c5f-114">Note</span><span class="sxs-lookup"><span data-stu-id="44c5f-114">Remarks</span></span>

<span data-ttu-id="44c5f-115">Usare la funzione [StrongNameKeyDelete](strongnamekeydelete-function.md) per eliminare il contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="44c5f-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="44c5f-116">Se la `StrongNameKeyInstall` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="44c5f-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="44c5f-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="44c5f-117">Requirements</span></span>

<span data-ttu-id="44c5f-118">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44c5f-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="44c5f-119">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="44c5f-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="44c5f-120">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="44c5f-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="44c5f-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44c5f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="44c5f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44c5f-122">See also</span></span>

- [<span data-ttu-id="44c5f-123">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="44c5f-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="44c5f-124">Metodo StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="44c5f-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="44c5f-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="44c5f-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

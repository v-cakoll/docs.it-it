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
ms.openlocfilehash: 9e441d4da64e9704fbda2368d2b07289aaea610a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125205"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="ea6b4-102">Funzione StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="ea6b4-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="ea6b4-103">Importa una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="ea6b4-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="ea6b4-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="ea6b4-104">This function has been deprecated.</span></span> <span data-ttu-id="ea6b4-105">Usare invece il metodo [ICLRStrongName:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ea6b4-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="ea6b4-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea6b4-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="ea6b4-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea6b4-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="ea6b4-108">in Nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="ea6b4-108">[in] The name of the key container.</span></span> <span data-ttu-id="ea6b4-109">`wszKeyContainer` deve essere una stringa non vuota.</span><span class="sxs-lookup"><span data-stu-id="ea6b4-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="ea6b4-110">in Coppia di chiavi binarie.</span><span class="sxs-lookup"><span data-stu-id="ea6b4-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="ea6b4-111">in Dimensione, in byte, del `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="ea6b4-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="ea6b4-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ea6b4-112">Return Value</span></span>

<span data-ttu-id="ea6b4-113">`true` al completamento; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ea6b4-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea6b4-114">Note</span><span class="sxs-lookup"><span data-stu-id="ea6b4-114">Remarks</span></span>

<span data-ttu-id="ea6b4-115">Usare la funzione [StrongNameKeyDelete](strongnamekeydelete-function.md) per eliminare il contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="ea6b4-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="ea6b4-116">Se la funzione `StrongNameKeyInstall` non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="ea6b4-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="ea6b4-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea6b4-117">Requirements</span></span>

<span data-ttu-id="ea6b4-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea6b4-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ea6b4-119">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="ea6b4-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="ea6b4-120">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ea6b4-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="ea6b4-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea6b4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ea6b4-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea6b4-122">See also</span></span>

- [<span data-ttu-id="ea6b4-123">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="ea6b4-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="ea6b4-124">Metodo StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="ea6b4-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="ea6b4-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ea6b4-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

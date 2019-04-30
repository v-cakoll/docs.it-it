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
ms.openlocfilehash: 6b3fc69b2edf611383402b13555cf33be10dbad3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000389"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="f1c45-102">Funzione StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="f1c45-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="f1c45-103">Importa una coppia di chiavi pubblica/privata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="f1c45-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="f1c45-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="f1c45-104">This function has been deprecated.</span></span> <span data-ttu-id="f1c45-105">Usare la [StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="f1c45-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1c45-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1c45-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="f1c45-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1c45-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="f1c45-108">[in] Il nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="f1c45-108">[in] The name of the key container.</span></span> <span data-ttu-id="f1c45-109">`wszKeyContainer` deve essere una stringa non vuota.</span><span class="sxs-lookup"><span data-stu-id="f1c45-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="f1c45-110">[in] La coppia di chiavi binaria.</span><span class="sxs-lookup"><span data-stu-id="f1c45-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="f1c45-111">[in] Le dimensioni, in byte, di `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="f1c45-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="f1c45-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f1c45-112">Return Value</span></span>

<span data-ttu-id="f1c45-113">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f1c45-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1c45-114">Note</span><span class="sxs-lookup"><span data-stu-id="f1c45-114">Remarks</span></span>

<span data-ttu-id="f1c45-115">Usare la [StrongNameKeyDelete](strongnamekeydelete-function.md) (funzione) per eliminare il contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="f1c45-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="f1c45-116">Se il `StrongNameKeyInstall` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="f1c45-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="f1c45-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1c45-117">Requirements</span></span>

<span data-ttu-id="f1c45-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1c45-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="f1c45-119">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f1c45-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="f1c45-120">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f1c45-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="f1c45-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1c45-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f1c45-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1c45-122">See also</span></span>

- [<span data-ttu-id="f1c45-123">Metodo StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="f1c45-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="f1c45-124">Metodo StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="f1c45-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="f1c45-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f1c45-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
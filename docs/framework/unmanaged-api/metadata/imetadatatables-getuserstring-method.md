---
title: Metodo IMetaDataTables::GetUserString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
ms.openlocfilehash: 21ce66722e069573b651ada950b64ef6d97220fb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501144"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="7d472-102">Metodo IMetaDataTables::GetUserString</span><span class="sxs-lookup"><span data-stu-id="7d472-102">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="7d472-103">Ottiene la stringa hardcoded in corrispondenza dell'indice specificato nella colonna stringa nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="7d472-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d472-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d472-104">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="7d472-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7d472-105">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="7d472-106">in Valore di indice da cui verrà recuperata la stringa hardcoded.</span><span class="sxs-lookup"><span data-stu-id="7d472-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="7d472-107">out Puntatore alla dimensione di `ppData` .</span><span class="sxs-lookup"><span data-stu-id="7d472-107">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="7d472-108">out Puntatore a un puntatore alla stringa restituita.</span><span class="sxs-lookup"><span data-stu-id="7d472-108">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d472-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d472-109">Requirements</span></span>

<span data-ttu-id="7d472-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d472-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="7d472-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7d472-111">**Header:** Cor.h</span></span>

<span data-ttu-id="7d472-112">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7d472-112">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="7d472-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d472-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7d472-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d472-114">See also</span></span>

- [<span data-ttu-id="7d472-115">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="7d472-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="7d472-116">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="7d472-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

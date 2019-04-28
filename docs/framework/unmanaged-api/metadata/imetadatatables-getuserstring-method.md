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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0fefbab6b2ea9fbbfd90e03c41578a924f99c7a0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645201"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="cf695-102">Metodo IMetaDataTables::GetUserString</span><span class="sxs-lookup"><span data-stu-id="cf695-102">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="cf695-103">Ottiene la stringa a livello di codice in corrispondenza dell'indice specificato nella colonna stringa nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="cf695-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf695-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf695-104">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="cf695-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cf695-105">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="cf695-106">[in] Il valore di indice da cui sarà possibile recuperare la stringa hardcoded.</span><span class="sxs-lookup"><span data-stu-id="cf695-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="cf695-107">[out] Un puntatore alla dimensione del `ppData`.</span><span class="sxs-lookup"><span data-stu-id="cf695-107">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="cf695-108">[out] Un puntatore a un puntatore alla stringa restituita.</span><span class="sxs-lookup"><span data-stu-id="cf695-108">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="cf695-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf695-109">Requirements</span></span>

<span data-ttu-id="cf695-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf695-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="cf695-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cf695-111">**Header:** Cor.h</span></span>

<span data-ttu-id="cf695-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cf695-112">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="cf695-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf695-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cf695-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf695-114">See also</span></span>

- [<span data-ttu-id="cf695-115">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="cf695-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="cf695-116">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="cf695-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
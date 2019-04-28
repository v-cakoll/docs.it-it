---
title: Metodo EnumImportTypes
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d0aefea7345bc3bf37bdb8d13cb2cda19cfe527
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789955"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="d0bb2-102">Metodo EnumImportTypes</span><span class="sxs-lookup"><span data-stu-id="d0bb2-102">EnumImportTypes Method</span></span>

<span data-ttu-id="d0bb2-103">Enumera ogni tipo in ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="d0bb2-103">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="d0bb2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0bb2-104">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="d0bb2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d0bb2-105">Parameters</span></span>

`hEnum`\
<span data-ttu-id="d0bb2-106">Handle per l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="d0bb2-106">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="d0bb2-107">Numero massimo di tipi da recuperare.</span><span class="sxs-lookup"><span data-stu-id="d0bb2-107">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="d0bb2-108">Riceve i token dei tipi, non deve superare `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="d0bb2-108">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="d0bb2-109">Riceve il numero effettivo di tipo in `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="d0bb2-109">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="d0bb2-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d0bb2-110">Return Value</span></span>

<span data-ttu-id="d0bb2-111">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d0bb2-111">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="d0bb2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d0bb2-112">Requirements</span></span>

<span data-ttu-id="d0bb2-113">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="d0bb2-113">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="d0bb2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0bb2-114">See also</span></span>

- [<span data-ttu-id="d0bb2-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="d0bb2-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d0bb2-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="d0bb2-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d0bb2-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="d0bb2-117">ALink API</span></span>](index.md)
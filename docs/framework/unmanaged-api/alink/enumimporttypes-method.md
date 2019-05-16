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
ms.openlocfilehash: 0cd154ac90418dd0f6f476151686ff670c01c98c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632239"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="520c8-102">Metodo EnumImportTypes</span><span class="sxs-lookup"><span data-stu-id="520c8-102">EnumImportTypes Method</span></span>

<span data-ttu-id="520c8-103">Enumera ogni tipo in ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="520c8-103">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="520c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="520c8-104">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="520c8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="520c8-105">Parameters</span></span>

`hEnum`\
<span data-ttu-id="520c8-106">Handle per l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="520c8-106">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="520c8-107">Numero massimo di tipi da recuperare.</span><span class="sxs-lookup"><span data-stu-id="520c8-107">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="520c8-108">Riceve i token dei tipi, non deve superare `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="520c8-108">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="520c8-109">Riceve il numero effettivo di tipo in `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="520c8-109">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="520c8-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="520c8-110">Return Value</span></span>

<span data-ttu-id="520c8-111">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="520c8-111">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="520c8-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="520c8-112">Requirements</span></span>

<span data-ttu-id="520c8-113">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="520c8-113">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="520c8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="520c8-114">See also</span></span>

- [<span data-ttu-id="520c8-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="520c8-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="520c8-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="520c8-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="520c8-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="520c8-117">ALink API</span></span>](index.md)

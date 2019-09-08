---
title: Metodo GetScope
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3a0e42e9ffb99896bdd09dbbab65eafb40cafff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777212"
---
# <a name="getscope-method"></a><span data-ttu-id="c6028-102">Metodo GetScope</span><span class="sxs-lookup"><span data-stu-id="c6028-102">GetScope Method</span></span>
<span data-ttu-id="c6028-103">Ottiene un ambito di importazione.</span><span class="sxs-lookup"><span data-stu-id="c6028-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6028-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6028-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6028-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c6028-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c6028-106">ID univoco dell'assembly in cui eseguire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="c6028-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="c6028-107">ID univoco del file da cui eseguire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="c6028-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="c6028-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="c6028-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="c6028-109">Riceve l'interfaccia dell' [interfaccia IMetaDataImport](../metadata/imetadataimport-interface.md) per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="c6028-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6028-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c6028-110">Return Value</span></span>  
 <span data-ttu-id="c6028-111">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c6028-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6028-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6028-112">Requirements</span></span>  
 <span data-ttu-id="c6028-113">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="c6028-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6028-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6028-114">See also</span></span>

- [<span data-ttu-id="c6028-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="c6028-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c6028-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="c6028-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c6028-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="c6028-117">ALink API</span></span>](index.md)

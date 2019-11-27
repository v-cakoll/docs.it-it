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
ms.openlocfilehash: 078168ae8860f18ff6f811dcc972e3eb3c857e1d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447201"
---
# <a name="getscope-method"></a><span data-ttu-id="ae976-102">Metodo GetScope</span><span class="sxs-lookup"><span data-stu-id="ae976-102">GetScope Method</span></span>
<span data-ttu-id="ae976-103">Ottiene un ambito di importazione.</span><span class="sxs-lookup"><span data-stu-id="ae976-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae976-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae976-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae976-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae976-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ae976-106">ID univoco dell'assembly in cui eseguire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="ae976-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ae976-107">ID univoco del file da cui eseguire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="ae976-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="ae976-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="ae976-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="ae976-109">Riceve l'interfaccia dell' [interfaccia IMetaDataImport](../metadata/imetadataimport-interface.md) per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="ae976-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae976-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ae976-110">Return Value</span></span>  
 <span data-ttu-id="ae976-111">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ae976-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae976-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae976-112">Requirements</span></span>  
 <span data-ttu-id="ae976-113">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="ae976-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae976-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae976-114">See also</span></span>

- [<span data-ttu-id="ae976-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="ae976-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ae976-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="ae976-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ae976-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="ae976-117">ALink API</span></span>](index.md)

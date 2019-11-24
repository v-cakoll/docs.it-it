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
# <a name="getscope-method"></a><span data-ttu-id="f2539-102">Metodo GetScope</span><span class="sxs-lookup"><span data-stu-id="f2539-102">GetScope Method</span></span>
<span data-ttu-id="f2539-103">Gets an import scope.</span><span class="sxs-lookup"><span data-stu-id="f2539-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2539-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2539-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2539-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f2539-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f2539-106">Unique ID of assembly to import to.</span><span class="sxs-lookup"><span data-stu-id="f2539-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f2539-107">Unique ID of the file to import from.</span><span class="sxs-lookup"><span data-stu-id="f2539-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="f2539-108">Zero-based scope to import.</span><span class="sxs-lookup"><span data-stu-id="f2539-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="f2539-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span><span class="sxs-lookup"><span data-stu-id="f2539-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2539-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f2539-110">Return Value</span></span>  
 <span data-ttu-id="f2539-111">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="f2539-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2539-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2539-112">Requirements</span></span>  
 <span data-ttu-id="f2539-113">Requires alink.h</span><span class="sxs-lookup"><span data-stu-id="f2539-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2539-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2539-114">See also</span></span>

- [<span data-ttu-id="f2539-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="f2539-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f2539-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="f2539-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f2539-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="f2539-117">ALink API</span></span>](index.md)

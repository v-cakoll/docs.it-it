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
ms.openlocfilehash: 571612796d4e66be9dd8469d748c2380c839ddfa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165783"
---
# <a name="getscope-method"></a><span data-ttu-id="74621-102">Metodo GetScope</span><span class="sxs-lookup"><span data-stu-id="74621-102">GetScope Method</span></span>
<span data-ttu-id="74621-103">Ottiene un ambito di importazione.</span><span class="sxs-lookup"><span data-stu-id="74621-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74621-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74621-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="74621-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74621-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="74621-106">ID univoco dell'assembly da importare.</span><span class="sxs-lookup"><span data-stu-id="74621-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="74621-107">ID univoco del file da importare da.</span><span class="sxs-lookup"><span data-stu-id="74621-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="74621-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="74621-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="74621-109">Riceve [interfaccia di IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="74621-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74621-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="74621-110">Return Value</span></span>  
 <span data-ttu-id="74621-111">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="74621-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74621-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74621-112">Requirements</span></span>  
 <span data-ttu-id="74621-113">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="74621-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74621-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74621-114">See also</span></span>

- [<span data-ttu-id="74621-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="74621-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="74621-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="74621-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="74621-117">API Alink</span><span class="sxs-lookup"><span data-stu-id="74621-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

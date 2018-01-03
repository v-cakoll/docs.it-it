---
title: GetScope Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetScope
api_location: alink.dll
api_type: COM
f1_keywords: GetScope
helpviewer_keywords: GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4cb51efc3f431dac4a10cc7582e2b43500ccba15
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getscope-method1"></a><span data-ttu-id="d931e-102">GetScope Method1</span><span class="sxs-lookup"><span data-stu-id="d931e-102">GetScope Method1</span></span>
<span data-ttu-id="d931e-103">Ottiene un ambito di importazione.</span><span class="sxs-lookup"><span data-stu-id="d931e-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d931e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d931e-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d931e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d931e-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d931e-106">ID univoco dell'assembly da importare.</span><span class="sxs-lookup"><span data-stu-id="d931e-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d931e-107">ID univoco del file da importare.</span><span class="sxs-lookup"><span data-stu-id="d931e-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="d931e-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="d931e-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="d931e-109">Riceve [interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="d931e-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d931e-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d931e-110">Return Value</span></span>  
 <span data-ttu-id="d931e-111">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="d931e-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d931e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d931e-112">Requirements</span></span>  
 <span data-ttu-id="d931e-113">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="d931e-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d931e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d931e-114">See Also</span></span>  
 [<span data-ttu-id="d931e-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="d931e-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d931e-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="d931e-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d931e-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="d931e-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

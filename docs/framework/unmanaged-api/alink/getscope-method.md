---
title: GetScope Method1
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
ms.openlocfilehash: e2746073fbc6adfd7090aa9b3cc38e46c4411744
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400185"
---
# <a name="getscope-method1"></a><span data-ttu-id="eb723-102">GetScope Method1</span><span class="sxs-lookup"><span data-stu-id="eb723-102">GetScope Method1</span></span>
<span data-ttu-id="eb723-103">Ottiene un ambito di importazione.</span><span class="sxs-lookup"><span data-stu-id="eb723-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb723-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb723-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb723-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eb723-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="eb723-106">ID univoco dell'assembly da importare.</span><span class="sxs-lookup"><span data-stu-id="eb723-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="eb723-107">ID univoco del file da importare.</span><span class="sxs-lookup"><span data-stu-id="eb723-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="eb723-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="eb723-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="eb723-109">Riceve [interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="eb723-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb723-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="eb723-110">Return Value</span></span>  
 <span data-ttu-id="eb723-111">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="eb723-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb723-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eb723-112">Requirements</span></span>  
 <span data-ttu-id="eb723-113">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="eb723-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb723-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb723-114">See Also</span></span>  
 [<span data-ttu-id="eb723-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="eb723-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="eb723-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="eb723-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="eb723-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="eb723-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

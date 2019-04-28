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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789818"
---
# <a name="getscope-method"></a><span data-ttu-id="9a5ed-102">Metodo GetScope</span><span class="sxs-lookup"><span data-stu-id="9a5ed-102">GetScope Method</span></span>
<span data-ttu-id="9a5ed-103">Ottiene un ambito di importazione.</span><span class="sxs-lookup"><span data-stu-id="9a5ed-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a5ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a5ed-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a5ed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a5ed-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9a5ed-106">ID univoco dell'assembly da importare.</span><span class="sxs-lookup"><span data-stu-id="9a5ed-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9a5ed-107">ID univoco del file da importare da.</span><span class="sxs-lookup"><span data-stu-id="9a5ed-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="9a5ed-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="9a5ed-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="9a5ed-109">Riceve [interfaccia di IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="9a5ed-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a5ed-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9a5ed-110">Return Value</span></span>  
 <span data-ttu-id="9a5ed-111">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9a5ed-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a5ed-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a5ed-112">Requirements</span></span>  
 <span data-ttu-id="9a5ed-113">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="9a5ed-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a5ed-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a5ed-114">See also</span></span>

- [<span data-ttu-id="9a5ed-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="9a5ed-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="9a5ed-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="9a5ed-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="9a5ed-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="9a5ed-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

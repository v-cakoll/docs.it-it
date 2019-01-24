---
title: Metodo1 GetScope
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
ms.openlocfilehash: 782697536f5e01fa29830a64e47d960a47fe4eae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663141"
---
# <a name="getscope-method1"></a><span data-ttu-id="1c4b7-102">Metodo1 GetScope</span><span class="sxs-lookup"><span data-stu-id="1c4b7-102">GetScope Method1</span></span>
<span data-ttu-id="1c4b7-103">Ottiene un ambito di importazione.</span><span class="sxs-lookup"><span data-stu-id="1c4b7-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c4b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c4b7-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c4b7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1c4b7-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1c4b7-106">ID univoco dell'assembly da importare.</span><span class="sxs-lookup"><span data-stu-id="1c4b7-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1c4b7-107">ID univoco del file da importare da.</span><span class="sxs-lookup"><span data-stu-id="1c4b7-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="1c4b7-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="1c4b7-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="1c4b7-109">Riceve [interfaccia di IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="1c4b7-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c4b7-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1c4b7-110">Return Value</span></span>  
 <span data-ttu-id="1c4b7-111">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1c4b7-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c4b7-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c4b7-112">Requirements</span></span>  
 <span data-ttu-id="1c4b7-113">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="1c4b7-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c4b7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c4b7-114">See also</span></span>
- [<span data-ttu-id="1c4b7-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="1c4b7-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1c4b7-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="1c4b7-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1c4b7-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="1c4b7-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

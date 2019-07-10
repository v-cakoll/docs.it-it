---
title: Metodo GetScope2
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c0abc63610f3f1ed6e8a556c44ee15edc1ea20b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741837"
---
# <a name="getscope2-method"></a><span data-ttu-id="e52a5-102">Metodo GetScope2</span><span class="sxs-lookup"><span data-stu-id="e52a5-102">GetScope2 Method</span></span>
<span data-ttu-id="e52a5-103">Ottiene un ambito di importazione.</span><span class="sxs-lookup"><span data-stu-id="e52a5-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e52a5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e52a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="e52a5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e52a5-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e52a5-106">ID dell'assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e52a5-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="e52a5-107">ID del file da cui importare.</span><span class="sxs-lookup"><span data-stu-id="e52a5-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="e52a5-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="e52a5-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="e52a5-109">Riceve il puntatore alla [interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interfaccia per l'ambito indicato.</span><span class="sxs-lookup"><span data-stu-id="e52a5-109">Receives pointer to [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e52a5-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e52a5-110">Return Value</span></span>  
 <span data-ttu-id="e52a5-111">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e52a5-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e52a5-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e52a5-112">Requirements</span></span>  
 <span data-ttu-id="e52a5-113">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="e52a5-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e52a5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e52a5-114">See also</span></span>

- [<span data-ttu-id="e52a5-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="e52a5-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e52a5-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="e52a5-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e52a5-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="e52a5-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

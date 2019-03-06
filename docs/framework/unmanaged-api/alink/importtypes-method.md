---
title: Metodo ImportTypes
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92dfc2bec33501a5cd9ca6b4ec4c3629b6d89946
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487954"
---
# <a name="importtypes-method"></a><span data-ttu-id="b6cfd-102">Metodo ImportTypes</span><span class="sxs-lookup"><span data-stu-id="b6cfd-102">ImportTypes Method</span></span>
<span data-ttu-id="b6cfd-103">Avvia l'importazione di tipi da ogni ambito importato attraverso [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="b6cfd-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6cfd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6cfd-104">Syntax</span></span>  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6cfd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b6cfd-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b6cfd-106">ID dell'assembly da importare.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="b6cfd-107">ID del file da importare da.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="b6cfd-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="b6cfd-109">Riceve l'handle di enumeratore per i tipi in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="b6cfd-110">Facoltativamente, riceve [interfaccia di IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="b6cfd-111">Facoltativamente, riceve il numero di tipi nell'ambito indicato.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6cfd-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b6cfd-112">Return Value</span></span>  
 <span data-ttu-id="b6cfd-113">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b6cfd-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6cfd-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6cfd-114">Requirements</span></span>  
 <span data-ttu-id="b6cfd-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="b6cfd-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6cfd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6cfd-116">See also</span></span>
- [<span data-ttu-id="b6cfd-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="b6cfd-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b6cfd-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="b6cfd-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b6cfd-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="b6cfd-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

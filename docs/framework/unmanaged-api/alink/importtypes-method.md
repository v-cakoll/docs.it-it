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
ms.openlocfilehash: 321038a148c27086ca499e2f448eb50cb93525ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405512"
---
# <a name="importtypes-method"></a><span data-ttu-id="25cc9-102">Metodo ImportTypes</span><span class="sxs-lookup"><span data-stu-id="25cc9-102">ImportTypes Method</span></span>
<span data-ttu-id="25cc9-103">Avvia l'importazione di tipi da ogni ambito importato tramite [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="25cc9-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25cc9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25cc9-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="25cc9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="25cc9-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="25cc9-106">ID dell'assembly da importare.</span><span class="sxs-lookup"><span data-stu-id="25cc9-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="25cc9-107">ID del file da importare.</span><span class="sxs-lookup"><span data-stu-id="25cc9-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="25cc9-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="25cc9-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="25cc9-109">Riceve l'handle dell'enumeratore per i tipi in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="25cc9-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="25cc9-110">Facoltativamente riceve [interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="25cc9-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="25cc9-111">Facoltativamente, riceve il numero dei tipi nell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="25cc9-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25cc9-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="25cc9-112">Return Value</span></span>  
 <span data-ttu-id="25cc9-113">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="25cc9-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25cc9-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25cc9-114">Requirements</span></span>  
 <span data-ttu-id="25cc9-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="25cc9-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25cc9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25cc9-116">See Also</span></span>  
 [<span data-ttu-id="25cc9-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="25cc9-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="25cc9-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="25cc9-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="25cc9-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="25cc9-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

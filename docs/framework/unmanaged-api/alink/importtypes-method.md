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
ms.openlocfilehash: 622e57aedf6c49e95dc2d7e40ba598361b3e6a26
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222861"
---
# <a name="importtypes-method"></a><span data-ttu-id="b80cf-102">Metodo ImportTypes</span><span class="sxs-lookup"><span data-stu-id="b80cf-102">ImportTypes Method</span></span>
<span data-ttu-id="b80cf-103">Avvia l'importazione di tipi da ogni ambito importato attraverso [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="b80cf-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b80cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b80cf-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b80cf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b80cf-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b80cf-106">ID dell'assembly da importare.</span><span class="sxs-lookup"><span data-stu-id="b80cf-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="b80cf-107">ID del file da importare da.</span><span class="sxs-lookup"><span data-stu-id="b80cf-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="b80cf-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="b80cf-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="b80cf-109">Riceve l'handle di enumeratore per i tipi in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="b80cf-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="b80cf-110">Facoltativamente, riceve [interfaccia di IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b80cf-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="b80cf-111">Facoltativamente, riceve il numero di tipi nell'ambito indicato.</span><span class="sxs-lookup"><span data-stu-id="b80cf-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b80cf-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b80cf-112">Return Value</span></span>  
 <span data-ttu-id="b80cf-113">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b80cf-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b80cf-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b80cf-114">Requirements</span></span>  
 <span data-ttu-id="b80cf-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="b80cf-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b80cf-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b80cf-116">See also</span></span>

- [<span data-ttu-id="b80cf-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="b80cf-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b80cf-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="b80cf-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b80cf-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="b80cf-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

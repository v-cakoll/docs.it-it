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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61753453"
---
# <a name="importtypes-method"></a><span data-ttu-id="975ca-102">Metodo ImportTypes</span><span class="sxs-lookup"><span data-stu-id="975ca-102">ImportTypes Method</span></span>
<span data-ttu-id="975ca-103">Avvia l'importazione di tipi da ogni ambito importato attraverso [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="975ca-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="975ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="975ca-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="975ca-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="975ca-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="975ca-106">ID dell'assembly da importare.</span><span class="sxs-lookup"><span data-stu-id="975ca-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="975ca-107">ID del file da importare da.</span><span class="sxs-lookup"><span data-stu-id="975ca-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="975ca-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="975ca-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="975ca-109">Riceve l'handle di enumeratore per i tipi in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="975ca-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="975ca-110">Facoltativamente, riceve [interfaccia di IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="975ca-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="975ca-111">Facoltativamente, riceve il numero di tipi nell'ambito indicato.</span><span class="sxs-lookup"><span data-stu-id="975ca-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="975ca-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="975ca-112">Return Value</span></span>  
 <span data-ttu-id="975ca-113">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="975ca-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="975ca-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="975ca-114">Requirements</span></span>  
 <span data-ttu-id="975ca-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="975ca-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="975ca-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="975ca-116">See also</span></span>

- [<span data-ttu-id="975ca-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="975ca-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="975ca-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="975ca-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="975ca-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="975ca-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

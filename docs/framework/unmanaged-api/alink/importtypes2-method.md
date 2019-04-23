---
title: Metodo ImportTypes2
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f14822a58f3982d6f9fee1328c10b960657c056f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098468"
---
# <a name="importtypes2-method"></a><span data-ttu-id="f311b-102">Metodo ImportTypes2</span><span class="sxs-lookup"><span data-stu-id="f311b-102">ImportTypes2 Method</span></span>
<span data-ttu-id="f311b-103">Avvia l'importazione di tipi.</span><span class="sxs-lookup"><span data-stu-id="f311b-103">Initiates the import of types.</span></span> <span data-ttu-id="f311b-104">Chiamare questo metodo per avviare l'importazione di tipi da ogni ambito importato attraverso [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="f311b-104">Call this method to begin importing types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f311b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f311b-105">Syntax</span></span>  
  
```  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f311b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f311b-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f311b-107">ID dell'assembly in cui si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="f311b-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f311b-108">ID del file dal quale si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="f311b-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="f311b-109">Ambito in base zero da cui importare.</span><span class="sxs-lookup"><span data-stu-id="f311b-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="f311b-110">Riceve l'handle di enumeratore per i tipi nell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="f311b-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="f311b-111">Facoltativamente, riceve [interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f311b-111">Optionally receives [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="f311b-112">Facoltativamente, riceve il numero di tipi nell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="f311b-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f311b-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f311b-113">Return Value</span></span>  
 <span data-ttu-id="f311b-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f311b-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f311b-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f311b-115">Requirements</span></span>  
 <span data-ttu-id="f311b-116">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="f311b-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f311b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f311b-117">See also</span></span>

- [<span data-ttu-id="f311b-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="f311b-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f311b-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="f311b-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f311b-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="f311b-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

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
ms.openlocfilehash: 76d2b163f959111923bffb1348890f6fbb29828e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445682"
---
# <a name="importtypes-method"></a><span data-ttu-id="6bd26-102">Metodo ImportTypes</span><span class="sxs-lookup"><span data-stu-id="6bd26-102">ImportTypes Method</span></span>
<span data-ttu-id="6bd26-103">Avvia l'importazione di tipi da ogni ambito importato tramite il [metodo ImportFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="6bd26-103">Initiates the importing of types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bd26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bd26-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bd26-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6bd26-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6bd26-106">ID dell'assembly in cui eseguire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="6bd26-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="6bd26-107">ID del file da cui eseguire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="6bd26-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="6bd26-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="6bd26-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="6bd26-109">Riceve l'handle dell'enumeratore per i tipi in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="6bd26-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="6bd26-110">Riceve facoltativamente l'interfaccia dell' [interfaccia IMetaDataImport](../metadata/imetadataimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6bd26-110">Optionally receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="6bd26-111">Riceve facoltativamente il numero di tipi nell'ambito indicato.</span><span class="sxs-lookup"><span data-stu-id="6bd26-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bd26-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6bd26-112">Return Value</span></span>  
 <span data-ttu-id="6bd26-113">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="6bd26-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bd26-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6bd26-114">Requirements</span></span>  
 <span data-ttu-id="6bd26-115">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="6bd26-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bd26-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bd26-116">See also</span></span>

- [<span data-ttu-id="6bd26-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="6bd26-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6bd26-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="6bd26-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6bd26-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="6bd26-119">ALink API</span></span>](index.md)

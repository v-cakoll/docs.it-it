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
ms.openlocfilehash: f19dd114925ed1fd12bcc0056411c3e3d4181215
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777091"
---
# <a name="importtypes-method"></a><span data-ttu-id="92f9a-102">Metodo ImportTypes</span><span class="sxs-lookup"><span data-stu-id="92f9a-102">ImportTypes Method</span></span>
<span data-ttu-id="92f9a-103">Avvia l'importazione di tipi da ogni ambito importato tramite il [metodo ImportFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="92f9a-103">Initiates the importing of types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92f9a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92f9a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="92f9a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="92f9a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="92f9a-106">ID dell'assembly in cui eseguire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="92f9a-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="92f9a-107">ID del file da cui eseguire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="92f9a-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="92f9a-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="92f9a-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="92f9a-109">Riceve l'handle dell'enumeratore per i tipi in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="92f9a-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="92f9a-110">Riceve facoltativamente l'interfaccia dell' [interfaccia IMetaDataImport](../metadata/imetadataimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="92f9a-110">Optionally receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="92f9a-111">Riceve facoltativamente il numero di tipi nell'ambito indicato.</span><span class="sxs-lookup"><span data-stu-id="92f9a-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92f9a-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="92f9a-112">Return Value</span></span>  
 <span data-ttu-id="92f9a-113">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="92f9a-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92f9a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="92f9a-114">Requirements</span></span>  
 <span data-ttu-id="92f9a-115">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="92f9a-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92f9a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92f9a-116">See also</span></span>

- [<span data-ttu-id="92f9a-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="92f9a-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="92f9a-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="92f9a-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="92f9a-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="92f9a-119">ALink API</span></span>](index.md)

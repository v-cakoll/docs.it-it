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
ms.openlocfilehash: ce09eca30e1edb9e1afc02216a07955a5fed4fd2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787264"
---
# <a name="importtypes2-method"></a><span data-ttu-id="0e016-102">Metodo ImportTypes2</span><span class="sxs-lookup"><span data-stu-id="0e016-102">ImportTypes2 Method</span></span>
<span data-ttu-id="0e016-103">Avvia l'importazione di tipi.</span><span class="sxs-lookup"><span data-stu-id="0e016-103">Initiates the import of types.</span></span> <span data-ttu-id="0e016-104">Chiamare questo metodo per iniziare a importare i tipi da ogni ambito importato tramite il [metodo ImportFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="0e016-104">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e016-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e016-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e016-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0e016-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0e016-107">ID dell'assembly in cui eseguire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="0e016-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="0e016-108">ID del file da importare.</span><span class="sxs-lookup"><span data-stu-id="0e016-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="0e016-109">Ambito in base zero da cui eseguire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="0e016-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="0e016-110">Riceve l'handle dell'enumeratore per i tipi nell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="0e016-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="0e016-111">Riceve facoltativamente l'interfaccia dell' [interfaccia IMetaDataImport2](../metadata/imetadataimport2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e016-111">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="0e016-112">Riceve facoltativamente il numero di tipi nell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="0e016-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e016-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0e016-113">Return Value</span></span>  
 <span data-ttu-id="0e016-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0e016-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e016-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e016-115">Requirements</span></span>  
 <span data-ttu-id="0e016-116">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="0e016-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e016-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e016-117">See also</span></span>

- [<span data-ttu-id="0e016-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="0e016-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0e016-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="0e016-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0e016-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="0e016-120">ALink API</span></span>](index.md)

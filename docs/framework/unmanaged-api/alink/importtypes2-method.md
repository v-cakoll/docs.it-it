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
ms.openlocfilehash: 8dae903ab76ab83ac0818c4bc4a76e81094bdf65
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445672"
---
# <a name="importtypes2-method"></a><span data-ttu-id="a478a-102">Metodo ImportTypes2</span><span class="sxs-lookup"><span data-stu-id="a478a-102">ImportTypes2 Method</span></span>
<span data-ttu-id="a478a-103">Avvia l'importazione di tipi.</span><span class="sxs-lookup"><span data-stu-id="a478a-103">Initiates the import of types.</span></span> <span data-ttu-id="a478a-104">Chiamare questo metodo per iniziare a importare i tipi da ogni ambito importato tramite il [metodo ImportFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="a478a-104">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a478a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a478a-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a478a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a478a-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a478a-107">ID dell'assembly in cui eseguire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="a478a-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a478a-108">ID del file da importare.</span><span class="sxs-lookup"><span data-stu-id="a478a-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="a478a-109">Ambito in base zero da cui eseguire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="a478a-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="a478a-110">Riceve l'handle dell'enumeratore per i tipi nell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="a478a-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="a478a-111">Riceve facoltativamente l'interfaccia dell' [interfaccia IMetaDataImport2](../metadata/imetadataimport2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a478a-111">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="a478a-112">Riceve facoltativamente il numero di tipi nell'ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="a478a-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a478a-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a478a-113">Return Value</span></span>  
 <span data-ttu-id="a478a-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a478a-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a478a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a478a-115">Requirements</span></span>  
 <span data-ttu-id="a478a-116">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="a478a-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a478a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a478a-117">See also</span></span>

- [<span data-ttu-id="a478a-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="a478a-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a478a-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="a478a-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a478a-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="a478a-120">ALink API</span></span>](index.md)

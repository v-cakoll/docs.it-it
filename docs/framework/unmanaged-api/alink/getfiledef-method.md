---
title: Metodo GetFileDef
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a51e8c83d0949f68a41f6a4e10396adbc4f3c9c1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741885"
---
# <a name="getfiledef-method"></a><span data-ttu-id="be1db-102">Metodo GetFileDef</span><span class="sxs-lookup"><span data-stu-id="be1db-102">GetFileDef Method</span></span>
<span data-ttu-id="be1db-103">Recupera il token FileDef effettivo utilizzato nei metadati (anziché i token assegnati da ALink).</span><span class="sxs-lookup"><span data-stu-id="be1db-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be1db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be1db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="be1db-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="be1db-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="be1db-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="be1db-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="be1db-107">Token del file aggiunto come recuperati dal metodo AddFile o AddImport (metodo).</span><span class="sxs-lookup"><span data-stu-id="be1db-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="be1db-108">Riceve il token FileDef.</span><span class="sxs-lookup"><span data-stu-id="be1db-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be1db-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="be1db-109">Return Value</span></span>  
 <span data-ttu-id="be1db-110">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="be1db-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be1db-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be1db-111">Requirements</span></span>  
 <span data-ttu-id="be1db-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="be1db-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be1db-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be1db-113">See also</span></span>

- [<span data-ttu-id="be1db-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="be1db-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="be1db-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="be1db-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="be1db-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="be1db-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

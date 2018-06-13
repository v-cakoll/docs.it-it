---
title: Metodo GetScope2
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ed9645c5111e7260010df74554825ffd8d427e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402145"
---
# <a name="getscope2-method"></a><span data-ttu-id="d4c9f-102">Metodo GetScope2</span><span class="sxs-lookup"><span data-stu-id="d4c9f-102">GetScope2 Method</span></span>
<span data-ttu-id="d4c9f-103">Ottiene un ambito di importazione.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4c9f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4c9f-104">Syntax</span></span>  
  
```  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4c9f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4c9f-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d4c9f-106">ID dell'assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d4c9f-107">ID del file da cui importare.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="d4c9f-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="d4c9f-109">Riceve il puntatore a [interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interfaccia per l'ambito indicato.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-109">Receives pointer to [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4c9f-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d4c9f-110">Return Value</span></span>  
 <span data-ttu-id="d4c9f-111">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4c9f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4c9f-112">Requirements</span></span>  
 <span data-ttu-id="d4c9f-113">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4c9f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4c9f-114">See Also</span></span>  
 [<span data-ttu-id="d4c9f-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="d4c9f-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d4c9f-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="d4c9f-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d4c9f-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="d4c9f-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

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
ms.openlocfilehash: a3c6b9e1239dc1baed9428d4fe967eb8274a9304
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206031"
---
# <a name="getscope2-method"></a><span data-ttu-id="a8985-102">Metodo GetScope2</span><span class="sxs-lookup"><span data-stu-id="a8985-102">GetScope2 Method</span></span>
<span data-ttu-id="a8985-103">Ottiene un ambito di importazione.</span><span class="sxs-lookup"><span data-stu-id="a8985-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8985-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8985-104">Syntax</span></span>  
  
```  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="a8985-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a8985-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a8985-106">ID dell'assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a8985-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a8985-107">ID del file da cui importare.</span><span class="sxs-lookup"><span data-stu-id="a8985-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="a8985-108">Ambito in base zero da importare.</span><span class="sxs-lookup"><span data-stu-id="a8985-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="a8985-109">Riceve il puntatore alla [interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interfaccia per l'ambito indicato.</span><span class="sxs-lookup"><span data-stu-id="a8985-109">Receives pointer to [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8985-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a8985-110">Return Value</span></span>  
 <span data-ttu-id="a8985-111">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a8985-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8985-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a8985-112">Requirements</span></span>  
 <span data-ttu-id="a8985-113">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="a8985-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8985-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8985-114">See also</span></span>

- [<span data-ttu-id="a8985-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="a8985-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a8985-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="a8985-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a8985-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="a8985-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

---
title: Metodo ExportNestedType
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7dfaedad48291ac09f6959bc7b314ae0d9da76e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742051"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="f3955-102">Metodo ExportNestedType</span><span class="sxs-lookup"><span data-stu-id="f3955-102">ExportNestedType Method</span></span>
<span data-ttu-id="f3955-103">Specifica i tipi annidati come esportabile.</span><span class="sxs-lookup"><span data-stu-id="f3955-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="f3955-104">Il [metodo ExportType](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) possono anche esportazione dei tipi nidificati, ma questo metodo è più veloce.</span><span class="sxs-lookup"><span data-stu-id="f3955-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3955-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3955-105">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="f3955-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f3955-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f3955-107">ID dell'assembly da cui esportare.</span><span class="sxs-lookup"><span data-stu-id="f3955-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f3955-108">Token file o l'Assembly del file che definisce il tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="f3955-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="f3955-109">Tipo di token del tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="f3955-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="f3955-110">Token del tipo padre.</span><span class="sxs-lookup"><span data-stu-id="f3955-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="f3955-111">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="f3955-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f3955-112">`ComType` ad esempio i flag `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="f3955-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="f3955-113">Questo valore può essere passato a [metodo DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="f3955-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="f3955-114">Riceve il token del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="f3955-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3955-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f3955-115">Return Value</span></span>  
 <span data-ttu-id="f3955-116">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f3955-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3955-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3955-117">Requirements</span></span>  
 <span data-ttu-id="f3955-118">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="f3955-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3955-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3955-119">See also</span></span>

- [<span data-ttu-id="f3955-120">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="f3955-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f3955-121">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="f3955-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f3955-122">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="f3955-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

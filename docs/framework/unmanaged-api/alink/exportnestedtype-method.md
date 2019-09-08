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
ms.openlocfilehash: 570e48788a11045882ef546bf6bc22315c2a02b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777271"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="ba85c-102">Metodo ExportNestedType</span><span class="sxs-lookup"><span data-stu-id="ba85c-102">ExportNestedType Method</span></span>
<span data-ttu-id="ba85c-103">Specifica i tipi annidati come esportabili.</span><span class="sxs-lookup"><span data-stu-id="ba85c-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="ba85c-104">Il [Metodo ExportType](exporttype-method.md) può anche esportare tipi annidati, ma questo metodo è più veloce.</span><span class="sxs-lookup"><span data-stu-id="ba85c-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba85c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba85c-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ba85c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba85c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ba85c-107">ID dell'assembly da cui eseguire l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="ba85c-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ba85c-108">Token del file o assembly del file che definisce il tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="ba85c-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="ba85c-109">Token di tipo di tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="ba85c-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="ba85c-110">Token del tipo padre.</span><span class="sxs-lookup"><span data-stu-id="ba85c-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="ba85c-111">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="ba85c-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ba85c-112">`ComType`flag come `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="ba85c-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="ba85c-113">Questo valore può essere passato al [Metodo DefineExportedType](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="ba85c-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="ba85c-114">Riceve il token per il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="ba85c-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba85c-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ba85c-115">Return Value</span></span>  
 <span data-ttu-id="ba85c-116">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ba85c-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba85c-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba85c-117">Requirements</span></span>  
 <span data-ttu-id="ba85c-118">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="ba85c-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba85c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba85c-119">See also</span></span>

- [<span data-ttu-id="ba85c-120">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="ba85c-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ba85c-121">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="ba85c-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ba85c-122">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="ba85c-122">ALink API</span></span>](index.md)

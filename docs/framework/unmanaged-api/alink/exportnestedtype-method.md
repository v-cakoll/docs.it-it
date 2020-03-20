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
ms.openlocfilehash: 9ca2167e66ac3aa5bcc0e92ff357eed18d366c67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179408"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="8124c-102">Metodo ExportNestedType</span><span class="sxs-lookup"><span data-stu-id="8124c-102">ExportNestedType Method</span></span>
<span data-ttu-id="8124c-103">Specifica i tipi annidati come esportabili.</span><span class="sxs-lookup"><span data-stu-id="8124c-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="8124c-104">Il [ExportType metodo](exporttype-method.md) può anche esportare i tipi annidati, ma questo metodo è più veloce.</span><span class="sxs-lookup"><span data-stu-id="8124c-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8124c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8124c-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8124c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8124c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="8124c-107">ID dell'assembly da cui esportare.</span><span class="sxs-lookup"><span data-stu-id="8124c-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="8124c-108">Token di file o Assembly di file che definisce il tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="8124c-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="8124c-109">Token di tipo di tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="8124c-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="8124c-110">Token del tipo padre.</span><span class="sxs-lookup"><span data-stu-id="8124c-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="8124c-111">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="8124c-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8124c-112">`ComType`contrassegni `tdPublic` come `tdNested`o .</span><span class="sxs-lookup"><span data-stu-id="8124c-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="8124c-113">Questo valore può essere passato al [metodo DefineExportedType](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="8124c-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="8124c-114">Riceve il token per il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="8124c-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8124c-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8124c-115">Return Value</span></span>  
 <span data-ttu-id="8124c-116">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8124c-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8124c-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8124c-117">Requirements</span></span>  
 <span data-ttu-id="8124c-118">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="8124c-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8124c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8124c-119">See also</span></span>

- [<span data-ttu-id="8124c-120">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="8124c-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8124c-121">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="8124c-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="8124c-122">API Alink</span><span class="sxs-lookup"><span data-stu-id="8124c-122">ALink API</span></span>](index.md)

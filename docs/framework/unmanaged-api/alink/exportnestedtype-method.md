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
ms.openlocfilehash: fded6b95144d4088a2abc8dfcc4ef8eda331c34f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438429"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="ba092-102">Metodo ExportNestedType</span><span class="sxs-lookup"><span data-stu-id="ba092-102">ExportNestedType Method</span></span>
<span data-ttu-id="ba092-103">Specifica i tipi annidati come esportabili.</span><span class="sxs-lookup"><span data-stu-id="ba092-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="ba092-104">Il [Metodo ExportType](exporttype-method.md) può anche esportare tipi annidati, ma questo metodo è più veloce.</span><span class="sxs-lookup"><span data-stu-id="ba092-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba092-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba092-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ba092-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba092-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ba092-107">ID dell'assembly da cui eseguire l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="ba092-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ba092-108">Token del file o assembly del file che definisce il tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="ba092-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="ba092-109">Token di tipo di tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="ba092-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="ba092-110">Token del tipo padre.</span><span class="sxs-lookup"><span data-stu-id="ba092-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="ba092-111">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="ba092-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ba092-112">flag di `ComType` come `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="ba092-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="ba092-113">Questo valore può essere passato al [Metodo DefineExportedType](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="ba092-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="ba092-114">Riceve il token per il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="ba092-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba092-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ba092-115">Return Value</span></span>  
 <span data-ttu-id="ba092-116">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ba092-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba092-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba092-117">Requirements</span></span>  
 <span data-ttu-id="ba092-118">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="ba092-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba092-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba092-119">See also</span></span>

- [<span data-ttu-id="ba092-120">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="ba092-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ba092-121">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="ba092-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ba092-122">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="ba092-122">ALink API</span></span>](index.md)

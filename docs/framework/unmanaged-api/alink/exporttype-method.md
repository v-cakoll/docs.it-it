---
title: Metodo ExportType
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
ms.openlocfilehash: 84c41e467c57afd2562e7aa8dd72ce4796249667
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438563"
---
# <a name="exporttype-method"></a><span data-ttu-id="d1daa-102">Metodo ExportType</span><span class="sxs-lookup"><span data-stu-id="d1daa-102">ExportType Method</span></span>
<span data-ttu-id="d1daa-103">Specifica che un tipo può essere esportato.</span><span class="sxs-lookup"><span data-stu-id="d1daa-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1daa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1daa-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1daa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d1daa-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d1daa-106">ID dell'assembly da cui eseguire l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="d1daa-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d1daa-107">Token file o ID assembly del file che definisce il tipo esportabile.</span><span class="sxs-lookup"><span data-stu-id="d1daa-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="d1daa-108">Token di tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="d1daa-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="d1daa-109">Nome completo del tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="d1daa-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d1daa-110">flag di `ComType` come `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="d1daa-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="d1daa-111">Questo parametro può essere passato al [Metodo DefineExportedType](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="d1daa-111">This parameter may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="d1daa-112">Riceve il token per il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="d1daa-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1daa-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d1daa-113">Return Value</span></span>  
 <span data-ttu-id="d1daa-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d1daa-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1daa-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d1daa-115">Requirements</span></span>  
 <span data-ttu-id="d1daa-116">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="d1daa-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1daa-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1daa-117">See also</span></span>

- [<span data-ttu-id="d1daa-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="d1daa-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d1daa-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="d1daa-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d1daa-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="d1daa-120">ALink API</span></span>](index.md)

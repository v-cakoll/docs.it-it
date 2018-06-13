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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 958b56266b0d2dcc317204c39a1df56baabd83e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402483"
---
# <a name="exporttype-method"></a><span data-ttu-id="4540a-102">Metodo ExportType</span><span class="sxs-lookup"><span data-stu-id="4540a-102">ExportType Method</span></span>
<span data-ttu-id="4540a-103">Specifica che un tipo può essere esportato.</span><span class="sxs-lookup"><span data-stu-id="4540a-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4540a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4540a-104">Syntax</span></span>  
  
```  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4540a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4540a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4540a-106">ID dell'assembly da cui esportare.</span><span class="sxs-lookup"><span data-stu-id="4540a-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="4540a-107">Token o assembly ID del file che definisce il tipo esportabile.</span><span class="sxs-lookup"><span data-stu-id="4540a-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="4540a-108">Token di tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="4540a-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="4540a-109">Nome completo del tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="4540a-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4540a-110">`ComType` flag, ad esempio `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="4540a-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="4540a-111">Questo parametro può essere passato a [DefineExportedType (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="4540a-111">This parameter may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="4540a-112">Riceve il token del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="4540a-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4540a-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4540a-113">Return Value</span></span>  
 <span data-ttu-id="4540a-114">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="4540a-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4540a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4540a-115">Requirements</span></span>  
 <span data-ttu-id="4540a-116">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="4540a-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4540a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4540a-117">See Also</span></span>  
 [<span data-ttu-id="4540a-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="4540a-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="4540a-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="4540a-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="4540a-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="4540a-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

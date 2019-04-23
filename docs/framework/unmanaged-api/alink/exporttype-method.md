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
ms.openlocfilehash: 95ff27143453e7772b4a463fa66ca039bbb715fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226917"
---
# <a name="exporttype-method"></a><span data-ttu-id="1f698-102">Metodo ExportType</span><span class="sxs-lookup"><span data-stu-id="1f698-102">ExportType Method</span></span>
<span data-ttu-id="1f698-103">Specifica che un tipo può essere esportato.</span><span class="sxs-lookup"><span data-stu-id="1f698-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f698-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f698-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1f698-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1f698-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1f698-106">ID dell'assembly da cui esportare.</span><span class="sxs-lookup"><span data-stu-id="1f698-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1f698-107">Assembly o token ID di file che definisce il tipo può essere esportato.</span><span class="sxs-lookup"><span data-stu-id="1f698-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="1f698-108">Token del tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="1f698-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="1f698-109">Nome completo del tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="1f698-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1f698-110">`ComType` ad esempio i flag `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="1f698-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="1f698-111">Questo parametro può essere passato a [metodo DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="1f698-111">This parameter may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="1f698-112">Riceve il token del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="1f698-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f698-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1f698-113">Return Value</span></span>  
 <span data-ttu-id="1f698-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1f698-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f698-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1f698-115">Requirements</span></span>  
 <span data-ttu-id="1f698-116">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="1f698-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f698-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f698-117">See also</span></span>

- [<span data-ttu-id="1f698-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="1f698-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1f698-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="1f698-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1f698-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="1f698-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

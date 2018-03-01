---
title: Metodo ExportType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f9cc61d0bc32545b486f4472904b17ed0b59526e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="exporttype-method"></a><span data-ttu-id="ec135-102">Metodo ExportType</span><span class="sxs-lookup"><span data-stu-id="ec135-102">ExportType Method</span></span>
<span data-ttu-id="ec135-103">Specifica che un tipo può essere esportato.</span><span class="sxs-lookup"><span data-stu-id="ec135-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec135-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec135-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="ec135-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ec135-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ec135-106">ID dell'assembly da cui esportare.</span><span class="sxs-lookup"><span data-stu-id="ec135-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ec135-107">Token o assembly ID del file che definisce il tipo esportabile.</span><span class="sxs-lookup"><span data-stu-id="ec135-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="ec135-108">Token di tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="ec135-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="ec135-109">Nome completo del tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="ec135-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ec135-110">`ComType`flag come `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="ec135-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="ec135-111">Questo parametro può essere passato a [DefineExportedType (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="ec135-111">This parameter may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="ec135-112">Riceve il token del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="ec135-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec135-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ec135-113">Return Value</span></span>  
 <span data-ttu-id="ec135-114">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="ec135-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec135-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec135-115">Requirements</span></span>  
 <span data-ttu-id="ec135-116">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="ec135-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec135-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec135-117">See Also</span></span>  
 [<span data-ttu-id="ec135-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="ec135-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="ec135-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="ec135-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="ec135-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="ec135-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

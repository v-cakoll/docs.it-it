---
title: Metodo ExportTypeForwarder
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ExportTypeForwarder
api_location: alink.dll
api_type: COM
f1_keywords: ExportTypeForwarder
helpviewer_keywords: ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0f117d64673729113d917d700e3a26f9723b5a6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="3b371-102">Metodo ExportTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="3b371-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="3b371-103">Aggiunge un server d'inoltro per la tabella dei tipi dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="3b371-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b371-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b371-104">Syntax</span></span>  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b371-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3b371-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="3b371-106">Riferimento all'assembly a cui fa riferimento il server d'inoltro del tipo.</span><span class="sxs-lookup"><span data-stu-id="3b371-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="3b371-107">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="3b371-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3b371-108">`ComType`flag come `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="3b371-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="3b371-109">Questo valore può essere passato a [DefineExportedType (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="3b371-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="3b371-110">Riceve il token del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="3b371-110">Receives the token of the exported type.</span></span> <span data-ttu-id="3b371-111">Ciò è necessario solo per la creazione di tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="3b371-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b371-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3b371-112">Return Value</span></span>  
 <span data-ttu-id="3b371-113">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="3b371-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b371-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3b371-114">Requirements</span></span>  
 <span data-ttu-id="3b371-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="3b371-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b371-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b371-116">See Also</span></span>  
 [<span data-ttu-id="3b371-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="3b371-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="3b371-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="3b371-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="3b371-119">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="3b371-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

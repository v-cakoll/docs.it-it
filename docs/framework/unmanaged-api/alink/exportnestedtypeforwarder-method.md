---
title: Metodo ExportNestedTypeForwarder
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ExportNestedTypeForwarder
api_location: alink.dll
api_type: COM
f1_keywords: ExportNestedTypeForwarder
helpviewer_keywords: ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 41c0984e4439b89ddee2b55bbca7a098075d6bd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="d1f33-102">Metodo ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="d1f33-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="d1f33-103">Aggiunge un server d'inoltro di tipo per un tipo annidato per la tabella dei tipi dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="d1f33-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1f33-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1f33-104">Syntax</span></span>  
  
```  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1f33-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d1f33-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d1f33-106">ID dell'assembly da cui esportare.</span><span class="sxs-lookup"><span data-stu-id="d1f33-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d1f33-107">ID di token o l'assembly del file che definisce il tipo di file.</span><span class="sxs-lookup"><span data-stu-id="d1f33-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="d1f33-108">Token per il tipo.</span><span class="sxs-lookup"><span data-stu-id="d1f33-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="d1f33-109">Token di tipo padre.</span><span class="sxs-lookup"><span data-stu-id="d1f33-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="d1f33-110">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="d1f33-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d1f33-111">`ComType`flag come `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="d1f33-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="d1f33-112">Riceve il token del tipo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="d1f33-112">Receives token of export type.</span></span> <span data-ttu-id="d1f33-113">Ciò è necessario solo per la creazione di tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="d1f33-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1f33-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d1f33-114">Return Value</span></span>  
 <span data-ttu-id="d1f33-115">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="d1f33-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1f33-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d1f33-116">Requirements</span></span>  
 <span data-ttu-id="d1f33-117">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="d1f33-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1f33-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1f33-118">See Also</span></span>  
 [<span data-ttu-id="d1f33-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="d1f33-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d1f33-120">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="d1f33-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d1f33-121">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="d1f33-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

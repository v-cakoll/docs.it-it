---
title: Metodo ExportTypeForwarder
ms.date: 03/30/2017
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03949fb52d23e3b0f107f9f1d5208208369c3960
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574613"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="16f19-102">Metodo ExportTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="16f19-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="16f19-103">Aggiunge un server d'inoltro per la tabella di tipo dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="16f19-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16f19-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16f19-104">Syntax</span></span>  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16f19-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="16f19-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="16f19-106">Riferimento all'assembly a cui fa riferimento il server d'inoltro.</span><span class="sxs-lookup"><span data-stu-id="16f19-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="16f19-107">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="16f19-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="16f19-108">`ComType` ad esempio i flag `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="16f19-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="16f19-109">Questo valore può essere passato a [metodo DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="16f19-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="16f19-110">Riceve il token del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="16f19-110">Receives the token of the exported type.</span></span> <span data-ttu-id="16f19-111">Ciò è necessario solo per la creazione di tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="16f19-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16f19-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="16f19-112">Return Value</span></span>  
 <span data-ttu-id="16f19-113">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="16f19-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16f19-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16f19-114">Requirements</span></span>  
 <span data-ttu-id="16f19-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="16f19-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16f19-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16f19-116">See also</span></span>
- [<span data-ttu-id="16f19-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="16f19-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="16f19-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="16f19-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="16f19-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="16f19-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

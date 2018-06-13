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
ms.openlocfilehash: 5b28c18d55b91d6315003229295ab0e6781be183
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406305"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="9105e-102">Metodo ExportTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="9105e-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="9105e-103">Aggiunge un server d'inoltro per la tabella dei tipi dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="9105e-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9105e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9105e-104">Syntax</span></span>  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9105e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9105e-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="9105e-106">Riferimento all'assembly a cui fa riferimento il server d'inoltro del tipo.</span><span class="sxs-lookup"><span data-stu-id="9105e-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="9105e-107">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="9105e-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9105e-108">`ComType` flag, ad esempio `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="9105e-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="9105e-109">Questo valore può essere passato a [DefineExportedType (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="9105e-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="9105e-110">Riceve il token del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="9105e-110">Receives the token of the exported type.</span></span> <span data-ttu-id="9105e-111">Ciò è necessario solo per la creazione di tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="9105e-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9105e-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9105e-112">Return Value</span></span>  
 <span data-ttu-id="9105e-113">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="9105e-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9105e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9105e-114">Requirements</span></span>  
 <span data-ttu-id="9105e-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="9105e-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9105e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9105e-116">See Also</span></span>  
 [<span data-ttu-id="9105e-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="9105e-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="9105e-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="9105e-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="9105e-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="9105e-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

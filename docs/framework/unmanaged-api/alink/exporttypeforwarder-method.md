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
ms.openlocfilehash: 5bdf9fb50fe06141df6f3818c784588b9e2138af
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212024"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="769fa-102">Metodo ExportTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="769fa-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="769fa-103">Aggiunge un server d'inoltro per la tabella di tipo dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="769fa-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="769fa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="769fa-104">Syntax</span></span>  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="769fa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="769fa-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="769fa-106">Riferimento all'assembly a cui fa riferimento il server d'inoltro.</span><span class="sxs-lookup"><span data-stu-id="769fa-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="769fa-107">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="769fa-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 `ComType` <span data-ttu-id="769fa-108">ad esempio i flag `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="769fa-108">flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="769fa-109">Questo valore può essere passato a [metodo DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="769fa-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="769fa-110">Riceve il token del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="769fa-110">Receives the token of the exported type.</span></span> <span data-ttu-id="769fa-111">Ciò è necessario solo per la creazione di tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="769fa-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="769fa-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="769fa-112">Return Value</span></span>  
 <span data-ttu-id="769fa-113">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="769fa-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="769fa-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="769fa-114">Requirements</span></span>  
 <span data-ttu-id="769fa-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="769fa-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="769fa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="769fa-116">See also</span></span>

- [<span data-ttu-id="769fa-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="769fa-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="769fa-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="769fa-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="769fa-119">API Alink</span><span class="sxs-lookup"><span data-stu-id="769fa-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

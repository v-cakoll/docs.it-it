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
ms.openlocfilehash: 36c99477e9faead5e24799d5b0ae8901f1dd13c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448714"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="0f52e-102">Metodo ExportTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="0f52e-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="0f52e-103">Aggiunge un server d'avanzamento del tipo alla tabella dei tipi dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="0f52e-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f52e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f52e-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f52e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0f52e-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="0f52e-106">Riferimento all'assembly a cui fa riferimento il server d'avanzamento del tipo.</span><span class="sxs-lookup"><span data-stu-id="0f52e-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="0f52e-107">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="0f52e-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0f52e-108">flag di `ComType` come `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="0f52e-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="0f52e-109">Questo valore può essere passato al [Metodo DefineExportedType](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="0f52e-109">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="0f52e-110">Riceve il token del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="0f52e-110">Receives the token of the exported type.</span></span> <span data-ttu-id="0f52e-111">Questa operazione è necessaria solo per la creazione di tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="0f52e-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f52e-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0f52e-112">Return Value</span></span>  
 <span data-ttu-id="0f52e-113">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0f52e-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f52e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f52e-114">Requirements</span></span>  
 <span data-ttu-id="0f52e-115">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="0f52e-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f52e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f52e-116">See also</span></span>

- [<span data-ttu-id="0f52e-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="0f52e-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0f52e-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="0f52e-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0f52e-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="0f52e-119">ALink API</span></span>](index.md)

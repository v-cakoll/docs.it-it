---
title: Metodo ExportNestedTypeForwarder
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb8fba433c5f7ef9701caf61971841672f46b425
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742029"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="b9848-102">Metodo ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="b9848-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="b9848-103">Aggiunge un server d'inoltro di tipo per un tipo annidato alla tabella di tipo di assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="b9848-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9848-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9848-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="b9848-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b9848-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b9848-106">ID dell'assembly da cui esportare.</span><span class="sxs-lookup"><span data-stu-id="b9848-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="b9848-107">ID token o l'assembly del file che definisce il tipo di file.</span><span class="sxs-lookup"><span data-stu-id="b9848-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="b9848-108">Token per il tipo.</span><span class="sxs-lookup"><span data-stu-id="b9848-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="b9848-109">Token del tipo padre.</span><span class="sxs-lookup"><span data-stu-id="b9848-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="b9848-110">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="b9848-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b9848-111">`ComType` ad esempio i flag `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="b9848-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="b9848-112">Riceve il token del tipo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="b9848-112">Receives token of export type.</span></span> <span data-ttu-id="b9848-113">Ciò è necessario solo per la creazione di tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="b9848-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9848-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b9848-114">Return Value</span></span>  
 <span data-ttu-id="b9848-115">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b9848-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9848-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9848-116">Requirements</span></span>  
 <span data-ttu-id="b9848-117">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="b9848-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9848-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9848-118">See also</span></span>

- [<span data-ttu-id="b9848-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="b9848-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b9848-120">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="b9848-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b9848-121">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="b9848-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

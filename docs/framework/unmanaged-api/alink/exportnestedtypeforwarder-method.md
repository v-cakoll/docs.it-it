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
ms.openlocfilehash: 050ed0bbd4da38bede5a56ff95d0243f5f3cf1da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220084"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="dfd7e-102">Metodo ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="dfd7e-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="dfd7e-103">Aggiunge un server d'inoltro di tipo per un tipo annidato alla tabella di tipo di assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfd7e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dfd7e-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="dfd7e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dfd7e-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="dfd7e-106">ID dell'assembly da cui esportare.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="dfd7e-107">ID token o l'assembly del file che definisce il tipo di file.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="dfd7e-108">Token per il tipo.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="dfd7e-109">Token del tipo padre.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="dfd7e-110">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 `ComType` <span data-ttu-id="dfd7e-111">ad esempio i flag `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-111">flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="dfd7e-112">Riceve il token del tipo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-112">Receives token of export type.</span></span> <span data-ttu-id="dfd7e-113">Ciò è necessario solo per la creazione di tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dfd7e-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dfd7e-114">Return Value</span></span>  
 <span data-ttu-id="dfd7e-115">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfd7e-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dfd7e-116">Requirements</span></span>  
 <span data-ttu-id="dfd7e-117">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="dfd7e-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfd7e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfd7e-118">See also</span></span>

- [<span data-ttu-id="dfd7e-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="dfd7e-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="dfd7e-120">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="dfd7e-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="dfd7e-121">API Alink</span><span class="sxs-lookup"><span data-stu-id="dfd7e-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

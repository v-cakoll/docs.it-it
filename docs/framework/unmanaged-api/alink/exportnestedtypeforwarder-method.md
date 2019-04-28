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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789909"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="52865-102">Metodo ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="52865-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="52865-103">Aggiunge un server d'inoltro di tipo per un tipo annidato alla tabella di tipo di assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="52865-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52865-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52865-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="52865-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="52865-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="52865-106">ID dell'assembly da cui esportare.</span><span class="sxs-lookup"><span data-stu-id="52865-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="52865-107">ID token o l'assembly del file che definisce il tipo di file.</span><span class="sxs-lookup"><span data-stu-id="52865-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="52865-108">Token per il tipo.</span><span class="sxs-lookup"><span data-stu-id="52865-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="52865-109">Token del tipo padre.</span><span class="sxs-lookup"><span data-stu-id="52865-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="52865-110">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="52865-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="52865-111">`ComType` ad esempio i flag `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="52865-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="52865-112">Riceve il token del tipo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="52865-112">Receives token of export type.</span></span> <span data-ttu-id="52865-113">Ciò è necessario solo per la creazione di tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="52865-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52865-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="52865-114">Return Value</span></span>  
 <span data-ttu-id="52865-115">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="52865-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52865-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52865-116">Requirements</span></span>  
 <span data-ttu-id="52865-117">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="52865-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52865-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52865-118">See also</span></span>

- [<span data-ttu-id="52865-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="52865-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="52865-120">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="52865-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="52865-121">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="52865-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

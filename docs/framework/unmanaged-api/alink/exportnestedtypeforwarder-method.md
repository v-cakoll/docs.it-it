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
ms.openlocfilehash: eb8112d6d2b5c2cbb257db2f20ff4be5a84e827b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787462"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="6f8fb-102">Metodo ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="6f8fb-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="6f8fb-103">Aggiunge un server d'avanzamento del tipo per un tipo annidato alla tabella dei tipi dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="6f8fb-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f8fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f8fb-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="6f8fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f8fb-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6f8fb-106">ID dell'assembly da cui eseguire l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="6f8fb-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="6f8fb-107">Token file o ID assembly del file che definisce il tipo.</span><span class="sxs-lookup"><span data-stu-id="6f8fb-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="6f8fb-108">Token per il tipo.</span><span class="sxs-lookup"><span data-stu-id="6f8fb-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="6f8fb-109">Token del tipo padre.</span><span class="sxs-lookup"><span data-stu-id="6f8fb-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="6f8fb-110">Nome completo del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="6f8fb-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6f8fb-111">`ComType`flag come `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="6f8fb-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="6f8fb-112">Riceve il token del tipo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="6f8fb-112">Receives token of export type.</span></span> <span data-ttu-id="6f8fb-113">Questa operazione è necessaria solo per la creazione di tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="6f8fb-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f8fb-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6f8fb-114">Return Value</span></span>  
 <span data-ttu-id="6f8fb-115">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="6f8fb-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f8fb-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f8fb-116">Requirements</span></span>  
 <span data-ttu-id="6f8fb-117">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="6f8fb-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f8fb-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f8fb-118">See also</span></span>

- [<span data-ttu-id="6f8fb-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="6f8fb-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6f8fb-120">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="6f8fb-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6f8fb-121">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="6f8fb-121">ALink API</span></span>](index.md)

---
title: Metodo AddImport
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aed70a78e2513f4d63fbf8ca8868f26efbac9ae8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787661"
---
# <a name="addimport-method"></a><span data-ttu-id="4c50a-102">Metodo AddImport</span><span class="sxs-lookup"><span data-stu-id="4c50a-102">AddImport Method</span></span>
<span data-ttu-id="4c50a-103">Aggiunge le importazioni all'assembly.</span><span class="sxs-lookup"><span data-stu-id="4c50a-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c50a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c50a-104">Syntax</span></span>  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c50a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4c50a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4c50a-106">ID univoco dell'assembly da incrementare.</span><span class="sxs-lookup"><span data-stu-id="4c50a-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="4c50a-107">ID univoco, recuperato dal [metodo ImportFile](importfile-method.md), del file da importare.</span><span class="sxs-lookup"><span data-stu-id="4c50a-107">Unique ID, retrieved from [ImportFile Method](importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4c50a-108">Flag FileDef com+, ad `ffContainsNoMetaData` esempio `ffWriteable`e.</span><span class="sxs-lookup"><span data-stu-id="4c50a-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="4c50a-109">`dwFlags`viene passato al [Metodo DefineFile](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="4c50a-109">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="4c50a-110">Puntatore al token che riceve l'ID per il file risultante.</span><span class="sxs-lookup"><span data-stu-id="4c50a-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c50a-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4c50a-111">Return Value</span></span>  
 <span data-ttu-id="4c50a-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4c50a-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c50a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4c50a-113">Requirements</span></span>  
 <span data-ttu-id="4c50a-114">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="4c50a-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c50a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c50a-115">See also</span></span>

- [<span data-ttu-id="4c50a-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="4c50a-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4c50a-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="4c50a-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4c50a-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="4c50a-118">ALink API</span></span>](index.md)

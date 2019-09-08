---
title: Metodo SetAssemblyFile2
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aba11ccd61b65d2a779b39db8e0e082cf4d4015b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787224"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="e08d0-102">Metodo SetAssemblyFile2</span><span class="sxs-lookup"><span data-stu-id="e08d0-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="e08d0-103">Imposta il nome delle opzioni e per un nuovo assembly.</span><span class="sxs-lookup"><span data-stu-id="e08d0-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="e08d0-104">Non chiamare questo metodo quando si producono moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="e08d0-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e08d0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e08d0-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e08d0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e08d0-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="e08d0-107">Nome del file manifesto.</span><span class="sxs-lookup"><span data-stu-id="e08d0-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="e08d0-108">Interfaccia dell' [Interfaccia IMetaDataEmit2](../metadata/imetadataemit2-interface.md) per questo file.</span><span class="sxs-lookup"><span data-stu-id="e08d0-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="e08d0-109">Opzioni rappresentate dall' [Enumerazione AssemblyFlags](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="e08d0-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="e08d0-110">Riceve l'ID univoco per l'assembly costruito.</span><span class="sxs-lookup"><span data-stu-id="e08d0-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e08d0-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e08d0-111">Return Value</span></span>  
 <span data-ttu-id="e08d0-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e08d0-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e08d0-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e08d0-113">Requirements</span></span>  
 <span data-ttu-id="e08d0-114">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="e08d0-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e08d0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e08d0-115">See also</span></span>

- [<span data-ttu-id="e08d0-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="e08d0-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e08d0-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="e08d0-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e08d0-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="e08d0-118">ALink API</span></span>](index.md)

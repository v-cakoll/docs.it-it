---
title: Metodo SetAssemblyFile
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a19762cbec91871d7af617957896e4ee34944fba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132711"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="ef473-102">Metodo SetAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="ef473-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="ef473-103">Assegna il nome dell'assembly da compilare.</span><span class="sxs-lookup"><span data-stu-id="ef473-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="ef473-104">Non per essere utilizzato durante la creazione di moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="ef473-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef473-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef473-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef473-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef473-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="ef473-107">Nome completo del file manifesto.</span><span class="sxs-lookup"><span data-stu-id="ef473-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="ef473-108">Puntatore alla [IMetaDataEmit (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ef473-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="ef473-109">Contrassegna come definito in [enumerazione AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ef473-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="ef473-110">Puntatore all'ID dell'assembly risultante.</span><span class="sxs-lookup"><span data-stu-id="ef473-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef473-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ef473-111">Return Value</span></span>  
 <span data-ttu-id="ef473-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ef473-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef473-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef473-113">Requirements</span></span>  
 <span data-ttu-id="ef473-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="ef473-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef473-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef473-115">See also</span></span>

- [<span data-ttu-id="ef473-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="ef473-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ef473-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="ef473-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ef473-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="ef473-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

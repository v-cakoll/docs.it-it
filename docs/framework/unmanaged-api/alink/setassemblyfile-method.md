---
title: Metodo SetAssemblyFile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.SetAssemblyFile
api_location: alink.dll
api_type: COM
f1_keywords: SetAssemblyFile
helpviewer_keywords: SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0be76e93ab41860f7f3416d0baffe3e4daf84c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="f06f9-102">Metodo SetAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="f06f9-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="f06f9-103">Assegna il nome dell'assembly da compilare.</span><span class="sxs-lookup"><span data-stu-id="f06f9-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="f06f9-104">Non per l'utilizzo durante la creazione di moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="f06f9-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f06f9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f06f9-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f06f9-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f06f9-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="f06f9-107">Nome completo del file manifesto.</span><span class="sxs-lookup"><span data-stu-id="f06f9-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="f06f9-108">Puntatore a [interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f06f9-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="f06f9-109">Flag definiti in [enumerazione AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f06f9-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="f06f9-110">Puntatore all'ID dell'assembly risultante.</span><span class="sxs-lookup"><span data-stu-id="f06f9-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f06f9-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f06f9-111">Return Value</span></span>  
 <span data-ttu-id="f06f9-112">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="f06f9-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f06f9-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f06f9-113">Requirements</span></span>  
 <span data-ttu-id="f06f9-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="f06f9-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f06f9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f06f9-115">See Also</span></span>  
 [<span data-ttu-id="f06f9-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="f06f9-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="f06f9-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="f06f9-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="f06f9-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="f06f9-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

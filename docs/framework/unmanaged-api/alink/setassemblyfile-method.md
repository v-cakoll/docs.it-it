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
ms.openlocfilehash: 1e557cc0da7bc684843ae3969242ffb84d811c44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405346"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="c95e3-102">Metodo SetAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="c95e3-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="c95e3-103">Assegna il nome dell'assembly da compilare.</span><span class="sxs-lookup"><span data-stu-id="c95e3-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="c95e3-104">Non per l'utilizzo durante la creazione di moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="c95e3-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c95e3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c95e3-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c95e3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c95e3-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="c95e3-107">Nome completo del file manifesto.</span><span class="sxs-lookup"><span data-stu-id="c95e3-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="c95e3-108">Puntatore a [interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c95e3-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="c95e3-109">Flag definiti in [enumerazione AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="c95e3-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="c95e3-110">Puntatore all'ID dell'assembly risultante.</span><span class="sxs-lookup"><span data-stu-id="c95e3-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c95e3-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c95e3-111">Return Value</span></span>  
 <span data-ttu-id="c95e3-112">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="c95e3-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c95e3-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c95e3-113">Requirements</span></span>  
 <span data-ttu-id="c95e3-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="c95e3-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c95e3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c95e3-115">See Also</span></span>  
 [<span data-ttu-id="c95e3-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="c95e3-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c95e3-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="c95e3-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c95e3-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="c95e3-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

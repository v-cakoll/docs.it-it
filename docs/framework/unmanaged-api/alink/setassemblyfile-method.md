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
ms.openlocfilehash: 1db4c4ab7e47e223a492e08297ac3cedcb3a27eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445599"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="c64b7-102">Metodo SetAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="c64b7-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="c64b7-103">Assegna il nome dell'assembly da compilare.</span><span class="sxs-lookup"><span data-stu-id="c64b7-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="c64b7-104">Non da usare quando si producono moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="c64b7-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c64b7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c64b7-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c64b7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c64b7-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="c64b7-107">Nome completo del file manifesto.</span><span class="sxs-lookup"><span data-stu-id="c64b7-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="c64b7-108">Puntatore all'interfaccia dell' [interfaccia IMetaDataEmit](../metadata/imetadataemit-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c64b7-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="c64b7-109">Flag come definito nell' [Enumerazione AssemblyFlags](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="c64b7-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="c64b7-110">Puntatore all'ID dell'assembly risultante.</span><span class="sxs-lookup"><span data-stu-id="c64b7-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c64b7-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c64b7-111">Return Value</span></span>  
 <span data-ttu-id="c64b7-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c64b7-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c64b7-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c64b7-113">Requirements</span></span>  
 <span data-ttu-id="c64b7-114">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="c64b7-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c64b7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c64b7-115">See also</span></span>

- [<span data-ttu-id="c64b7-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="c64b7-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c64b7-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="c64b7-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c64b7-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="c64b7-118">ALink API</span></span>](index.md)

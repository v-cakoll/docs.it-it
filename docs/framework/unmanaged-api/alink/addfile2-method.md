---
title: Metodo AddFile2
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3a6892dbed172c0be3b036014d393657dbc8593
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777516"
---
# <a name="addfile2-method"></a><span data-ttu-id="24417-102">Metodo AddFile2</span><span class="sxs-lookup"><span data-stu-id="24417-102">AddFile2 Method</span></span>
<span data-ttu-id="24417-103">Aggiunge file all'assembly.</span><span class="sxs-lookup"><span data-stu-id="24417-103">Adds files to the assembly.</span></span> <span data-ttu-id="24417-104">Può essere usato anche per creare moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="24417-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24417-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24417-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="24417-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="24417-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="24417-107">ID dell'assembly a cui viene aggiunto il file.</span><span class="sxs-lookup"><span data-stu-id="24417-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="24417-108">Nome del file da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="24417-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="24417-109">Flag `FileDef` com+ `ffWriteable` `ffContainsNoMetaData` , ad esempio e.</span><span class="sxs-lookup"><span data-stu-id="24417-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="24417-110">`dwFlags`viene passato al [Metodo DefineFile](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="24417-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="24417-111">Interfaccia per interfaccia dell' [Interfaccia IMetaDataEmit2](../metadata/imetadataemit2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="24417-111">Interface to [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="24417-112">Riceve l'ID per il file da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="24417-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24417-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="24417-113">Return Value</span></span>  
 <span data-ttu-id="24417-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="24417-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24417-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="24417-115">Requirements</span></span>  
 <span data-ttu-id="24417-116">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="24417-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24417-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24417-117">See also</span></span>

- [<span data-ttu-id="24417-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="24417-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="24417-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="24417-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="24417-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="24417-120">ALink API</span></span>](index.md)

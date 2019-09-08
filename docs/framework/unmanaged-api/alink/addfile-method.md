---
title: Metodo AddFile
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b1406c68f1f6abff4d140b131f5f630d0fd767e1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787683"
---
# <a name="addfile-method"></a><span data-ttu-id="cf1f0-102">Metodo AddFile</span><span class="sxs-lookup"><span data-stu-id="cf1f0-102">AddFile Method</span></span>
<span data-ttu-id="cf1f0-103">Aggiunge file all'assembly.</span><span class="sxs-lookup"><span data-stu-id="cf1f0-103">Adds files to the assembly.</span></span> <span data-ttu-id="cf1f0-104">Può essere usato anche per creare moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="cf1f0-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf1f0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf1f0-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf1f0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="cf1f0-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="cf1f0-107">ID univoco dell'assembly da incrementare.</span><span class="sxs-lookup"><span data-stu-id="cf1f0-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="cf1f0-108">Nome completo del file da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="cf1f0-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cf1f0-109">Flag FileDef com+, ad `ffContainsNoMetaData` esempio `ffWriteable`e.</span><span class="sxs-lookup"><span data-stu-id="cf1f0-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="cf1f0-110">`dwFlags`viene passato al [Metodo DefineFile](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="cf1f0-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="cf1f0-111">Interfaccia di [interfaccia IMetaDataEmit](../metadata/imetadataemit-interface.md) da usare per creare i metadati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="cf1f0-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="cf1f0-112">Puntatore alla posizione in cui verrà archiviato l'ID univoco del file aggiunto.</span><span class="sxs-lookup"><span data-stu-id="cf1f0-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf1f0-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cf1f0-113">Return Value</span></span>  
 <span data-ttu-id="cf1f0-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cf1f0-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf1f0-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf1f0-115">Requirements</span></span>  
 <span data-ttu-id="cf1f0-116">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="cf1f0-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf1f0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf1f0-117">See also</span></span>

- [<span data-ttu-id="cf1f0-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="cf1f0-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="cf1f0-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="cf1f0-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="cf1f0-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="cf1f0-120">ALink API</span></span>](index.md)

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
ms.openlocfilehash: 4dd104805d547613315335bc9c95b5c60a9cab14
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446679"
---
# <a name="addfile-method"></a><span data-ttu-id="0ae8f-102">Metodo AddFile</span><span class="sxs-lookup"><span data-stu-id="0ae8f-102">AddFile Method</span></span>
<span data-ttu-id="0ae8f-103">Aggiunge file all'assembly.</span><span class="sxs-lookup"><span data-stu-id="0ae8f-103">Adds files to the assembly.</span></span> <span data-ttu-id="0ae8f-104">Può essere usato anche per creare moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="0ae8f-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ae8f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ae8f-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ae8f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ae8f-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0ae8f-107">ID univoco dell'assembly da incrementare.</span><span class="sxs-lookup"><span data-stu-id="0ae8f-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="0ae8f-108">Nome completo del file da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="0ae8f-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0ae8f-109">Flag FileDef COM+, ad esempio `ffContainsNoMetaData` e `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="0ae8f-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="0ae8f-110">`dwFlags` viene passato al [Metodo DefineFile](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="0ae8f-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="0ae8f-111">Interfaccia di [interfaccia IMetaDataEmit](../metadata/imetadataemit-interface.md) da usare per creare i metadati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="0ae8f-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="0ae8f-112">Puntatore alla posizione in cui verrà archiviato l'ID univoco del file aggiunto.</span><span class="sxs-lookup"><span data-stu-id="0ae8f-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ae8f-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0ae8f-113">Return Value</span></span>  
 <span data-ttu-id="0ae8f-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0ae8f-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ae8f-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ae8f-115">Requirements</span></span>  
 <span data-ttu-id="0ae8f-116">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="0ae8f-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ae8f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ae8f-117">See also</span></span>

- [<span data-ttu-id="0ae8f-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="0ae8f-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0ae8f-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="0ae8f-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0ae8f-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="0ae8f-120">ALink API</span></span>](index.md)

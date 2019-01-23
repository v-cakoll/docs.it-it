---
title: Metodo SetManifestFile
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a253503f3046c004cc7109a31b5aa8fd8e8dc195
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618051"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="ece5e-102">Metodo SetManifestFile</span><span class="sxs-lookup"><span data-stu-id="ece5e-102">SetManifestFile Method</span></span>
<span data-ttu-id="ece5e-103">Consente di specificare o ripristinare il file manifesto che il linker Usa durante la creazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ece5e-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ece5e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ece5e-104">Syntax</span></span>  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ece5e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ece5e-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="ece5e-106">Il nome del file manifesto viene inserito il cui contenuto nell'oggetto blob di risorse Win32.</span><span class="sxs-lookup"><span data-stu-id="ece5e-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ece5e-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ece5e-107">Return Value</span></span>  
 <span data-ttu-id="ece5e-108">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ece5e-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ece5e-109">Note</span><span class="sxs-lookup"><span data-stu-id="ece5e-109">Remarks</span></span>  
 <span data-ttu-id="ece5e-110">Chiamare questo metodo prima di richiedere il Win32ResBlob.</span><span class="sxs-lookup"><span data-stu-id="ece5e-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="ece5e-111">Il valore della `pszFile` parametro è il nome del file manifesto il cui contenuto viene letto e inserire nelle risorse Win32 con l'ID di RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="ece5e-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="ece5e-112">Quando viene chiamato con un parametro null, viene cancellata manifesto letta in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ece5e-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="ece5e-113">Ciò consente di reimpostare lo stato del linker al momento dell'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="ece5e-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ece5e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ece5e-114">Requirements</span></span>  
 <span data-ttu-id="ece5e-115">Richiede aLink.h</span><span class="sxs-lookup"><span data-stu-id="ece5e-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece5e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ece5e-116">See also</span></span>
- [<span data-ttu-id="ece5e-117">Interfaccia IALink3</span><span class="sxs-lookup"><span data-stu-id="ece5e-117">IALink3 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)
- [<span data-ttu-id="ece5e-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="ece5e-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
- [<span data-ttu-id="ece5e-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="ece5e-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ece5e-120">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="ece5e-120">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)

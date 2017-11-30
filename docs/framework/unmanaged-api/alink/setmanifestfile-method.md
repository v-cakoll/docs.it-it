---
title: Metodo SetManifestFile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink3.SetManifestFile
api_location: alink.dll
api_type: COM
f1_keywords: SetManifestFile
helpviewer_keywords: SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 807452326193d193f3bc603ebc7b74a5a0f1c281
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="e9b2c-102">Metodo SetManifestFile</span><span class="sxs-lookup"><span data-stu-id="e9b2c-102">SetManifestFile Method</span></span>
<span data-ttu-id="e9b2c-103">Consente di specificare o reimpostare il file manifesto che il linker utilizza quando viene creato l'assembly.</span><span class="sxs-lookup"><span data-stu-id="e9b2c-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b2c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9b2c-104">Syntax</span></span>  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9b2c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9b2c-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="e9b2c-106">Il nome del file manifesto il cui contenuto è inserito nel blob di risorse Win32.</span><span class="sxs-lookup"><span data-stu-id="e9b2c-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9b2c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e9b2c-107">Return Value</span></span>  
 <span data-ttu-id="e9b2c-108">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="e9b2c-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9b2c-109">Note</span><span class="sxs-lookup"><span data-stu-id="e9b2c-109">Remarks</span></span>  
 <span data-ttu-id="e9b2c-110">Chiamare questo metodo prima di richiedere la Win32ResBlob.</span><span class="sxs-lookup"><span data-stu-id="e9b2c-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="e9b2c-111">Il valore di `pszFile` parametro è il nome del file manifesto il cui contenuto viene letto e inserito nelle risorse Win32 con l'ID di RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="e9b2c-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="e9b2c-112">Quando viene chiamato con un parametro null, viene cancellato qualsiasi manifesti letti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e9b2c-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="e9b2c-113">Ciò consente di reimpostare lo stato del linker al momento dell'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="e9b2c-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9b2c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9b2c-114">Requirements</span></span>  
 <span data-ttu-id="e9b2c-115">Richiede aLink.h</span><span class="sxs-lookup"><span data-stu-id="e9b2c-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b2c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9b2c-116">See Also</span></span>  
 [<span data-ttu-id="e9b2c-117">Interfaccia IALink3</span><span class="sxs-lookup"><span data-stu-id="e9b2c-117">IALink3 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)  
 [<span data-ttu-id="e9b2c-118">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="e9b2c-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)  
 [<span data-ttu-id="e9b2c-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="e9b2c-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e9b2c-120">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="e9b2c-120">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)

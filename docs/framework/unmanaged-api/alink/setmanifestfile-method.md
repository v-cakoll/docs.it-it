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
ms.openlocfilehash: 8307960166cfc668a577431d688c439f0f794be2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949043"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="367d7-102">Metodo SetManifestFile</span><span class="sxs-lookup"><span data-stu-id="367d7-102">SetManifestFile Method</span></span>
<span data-ttu-id="367d7-103">Consente di specificare o ripristinare il file manifesto che il linker Usa durante la creazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="367d7-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="367d7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="367d7-104">Syntax</span></span>  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="367d7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="367d7-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="367d7-106">Il nome del file manifesto viene inserito il cui contenuto nell'oggetto blob di risorse Win32.</span><span class="sxs-lookup"><span data-stu-id="367d7-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="367d7-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="367d7-107">Return Value</span></span>  
 <span data-ttu-id="367d7-108">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="367d7-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="367d7-109">Note</span><span class="sxs-lookup"><span data-stu-id="367d7-109">Remarks</span></span>  
 <span data-ttu-id="367d7-110">Chiamare questo metodo prima di richiedere il Win32ResBlob.</span><span class="sxs-lookup"><span data-stu-id="367d7-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="367d7-111">Il valore della `pszFile` parametro è il nome del file manifesto il cui contenuto viene letto e inserire nelle risorse Win32 con l'ID di RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="367d7-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="367d7-112">Quando viene chiamato con un parametro null, viene cancellata manifesto letta in precedenza.</span><span class="sxs-lookup"><span data-stu-id="367d7-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="367d7-113">Ciò consente di reimpostare lo stato del linker al momento dell'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="367d7-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="367d7-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="367d7-114">Requirements</span></span>  
 <span data-ttu-id="367d7-115">Richiede aLink.h</span><span class="sxs-lookup"><span data-stu-id="367d7-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="367d7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="367d7-116">See also</span></span>

- [<span data-ttu-id="367d7-117">Interfaccia IALink3</span><span class="sxs-lookup"><span data-stu-id="367d7-117">IALink3 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)
- [<span data-ttu-id="367d7-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="367d7-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
- [<span data-ttu-id="367d7-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="367d7-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="367d7-120">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="367d7-120">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)

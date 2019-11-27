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
ms.openlocfilehash: df97f4c37d8f335ce183685debd7c0933be910ed
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445565"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="fbc8a-102">Metodo SetManifestFile</span><span class="sxs-lookup"><span data-stu-id="fbc8a-102">SetManifestFile Method</span></span>
<span data-ttu-id="fbc8a-103">Consente di specificare o reimpostare il file manifesto utilizzato dal linker durante la creazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fbc8a-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbc8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fbc8a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbc8a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fbc8a-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="fbc8a-106">Nome del file manifesto il cui contenuto viene inserito nel BLOB di risorse Win32.</span><span class="sxs-lookup"><span data-stu-id="fbc8a-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbc8a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fbc8a-107">Return Value</span></span>  
 <span data-ttu-id="fbc8a-108">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fbc8a-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbc8a-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fbc8a-109">Remarks</span></span>  
 <span data-ttu-id="fbc8a-110">Chiamare questo oggetto prima di richiedere l'Win32ResBlob.</span><span class="sxs-lookup"><span data-stu-id="fbc8a-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="fbc8a-111">Il valore del parametro `pszFile` è il nome del file manifesto il cui contenuto viene letto e inserito nelle risorse Win32 con ID RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="fbc8a-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="fbc8a-112">Quando viene chiamato usando un parametro NULL, qualsiasi manifesto precedentemente letto viene cancellato.</span><span class="sxs-lookup"><span data-stu-id="fbc8a-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="fbc8a-113">In questo modo, è possibile reimpostare lo stato del linker su quello del tempo di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="fbc8a-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbc8a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fbc8a-114">Requirements</span></span>  
 <span data-ttu-id="fbc8a-115">Richiede aLink. h</span><span class="sxs-lookup"><span data-stu-id="fbc8a-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc8a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbc8a-116">See also</span></span>

- [<span data-ttu-id="fbc8a-117">Interfaccia IALink3</span><span class="sxs-lookup"><span data-stu-id="fbc8a-117">IALink3 Interface</span></span>](ialink3-interface.md)
- [<span data-ttu-id="fbc8a-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="fbc8a-118">ALink API</span></span>](index.md)
- [<span data-ttu-id="fbc8a-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="fbc8a-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="fbc8a-120">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="fbc8a-120">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)

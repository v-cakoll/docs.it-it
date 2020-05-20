---
title: Funzione _CorExeMain
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
ms.openlocfilehash: 935ac478fb966315e81fdcc004761038b28e3178
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616591"
---
# <a name="_corexemain-function"></a><span data-ttu-id="dce52-102">Funzione _CorExeMain</span><span class="sxs-lookup"><span data-stu-id="dce52-102">_CorExeMain Function</span></span>
<span data-ttu-id="dce52-103">Inizializza il Common Language Runtime (CLR), individua il punto di ingresso gestito nell'intestazione CLR dell'assembly eseguibile e avvia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dce52-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dce52-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dce52-104">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="dce52-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dce52-105">Remarks</span></span>  
 <span data-ttu-id="dce52-106">Questa funzione viene chiamata dal caricatore nei processi creati dagli assembly eseguibili gestiti.</span><span class="sxs-lookup"><span data-stu-id="dce52-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="dce52-107">Per gli assembly DLL, il caricatore chiama invece la funzione [_CorDllMain](cordllmain-function.md) .</span><span class="sxs-lookup"><span data-stu-id="dce52-107">For DLL assemblies, the loader calls the [_CorDllMain](cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="dce52-108">Il caricatore del sistema operativo chiama questo metodo indipendentemente dal punto di ingresso specificato nel file di immagine.</span><span class="sxs-lookup"><span data-stu-id="dce52-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="dce52-109">In Windows 98, Windows ME, Windows NT e Windows 2000, la `_CorExeMain` funzione viene chiamata indirettamente tramite una correzione nel caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="dce52-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="dce52-110">In tutte le altre versioni di Windows, viene chiamato direttamente dal caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="dce52-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="dce52-111">Per ulteriori informazioni, vedere la sezione osservazioni nell'argomento [_CorValidateImage](corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="dce52-111">For additional information, see the Remarks section in the [_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dce52-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dce52-112">Requirements</span></span>  
 <span data-ttu-id="dce52-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dce52-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dce52-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dce52-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dce52-115">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dce52-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dce52-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dce52-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce52-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dce52-117">See also</span></span>

- [<span data-ttu-id="dce52-118">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="dce52-118">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)

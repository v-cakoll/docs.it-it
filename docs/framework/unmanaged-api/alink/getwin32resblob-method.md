---
title: Metodo GetWin32ResBlob
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a4c77ade46d2401e2499a94504808efd94f79f93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789792"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="369f6-102">Metodo GetWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="369f6-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="369f6-103">Recupera il blob di risorse Win32.</span><span class="sxs-lookup"><span data-stu-id="369f6-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="369f6-104">Chiamare questo metodo dopo aver impostato le opzioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="369f6-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="369f6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="369f6-105">Syntax</span></span>  
  
```  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="369f6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="369f6-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="369f6-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="369f6-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="369f6-108">Token file utilizzato per recuperare il nome del file da utilizzare quando si crea la risorsa di versione Win32</span><span class="sxs-lookup"><span data-stu-id="369f6-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="369f6-109">TRUE se una DLL, file di un file eseguibile è false.</span><span class="sxs-lookup"><span data-stu-id="369f6-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="369f6-110">Icona facoltativa da inserire nell'oggetto blob di risorse.</span><span class="sxs-lookup"><span data-stu-id="369f6-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="369f6-111">Riceve il blob di risorse.</span><span class="sxs-lookup"><span data-stu-id="369f6-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="369f6-112">Riceve le dimensioni del blob.</span><span class="sxs-lookup"><span data-stu-id="369f6-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="369f6-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="369f6-113">Return Value</span></span>  
 <span data-ttu-id="369f6-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="369f6-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="369f6-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="369f6-115">Requirements</span></span>  
 <span data-ttu-id="369f6-116">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="369f6-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="369f6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="369f6-117">See also</span></span>

- [<span data-ttu-id="369f6-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="369f6-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="369f6-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="369f6-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="369f6-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="369f6-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

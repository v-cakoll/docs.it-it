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
ms.openlocfilehash: b26f08548ac964fae2f4d64db50167add327eb2d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777364"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="01dc0-102">Metodo GetWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="01dc0-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="01dc0-103">Recupera il BLOB di risorse Win32.</span><span class="sxs-lookup"><span data-stu-id="01dc0-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="01dc0-104">Chiamare questo metodo dopo aver impostato le opzioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="01dc0-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01dc0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01dc0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="01dc0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="01dc0-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="01dc0-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="01dc0-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="01dc0-108">Token del file usato per recuperare il nome file da usare quando si costruisce la risorsa della versione Win32</span><span class="sxs-lookup"><span data-stu-id="01dc0-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="01dc0-109">TRUE se il file è una DLL, false per un file EXE.</span><span class="sxs-lookup"><span data-stu-id="01dc0-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="01dc0-110">Icona facoltativa da inserire nel BLOB di risorse.</span><span class="sxs-lookup"><span data-stu-id="01dc0-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="01dc0-111">Riceve il BLOB di risorse.</span><span class="sxs-lookup"><span data-stu-id="01dc0-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="01dc0-112">Riceve la dimensione del BLOB.</span><span class="sxs-lookup"><span data-stu-id="01dc0-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01dc0-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="01dc0-113">Return Value</span></span>  
 <span data-ttu-id="01dc0-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="01dc0-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01dc0-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01dc0-115">Requirements</span></span>  
 <span data-ttu-id="01dc0-116">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="01dc0-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01dc0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01dc0-117">See also</span></span>

- [<span data-ttu-id="01dc0-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="01dc0-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="01dc0-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="01dc0-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="01dc0-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="01dc0-120">ALink API</span></span>](index.md)

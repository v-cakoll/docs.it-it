---
title: Funzione CreateVersionStringFromModule
ms.date: 03/30/2017
api_name:
- CreateVersionStringFromModule
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CreateVersionStringFromModule
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CreateVersionStringFromModule function
ms.assetid: 3d2fe9bd-75ef-4364-84a6-da1e1994ac1a
topic_type:
- apiref
ms.openlocfilehash: 609d6e47c951aa104cb23084b65e98827a6851f1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789182"
---
# <a name="createversionstringfrommodule-function"></a><span data-ttu-id="82ff2-102">Funzione CreateVersionStringFromModule</span><span class="sxs-lookup"><span data-stu-id="82ff2-102">CreateVersionStringFromModule Function</span></span>
<span data-ttu-id="82ff2-103">Crea una stringa di versione da un percorso Common Language Runtime (CLR) in un processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="82ff2-103">Creates a version string from a common language runtime (CLR) path in a target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82ff2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82ff2-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateVersionStringFromModule (  
    [in]  DWORD      pidDebuggee,  
    [in]  LPCWSTR    szModuleName,  
    [out, size_is(cchBuffer),  
          length_is(*pdwLength)] LPWSTR Buffer,  
    [in]  DWORD      cchBuffer,  
    [out] DWORD*     pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82ff2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="82ff2-105">Parameters</span></span>  
 `pidDebuggee`  
 <span data-ttu-id="82ff2-106">[in] Identificatore del processo nel quale è caricato il CLR di destinazione.</span><span class="sxs-lookup"><span data-stu-id="82ff2-106">[in] Identifier of the process in which the target CLR is loaded.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="82ff2-107">[in] Percorso completo o relativo del CLR di destinazione caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="82ff2-107">[in] Full or relative path to the target CLR that is loaded in the process.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="82ff2-108">[out] Buffer di ritorno per l'archiviazione delle stringhe di versione per il CLR di destinazione.</span><span class="sxs-lookup"><span data-stu-id="82ff2-108">[out] Return buffer for storing the version string for the target CLR.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="82ff2-109">[in] Dimensione di `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="82ff2-109">[in] Size of `pBuffer`.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="82ff2-110">[out] Lunghezza della stringa di versione restituita da `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="82ff2-110">[out] Length of the version string returned by `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82ff2-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="82ff2-111">Return Value</span></span>  
 <span data-ttu-id="82ff2-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="82ff2-112">S_OK</span></span>  
 <span data-ttu-id="82ff2-113">La stringa della versione per il CLR di destinazione è stata correttamente restituita in `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="82ff2-113">The version string for the target CLR was successfully returned in `pBuffer`.</span></span>  
  
 <span data-ttu-id="82ff2-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="82ff2-114">E_INVALIDARG</span></span>  
 <span data-ttu-id="82ff2-115">`szModuleName` è null oppure either `pBuffer` o `cchBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="82ff2-115">`szModuleName` is null, or either `pBuffer` or `cchBuffer` is null.</span></span> <span data-ttu-id="82ff2-116">`pBuffer` e `cchBuffer` devono entrambi essere null o non Null.</span><span class="sxs-lookup"><span data-stu-id="82ff2-116">`pBuffer` and `cchBuffer` must both be null or non-null.</span></span>  
  
 <span data-ttu-id="82ff2-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="82ff2-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>  
 <span data-ttu-id="82ff2-118">`pdwLength` è maggiore di `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="82ff2-118">`pdwLength` is greater than `cchBuffer`.</span></span> <span data-ttu-id="82ff2-119">Può trattarsi di un risultato previsto se è stato passato un valore Null per entrambi gli elementi `pBuffer` e `cchBuffer` e se è stata eseguita una query sulle dimensioni del buffer necessarie tramite `pdwLength`.</span><span class="sxs-lookup"><span data-stu-id="82ff2-119">This may be an expected result if you have passed null for both `pBuffer` and `cchBuffer`, and queried the necessary buffer size by using `pdwLength`.</span></span>  
  
 <span data-ttu-id="82ff2-120">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span><span class="sxs-lookup"><span data-stu-id="82ff2-120">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span></span>  
 <span data-ttu-id="82ff2-121">`szModuleName` on contiene un percorso a un CLR valido nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="82ff2-121">`szModuleName` does not contain a path to a valid CLR in the target process.</span></span>  
  
 <span data-ttu-id="82ff2-122">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="82ff2-122">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="82ff2-123">`pidDebuggee` non fa riferimento a un processo valido o a altri errori.</span><span class="sxs-lookup"><span data-stu-id="82ff2-123">`pidDebuggee` does not refer to a valid process, or other failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82ff2-124">Note</span><span class="sxs-lookup"><span data-stu-id="82ff2-124">Remarks</span></span>  
 <span data-ttu-id="82ff2-125">Questa funzione accetta un processo di CLR identificato da `pidDebuggee` e un percorso della stringa specificato da `szModuleName`.</span><span class="sxs-lookup"><span data-stu-id="82ff2-125">This function accepts a CLR process that is identified by `pidDebuggee` and a string path that is specified by `szModuleName`.</span></span> <span data-ttu-id="82ff2-126">La stringa della versione viene restituita nel buffer al quale punta`pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="82ff2-126">The version string is returned in the buffer that `pBuffer` points to.</span></span> <span data-ttu-id="82ff2-127">Questa stringa è invisibile all'utente della funzione. In altre parole, non è presente alcun significato intrinseco nella stringa di versione stessa.</span><span class="sxs-lookup"><span data-stu-id="82ff2-127">This string is opaque to the function user; that is, there is no intrinsic meaning in the version string itself.</span></span> <span data-ttu-id="82ff2-128">Viene utilizzato esclusivamente nel contesto di questa funzione e della [funzione CreateDebuggingInterfaceFromVersion](createdebugginginterfacefromversion-function-for-silverlight.md).</span><span class="sxs-lookup"><span data-stu-id="82ff2-128">It is used solely in the context of this function and the [CreateDebuggingInterfaceFromVersion function](createdebugginginterfacefromversion-function-for-silverlight.md).</span></span>  
  
 <span data-ttu-id="82ff2-129">Questa funzione deve essere chiamata due volte.</span><span class="sxs-lookup"><span data-stu-id="82ff2-129">This function should be called twice.</span></span> <span data-ttu-id="82ff2-130">Quando si chiama per la prima volta, passare il valore null per `pBuffer` e `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="82ff2-130">When you call it the first time, pass null for both `pBuffer` and `cchBuffer`.</span></span> <span data-ttu-id="82ff2-131">Quando si esegue questa operazione, le dimensioni del buffer necessarie per `pBuffer` verranno restituite in `pdwLength`.</span><span class="sxs-lookup"><span data-stu-id="82ff2-131">When you do this, the size of the buffer necessary for `pBuffer` will be returned in `pdwLength`.</span></span> <span data-ttu-id="82ff2-132">È possibile, quindi, chiamare la funzione una seconda volta e passare il buffer in `pBuffer` e le sue dimensioni in `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="82ff2-132">You can then call the function a second time, and pass the buffer in `pBuffer` and its size in `cchBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82ff2-133">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="82ff2-133">Requirements</span></span>  
 <span data-ttu-id="82ff2-134">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82ff2-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82ff2-135">**Intestazione:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="82ff2-135">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="82ff2-136">**Libreria:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="82ff2-136">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="82ff2-137">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="82ff2-137">**.NET Framework Versions:** 3.5 SP1</span></span>

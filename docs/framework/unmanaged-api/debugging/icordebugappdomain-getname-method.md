---
title: Metodo ICorDebugAppDomain::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7939f7b1c0c725bb4e8c642bc38121dd755da5e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785138"
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="f0e17-102">Metodo ICorDebugAppDomain::GetName</span><span class="sxs-lookup"><span data-stu-id="f0e17-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="f0e17-103">Ottiene il nome del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f0e17-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0e17-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0e17-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0e17-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f0e17-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="f0e17-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="f0e17-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="f0e17-107">Impostare questo valore su zero per il metodo put in modalità query.</span><span class="sxs-lookup"><span data-stu-id="f0e17-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f0e17-108">[out] Un puntatore alla dimensione del nome o il numero di caratteri effettivamente restituiti nella `szName`.</span><span class="sxs-lookup"><span data-stu-id="f0e17-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="f0e17-109">In modalità query, questo valore consente al chiamante di sapere come un buffer di grandi dimensioni da allocare per il nome.</span><span class="sxs-lookup"><span data-stu-id="f0e17-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="f0e17-110">[out] Matrice che archivia il nome del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f0e17-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0e17-111">Note</span><span class="sxs-lookup"><span data-stu-id="f0e17-111">Remarks</span></span>  
 <span data-ttu-id="f0e17-112">Un debugger chiama il `GetName` metodo una volta per ottenere la dimensione del buffer necessaria per il nome.</span><span class="sxs-lookup"><span data-stu-id="f0e17-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="f0e17-113">Il debugger esegue l'allocazione di buffer e quindi chiama il metodo di una seconda volta per riempire il buffer.</span><span class="sxs-lookup"><span data-stu-id="f0e17-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="f0e17-114">La prima chiamata, per ottenere le dimensioni del nome, è detto *modalità query*.</span><span class="sxs-lookup"><span data-stu-id="f0e17-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0e17-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0e17-115">Requirements</span></span>  
 <span data-ttu-id="f0e17-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0e17-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0e17-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0e17-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0e17-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0e17-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0e17-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0e17-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

---
title: Funzione InitDbgTransportManager
ms.date: 03/30/2017
api_name:
- InitDbgTransportManager
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type:
- apiref
ms.openlocfilehash: e18ceb25b9c58a9710ef967cb071e3ef55beea8c
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421046"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="9db7f-102">Funzione InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="9db7f-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="9db7f-103">Inizializza il gestore trasporto per connettersi a una destinazione remota per l'enumerazione del runtime e dei processi.</span><span class="sxs-lookup"><span data-stu-id="9db7f-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9db7f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9db7f-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9db7f-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9db7f-105">Return Value</span></span>  
 <span data-ttu-id="9db7f-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="9db7f-106">S_OK</span></span>  
 <span data-ttu-id="9db7f-107">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="9db7f-107">Success.</span></span>  
  
 <span data-ttu-id="9db7f-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9db7f-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="9db7f-109">La funzione non è riuscita ad allocare memoria per un gestore trasporto.</span><span class="sxs-lookup"><span data-stu-id="9db7f-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="9db7f-110">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="9db7f-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9db7f-111">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="9db7f-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9db7f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9db7f-112">Requirements</span></span>  
 <span data-ttu-id="9db7f-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9db7f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9db7f-114">**Intestazione:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="9db7f-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="9db7f-115">**Libreria:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="9db7f-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="9db7f-116">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="9db7f-116">**.NET Framework Versions:** 3.5 SP1</span></span>

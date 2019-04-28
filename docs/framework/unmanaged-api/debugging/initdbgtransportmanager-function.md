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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74cb2c7d1f79d23e1331cc7192ba2d6acfd9835c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761650"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="52dd2-102">Funzione InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="52dd2-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="52dd2-103">Inizializza il gestore trasporto per connettersi a una destinazione remota per l'enumerazione del runtime e dei processi.</span><span class="sxs-lookup"><span data-stu-id="52dd2-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52dd2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52dd2-104">Syntax</span></span>  
  
```  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="52dd2-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="52dd2-105">Return Value</span></span>  
 <span data-ttu-id="52dd2-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="52dd2-106">S_OK</span></span>  
 <span data-ttu-id="52dd2-107">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="52dd2-107">Success.</span></span>  
  
 <span data-ttu-id="52dd2-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="52dd2-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="52dd2-109">La funzione non è riuscita ad allocare memoria per un gestore trasporto.</span><span class="sxs-lookup"><span data-stu-id="52dd2-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="52dd2-110">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="52dd2-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="52dd2-111">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="52dd2-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52dd2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52dd2-112">Requirements</span></span>  
 <span data-ttu-id="52dd2-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52dd2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52dd2-114">**Intestazione:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="52dd2-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="52dd2-115">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="52dd2-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="52dd2-116">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="52dd2-116">**.NET Framework Versions:** 3.5 SP1</span></span>

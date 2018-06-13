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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423663"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="8292a-102">Funzione InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="8292a-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="8292a-103">Inizializza il gestore trasporto per connettersi a una destinazione remota per l'enumerazione del runtime e dei processi.</span><span class="sxs-lookup"><span data-stu-id="8292a-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8292a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8292a-104">Syntax</span></span>  
  
```  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8292a-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8292a-105">Return Value</span></span>  
 <span data-ttu-id="8292a-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="8292a-106">S_OK</span></span>  
 <span data-ttu-id="8292a-107">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="8292a-107">Success.</span></span>  
  
 <span data-ttu-id="8292a-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8292a-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="8292a-109">La funzione non è riuscita ad allocare memoria per un gestore trasporto.</span><span class="sxs-lookup"><span data-stu-id="8292a-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="8292a-110">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="8292a-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="8292a-111">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="8292a-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8292a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8292a-112">Requirements</span></span>  
 <span data-ttu-id="8292a-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8292a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8292a-114">**Intestazione:** coreclrremotedebugginginterfaces. H</span><span class="sxs-lookup"><span data-stu-id="8292a-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="8292a-115">**Libreria:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="8292a-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="8292a-116">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="8292a-116">**.NET Framework Versions:** 3.5 SP1</span></span>

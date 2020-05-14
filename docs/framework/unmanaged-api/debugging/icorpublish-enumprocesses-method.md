---
title: Metodo ICorPublish::EnumProcesses
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
ms.openlocfilehash: 70255a89cee13abfe63b01351f8ffba51e54665a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396396"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="c9b6c-102">Metodo ICorPublish::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="c9b6c-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="c9b6c-103">Ottiene un enumeratore per i processi gestiti in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="c9b6c-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9b6c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9b6c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9b6c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c9b6c-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="c9b6c-106">Valore dell'enumerazione [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) che specifica il tipo di processo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="c9b6c-106">A value of the [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="c9b6c-107">Nella versione corrente solo COR_PUB_MANAGEDONLY è valido.</span><span class="sxs-lookup"><span data-stu-id="c9b6c-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="c9b6c-108">Puntatore all'indirizzo di un'istanza di [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) che rappresenta l'enumeratore dei processi.</span><span class="sxs-lookup"><span data-stu-id="c9b6c-108">A pointer to the address of an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9b6c-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="c9b6c-109">Remarks</span></span>  
 <span data-ttu-id="c9b6c-110">La raccolta di processi dell'enumeratore si basa su uno snapshot dei processi in esecuzione quando `EnumProcesses` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="c9b6c-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="c9b6c-111">L'enumeratore non includerà i processi che terminano prima o che si avvia dopo `EnumProcesses` la chiamata a.</span><span class="sxs-lookup"><span data-stu-id="c9b6c-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="c9b6c-112">Il `EnumProcesses` metodo può essere chiamato più di una volta in questa istanza di [ICorPublish](icorpublish-interface.md) per creare una nuova raccolta aggiornata di processi.</span><span class="sxs-lookup"><span data-stu-id="c9b6c-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="c9b6c-113">Le raccolte esistenti non saranno interessate dalle chiamate successive del `EnumProcesses` metodo.</span><span class="sxs-lookup"><span data-stu-id="c9b6c-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9b6c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9b6c-114">Requirements</span></span>  
 <span data-ttu-id="c9b6c-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9b6c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9b6c-116">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="c9b6c-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c9b6c-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9b6c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9b6c-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9b6c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9b6c-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c9b6c-119">See also</span></span>

- [<span data-ttu-id="c9b6c-120">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="c9b6c-120">ICorPublish Interface</span></span>](icorpublish-interface.md)

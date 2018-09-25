---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: e0e5a112b7444872dd74cb70bb044ae233334d2a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47076902"
---
# <a name="ienumrawinputdevice"></a><span data-ttu-id="f85bf-102">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="f85bf-102">IEnumRAWINPUTDEVICE</span></span>
<span data-ttu-id="f85bf-103">Questa interfaccia enumera i dispositivi di input non elaborati e viene usata solo da PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="f85bf-103">This interface enumerates the raw input devices, and is only used by PresentationHost.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f85bf-104">Questa API è solo intesa e supportata per l'uso sul computer client locale</span><span class="sxs-lookup"><span data-stu-id="f85bf-104">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="f85bf-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f85bf-105">Members</span></span>  
  
|<span data-ttu-id="f85bf-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f85bf-106">Member</span></span>|<span data-ttu-id="f85bf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f85bf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f85bf-108">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="f85bf-108">IEnumRAWINPUTDEVIC:Next</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)|<span data-ttu-id="f85bf-109">Vengono enumerati i successivi elementi `celt` successivi (ovvero le strutture RAWINPUTDEVICE) nell'elenco dell'enumeratore, che vengono restituiti in `rgelt` insieme al numero effettivo di elementi enumerati in `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="f85bf-109">Enumerates the next `celt` elements (that is, RAWINPUTDEVICE structures) in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>|  
|[<span data-ttu-id="f85bf-110">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="f85bf-110">IEnumRAWINPUTDEVIC:Skip</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-skip.md)|<span data-ttu-id="f85bf-111">Indica all'enumeratore di ignorare i successivi `celt` gli elementi nell'enumerazione in modo che alla successiva chiamata a [ienumrawinputdevic: Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) non restituirà gli elementi.</span><span class="sxs-lookup"><span data-stu-id="f85bf-111">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) will not return those elements.</span></span>|  
|[<span data-ttu-id="f85bf-112">IEnumRAWINPUTDEVIC:Reset</span><span class="sxs-lookup"><span data-stu-id="f85bf-112">IEnumRAWINPUTDEVIC:Reset</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-reset.md)|<span data-ttu-id="f85bf-113">Riporta all'inizio la sequenza di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f85bf-113">Resets the enumeration sequence to the beginning.</span></span>|  
|[<span data-ttu-id="f85bf-114">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="f85bf-114">IEnumRAWINPUTDEVIC:Clone</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-clone.md)|<span data-ttu-id="f85bf-115">Crea un altro enumeratore del dispositivo di input non elaborato con lo stesso stato dell'enumeratore corrente per eseguire l'iterazione dello stesso elenco.</span><span class="sxs-lookup"><span data-stu-id="f85bf-115">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f85bf-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f85bf-116">See Also</span></span>  
 [<span data-ttu-id="f85bf-117">Sull'Input non elaborato</span><span class="sxs-lookup"><span data-stu-id="f85bf-117">About Raw Input</span></span>](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/aboutrawinput.asp)

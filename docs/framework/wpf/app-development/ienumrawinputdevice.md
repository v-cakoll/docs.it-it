---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 5249d7ea359db5d5c58ae87600f61048b465b4c1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964771"
---
# <a name="ienumrawinputdevice"></a>IEnumRAWINPUTDEVICE
Questa interfaccia enumera i dispositivi di input non elaborati e viene usata solo da PresentationHost.exe.  
  
> [!NOTE]
> Questa API è solo intesa e supportata per l'uso sul computer client locale  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|[IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md)|Vengono enumerati i successivi elementi `celt` successivi (ovvero le strutture RAWINPUTDEVICE) nell'elenco dell'enumeratore, che vengono restituiti in `rgelt` insieme al numero effettivo di elementi enumerati in `pceltFetched`.|  
|[IEnumRAWINPUTDEVIC:Skip](ienumrawinputdevic-skip.md)|Indica all'enumeratore di ignorare gli elementi `celt` successivi nell'enumerazione, in modo che la chiamata successiva a [IEnumRAWINPUTDEVIC: Next](ienumrawinputdevic-next.md) non restituisca tali elementi.|  
|[IEnumRAWINPUTDEVIC:Reset](ienumrawinputdevic-reset.md)|Riporta all'inizio la sequenza di enumerazione.|  
|[IEnumRAWINPUTDEVIC:Clone](ienumrawinputdevic-clone.md)|Crea un altro enumeratore del dispositivo di input non elaborato con lo stesso stato dell'enumeratore corrente per eseguire l'iterazione dello stesso elenco.|  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni sull'input non elaborato](/windows/desktop/inputdev/about-raw-input)

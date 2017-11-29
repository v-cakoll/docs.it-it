---
title: GetRawInputDevices
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e936b4ef2cab65e72ca9edbc3b95281815938983
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="getrawinputdevices"></a><span data-ttu-id="22b1d-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="22b1d-102">GetRawInputDevices</span></span>
<span data-ttu-id="22b1d-103">Consente a PresentationHost.exe di individuare i dispositivi di input non elaborato (HID, Human Interface Devices) che interessano l'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="22b1d-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22b1d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22b1d-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22b1d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="22b1d-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="22b1d-106">[out] Un puntatore a un [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) per enumerare i dispositivi di input non elaborati.</span><span class="sxs-lookup"><span data-stu-id="22b1d-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="22b1d-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="22b1d-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="22b1d-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="22b1d-108">HRESULT:</span></span>  
  
 <span data-ttu-id="22b1d-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) verrà utilizzato da PresentationHost.exe solo se viene restituito S_OK.</span><span class="sxs-lookup"><span data-stu-id="22b1d-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="22b1d-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="22b1d-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22b1d-111">Note</span><span class="sxs-lookup"><span data-stu-id="22b1d-111">Remarks</span></span>  
 <span data-ttu-id="22b1d-112">I dispositivi di input non elaborato comprendono una serie di dispositivi tra cui tastiere, mouse e dispositivi meno tradizionali quali i telecomandi.</span><span class="sxs-lookup"><span data-stu-id="22b1d-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="22b1d-113">Dopo avere recuperato l'elenco di dispositivi di input non elaborato, PresentationHost.exe viene registrato per i dispositivi per ricevere messaggi di notifica WM_INPUT.</span><span class="sxs-lookup"><span data-stu-id="22b1d-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22b1d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22b1d-114">See Also</span></span>  
 [<span data-ttu-id="22b1d-115">http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.ASP</span><span class="sxs-lookup"><span data-stu-id="22b1d-115">http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp</span></span>](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp)  
 [<span data-ttu-id="22b1d-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="22b1d-116">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)

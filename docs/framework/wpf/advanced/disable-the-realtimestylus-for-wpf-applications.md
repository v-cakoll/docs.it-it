---
title: Disabilitare RealTimeStylus per le applicazioni WPF
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: ddf4a7f4488f957b2f413d61ad02aa59beba30f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545662"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="344b8-102">Disabilitare RealTimeStylus per le applicazioni WPF</span><span class="sxs-lookup"><span data-stu-id="344b8-102">Disable the RealTimeStylus for WPF Applications</span></span>
<span data-ttu-id="344b8-103">Windows Presentation Foundation (WPF) dispone del supporto incorporato per l'elaborazione dell'input tocco Windows 7. Il supporto viene fornito tramite input con stilo in tempo reale della piattaforma Tablet PC come <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, e <xref:System.Windows.UIElement.OnStylusMove%2A> eventi.</span><span class="sxs-lookup"><span data-stu-id="344b8-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="344b8-104">Windows 7 fornisce inoltre l'input di Multi-touch come messaggi finestra Win32 WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="344b8-104">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="344b8-105">Queste due API si escludono a vicenda sullo stesso HWND.</span><span class="sxs-lookup"><span data-stu-id="344b8-105">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="344b8-106">Abilitazione dell'input tocco tramite la piattaforma di Tablet PC (il valore predefinito per le applicazioni WPF) disabilita i messaggi WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="344b8-106">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="344b8-107">Di conseguenza, per utilizzare WM_TOUCH per ricevere messaggi di tocco da una finestra WPF, è necessario disabilitare il supporto dello stilo incorporato in WPF.</span><span class="sxs-lookup"><span data-stu-id="344b8-107">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="344b8-108">Questa opzione è disponibile in uno scenario, ad esempio una finestra WPF hosting di un componente che utilizza WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="344b8-108">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="344b8-109">Per disabilitare l'ascolto di input con stilo WPF, rimuovere qualsiasi supporto tablet aggiunto dalla finestra WPF.</span><span class="sxs-lookup"><span data-stu-id="344b8-109">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="344b8-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="344b8-110">Example</span></span>  
 <span data-ttu-id="344b8-111">Esempio di codice seguente viene illustrato come rimuovere il supporto della piattaforma predefinito tablet tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="344b8-111">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
```  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.    
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {     
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }                  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="344b8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="344b8-112">See Also</span></span>  
 [<span data-ttu-id="344b8-113">Intercettazione dell'input dello stilo</span><span class="sxs-lookup"><span data-stu-id="344b8-113">Intercepting Input from the Stylus</span></span>](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)

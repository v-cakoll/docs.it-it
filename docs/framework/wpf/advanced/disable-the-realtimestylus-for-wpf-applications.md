---
title: Disabilitare RealTimeStylus per le applicazioni WPF
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: 7b97a451c52b72ee1ddcec5c58e1848a0b10fb7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616910"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="2b631-102">Disabilitare RealTimeStylus per le applicazioni WPF</span><span class="sxs-lookup"><span data-stu-id="2b631-102">Disable the RealTimeStylus for WPF Applications</span></span>
<span data-ttu-id="2b631-103">Windows Presentation Foundation (WPF) ha supporto incorporato per l'elaborazione di input di tocco di Windows 7. Il supporto viene fornito tramite input dello stilo in tempo reale della piattaforma tablet <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, e <xref:System.Windows.UIElement.OnStylusMove%2A> eventi.</span><span class="sxs-lookup"><span data-stu-id="2b631-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="2b631-104">Windows 7 offre anche input multitocco come i messaggi della finestra Win32 WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="2b631-104">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="2b631-105">Queste due API si escludono a vicenda sullo stesso HWND.</span><span class="sxs-lookup"><span data-stu-id="2b631-105">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="2b631-106">Abilitazione dell'input tocco tramite la piattaforma tablet (impostazione predefinita per le applicazioni WPF) disabilita i messaggi WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="2b631-106">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="2b631-107">Di conseguenza, per ricevere messaggi tramite tocco da una finestra WPF utilizzando WM_TOUCH, è necessario disabilitare il supporto dello stilo incorporato in WPF.</span><span class="sxs-lookup"><span data-stu-id="2b631-107">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="2b631-108">Questa opzione è disponibile in uno scenario, ad esempio una finestra WPF che ospita un componente che usa WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="2b631-108">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="2b631-109">Per disabilitare l'ascolto di input dello stilo WPF, rimuovere qualsiasi supporto tablet aggiunto dalla finestra WPF.</span><span class="sxs-lookup"><span data-stu-id="2b631-109">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b631-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b631-110">Example</span></span>  
 <span data-ttu-id="2b631-111">Esempio di codice seguente viene illustrato come rimuovere il supporto della piattaforma predefinita tablet tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="2b631-111">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2b631-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b631-112">See also</span></span>
- [<span data-ttu-id="2b631-113">Intercettazione dell'input dello stilo</span><span class="sxs-lookup"><span data-stu-id="2b631-113">Intercepting Input from the Stylus</span></span>](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)

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
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Disabilitare RealTimeStylus per le applicazioni WPF
Windows Presentation Foundation (WPF) dispone del supporto incorporato per l'elaborazione dell'input tocco Windows 7. Il supporto viene fornito tramite input con stilo in tempo reale della piattaforma Tablet PC come <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, e <xref:System.Windows.UIElement.OnStylusMove%2A> eventi. Windows 7 fornisce inoltre l'input di Multi-touch come messaggi finestra Win32 WM_TOUCH. Queste due API si escludono a vicenda sullo stesso HWND. Abilitazione dell'input tocco tramite la piattaforma di Tablet PC (il valore predefinito per le applicazioni WPF) disabilita i messaggi WM_TOUCH. Di conseguenza, per utilizzare WM_TOUCH per ricevere messaggi di tocco da una finestra WPF, è necessario disabilitare il supporto dello stilo incorporato in WPF. Questa opzione è disponibile in uno scenario, ad esempio una finestra WPF hosting di un componente che utilizza WM_TOUCH.  
  
 Per disabilitare l'ascolto di input con stilo WPF, rimuovere qualsiasi supporto tablet aggiunto dalla finestra WPF.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come rimuovere il supporto della piattaforma predefinito tablet tramite reflection.  
  
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
  
## <a name="see-also"></a>Vedere anche  
 [Intercettazione dell'input dello stilo](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)

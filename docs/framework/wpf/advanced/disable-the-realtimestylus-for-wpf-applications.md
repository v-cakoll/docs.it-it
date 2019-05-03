---
title: Disabilitare RealTimeStylus per le applicazioni WPF
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: e44b71ac5af64ab3a6cb008db71e5a8881592e91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962490"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Disabilitare RealTimeStylus per le applicazioni WPF
Windows Presentation Foundation (WPF) ha supporto incorporato per l'elaborazione di input di tocco di Windows 7. Il supporto viene fornito tramite input dello stilo in tempo reale della piattaforma tablet <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, e <xref:System.Windows.UIElement.OnStylusMove%2A> eventi. Windows 7 offre anche input multitocco come i messaggi della finestra Win32 WM_TOUCH. Queste due API si escludono a vicenda sullo stesso HWND. Abilitazione dell'input tocco tramite la piattaforma tablet (impostazione predefinita per le applicazioni WPF) disabilita i messaggi WM_TOUCH. Di conseguenza, per ricevere messaggi tramite tocco da una finestra WPF utilizzando WM_TOUCH, è necessario disabilitare il supporto dello stilo incorporato in WPF. Questa opzione è disponibile in uno scenario, ad esempio una finestra WPF che ospita un componente che usa WM_TOUCH.  
  
 Per disabilitare l'ascolto di input dello stilo WPF, rimuovere qualsiasi supporto tablet aggiunto dalla finestra WPF.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come rimuovere il supporto della piattaforma predefinita tablet tramite reflection.  
  
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

- [Intercettazione dell'input dello stilo](intercepting-input-from-the-stylus.md)

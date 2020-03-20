---
title: Disabilitare RealTimeStylus
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: c2500b494f76c85e4b23823a44a180d85d5092ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186075"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Disabilitare RealTimeStylus per le applicazioni WPF

Windows Presentation Foundation (WPF) ha integrato il supporto per l'elaborazione dell'input tocco di Windows 7.Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input. Il supporto viene attraverso l'input dello stilo in tempo reale della piattaforma tablet come <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>e <xref:System.Windows.UIElement.OnStylusMove%2A> gli eventi. Windows 7 fornisce anche l'input multi-touch come messaggi di finestra WM_TOUCH Win32. Queste due API si escludono a vicenda nello stesso HWND. L'abilitazione dell'input tocco tramite la piattaforma tablet (impostazione predefinita per le applicazioni WPF) disabilita i messaggi di WM_TOUCH. Di conseguenza, per usare WM_TOUCH per ricevere messaggi tocco da una finestra WPFWPF, è necessario disabilitare il supporto dello stilo incorporato in WPFWPF. Ciò è applicabile in uno scenario, ad esempio una finestra WPFWPF che ospita un componente che usa WM_TOUCH.  
  
 Per disabilitare l'ascolto WPF per l'input dello stilo, rimuovere qualsiasi supporto tablet aggiunto dal WPFWPF finestra.  
  
## <a name="example"></a>Esempio  
 Il codice di esempio seguente viene illustrato come rimuovere il supporto della piattaforma tablet predefinita utilizzando la reflection.  
  
```csharp  
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

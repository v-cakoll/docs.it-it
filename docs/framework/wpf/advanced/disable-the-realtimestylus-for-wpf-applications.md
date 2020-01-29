---
title: Disabilitare il Metodo RealTimeStylus
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: 74145c32af7e9ebbc774a0301e205aa1eb1539b3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737946"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Disabilitare RealTimeStylus per le applicazioni WPF

Windows Presentation Foundation (WPF) ha integrato il supporto per l'elaborazione dell'input tocco di Windows 7. Il supporto deriva dall'input dello stilo in tempo reale della piattaforma Tablet come <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>e <xref:System.Windows.UIElement.OnStylusMove%2A> eventi. Windows 7 fornisce inoltre input multitocco come messaggi della finestra WM_TOUCH Win32. Queste due API si escludono a vicenda nello stesso HWND. L'abilitazione dell'input tocco tramite la piattaforma Tablet (impostazione predefinita per le applicazioni WPF) Disabilita i messaggi di WM_TOUCH. Di conseguenza, per usare WM_TOUCH per ricevere messaggi di tocco da una finestra WPF, è necessario disabilitare il supporto dello stilo incorporato in WPF. Questa operazione è applicabile in uno scenario come una finestra WPF che ospita un componente che usa WM_TOUCH.  
  
 Per disabilitare l'ascolto dell'input dello stilo in WPF, rimuovere il supporto per Tablet aggiunto dalla finestra WPF.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come rimuovere il supporto predefinito della piattaforma Tablet utilizzando la reflection.  
  
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
